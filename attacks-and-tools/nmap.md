# nmap

[https://www.stationx.net/top-nmap-commands/](https://www.stationx.net/top-nmap-commands/)

NETWORK MAPPER

*   Network Segment:

    Grp of comp connected using a shared medium. A subnetwork (subnet) has its own IP address range and is connected to a more extensive network via a router. There might be a firewall enforcing security policies depending on each network.
*   Layers:

    ![745e0412b319d324352c7b29863b74f4.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/0912b6d9-b303-4e6e-9b4a-91bff1692fe2/745e0412b319d324352c7b29863b74f4.png)

    * ARP from Link Layer
    * ICMP from Network Layer
    * TCP from Transport Layer
    * UDP from Transport Layer
*   Connections through ports

    Its imp to conduct a security audit on given IP addresses by first understanding the services running on them. This process involves port scanning, where computers open specific ports to receive connections for various services. Ports are essential for distinguishing between different network requests and services. The connection is established between an open port on the server and a randomly selected port on your computer, allowing different services to operate on the same server.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/468b2481-d9a7-427a-842d-9cd991e66901/Untitled.png)

    Every computer has a total of 65535 available ports; however, many of these are registered as standard ports. For example, a HTTP Webservice can nearly always be found on port 80 of the server. A HTTPS Webservice can be found on port 443. Windows NETBIOS can be found on port 139 and SMB can be found on port 445.

    Ports are a networking constructs are used to direct traffic to the right application on a server.

    ***
*   QUES:

    *   By which command option will nmap use ip and domains from file ?

        ```python
        nmap -iL filename.txt
        ```
    *   Full port scan command is

        ```python
        nmap -p- target
        ```

        ```python
        nmap -p 0-65536
        ```

        ***
    *   Do nmap scan host with service name? for eg;- nmap -p ssh,telnet,imap 192.168.0.22

        ```python
        nmap --servicedb 192.168.0.22
        ```
    *   What is command Option for Stealth Scan in Nmap ?

        ```python
        nmap -sS target
        ```
    *   What command Option is used for Default NSE Script Scan ?

        ```python
        nmap -sC target
        ```
    *   What command Option is used for  only host discovery ?

        ```python
        nmap -sn target
        ```
    *   What is default ttl value of windows

        128

    ***
*

***

* **Nmap Port Scanning**:
  * Nmap sequentially connects to each port on the target.
  * Responses categorize ports as open, closed, or filtered (typically by a firewall).
* **Determining Open Ports**:
  * Identifies open ports to proceed with service enumeration.
  * Enumeration can be manual or conducted with tools like Nmap.
* **Port Classification**:
  * Well-known ports range from 0 to 1023.
  * Registered ports span from 1024 to 49151.
  * Remaining ports, from 49152 to 65535, are dynamically assignable by applications.

***

*   NULL, FIN and Xmas

    All three are interlinked and are used primarily as they tend to be even stealthier, relatively speaking, than a SYN "stealth" scan.

    ### NULL:

    NULL scans (`-sN`) are when the TCP request is sent with no flags set at all. As per the RFC, the target host should respond with a RST if the port is closed.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/5602c072-abf2-44c6-8c10-9cc55b07c5c7/Untitled.png)

    ### FIN:

    FIN scans (`-sF`) work in an almost identical fashion; however, instead of sending a completely empty packet, a request is sent with the FIN flag (usually used to gracefully close an active connection). Once again, Nmap expects a RST if the port is closed.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/4c8f93e3-fd3e-48c3-9197-103b6f79007c/Untitled.png)

    ### Xmas:

    Xmas scans (`-sX`) send a malformed TCP packet and expects a RST response for closed ports. It's referred to as an xmas scan as the flags that it sets (PSH, URG and FIN) give it the appearance of a blinking christmas tree when viewed as a packet capture in Wireshark.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/c6c38524-2ce8-4a03-8f01-1836e86dd9c4/Untitled.png)

    If the port is open then there is no response to the malformed packet. Unfortunately (as with open UDP ports), that is _also_ an expected behaviour if the port is protected by a firewall, so NULL, FIN and Xmas scans will only ever identify ports as being _open|filtered_, _closed_, or _filtered_. If a port is identified as filtered with one of these scans then it is usually because the target has responded with an ICMP unreachable packet.

    That said, the goal here is, of course, firewall evasion. Many firewalls are configured to drop incoming TCP packets to blocked ports which have the SYN flag set (thus blocking new connection initiation requests). By sending requests which do not contain the SYN flag, we effectively bypass this kind of firewall. Whilst this is good in theory, most modern IDS solutions are savvy to these scan types, so don't rely on them to be 100% effective when dealing with modern systems.
*   ping sweep

    To perform a ping sweep, we use the `-sn` switch in conjunction with IP ranges which can be specified with either a hypen (`-`)

    The `-sn` switch tells Nmap not to scan any ports -- forcing it to rely primarily on ICMP echo packets (or ARP requests on a local network, if run with sudo or directly as the root user) to identify targets. In addition to the ICMP echo requests, the `-sn` switch will also cause nmap to send a TCP SYN packet to port 443 of the target, as well as a TCP ACK (or TCP SYN if not run as root) packet to port 80 of the target.
*   NSE

    The **N**map **S**cripting **E**ngine (NSE) is an incredibly powerful addition to Nmap, extending its functionality quite considerably. NSE Scripts are written in the _Lua_ programming language, and can be used to do a variety of things: from scanning for vulnerabilities, to automating exploits for them. The NSE is particularly useful for reconnaisance, however, it is well worth bearing in mind how extensive the script library is.

    * `safe`:- Won't affect the target
    * `intrusive`:- Not safe: likely to affect the target
    * `vuln`:- Scan for vulnerabilities
    * `exploit`:- Attempt to exploit a vulnerability
    * `auth`:- Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
    * `brute`:- Attempt to bruteforce credentials for running services
    * `discovery`:- Attempt to query running services for further information about the network (e.g. query an SNMP server).
*   NSE Scripts

    To know about a script

    ```cpp
    nmap --script-help <script-name>
    ```

    To search for something in a script:

    ```cpp
    grep "safe" /usr/share/nmap/scripts/script.db
    ```

    If the command `--script=safe` is run, then any applicable safe scripts will be run against the target (Note: only scripts which target an active service will be activated).

    To run a specific script, we would use `--script=<script-name>` , e.g. `--script=http-fileupload-exploiter`.

    Multiple scripts can be run simultaneously in this fashion by separating them by a comma. For example: `--script=smb-enum-users,smb-enum-shares`.

    Some scripts require arguments (for example, credentials, if they're exploiting an authenticated vulnerability). These can be given with the `--script-args` Nmap switch. An example of this would be with the `http-put` script (used to upload files using the PUT method). This takes two arguments: the URL to upload the file to, and the file's location on disk.  For example:

    `nmap -p 80 --script http-put --script-args http-put.url='/dav/shell.php',http-put.file='./shell.php'`

    Note that the arguments are separated by commas, and connected to the corresponding script with periods (i.e.  `<script-name>.<argument>`).

    [NSEDoc Reference Portal — Nmap Scripting Engine documentation](https://nmap.org/nsedoc/)

    `/usr/share/nmap/scripts/script.db` file.

    Nmap stores its scripts on Linux at `/usr/share/nmap/scripts`.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/76ac5a12-c5fc-4a67-8509-5ab71f0d8afa/Untitled.png)

    The second way to search for scripts is quite simply to use the `ls` command.

    `ls -l /usr/share/nmap/scripts/*ftp*`

    The same techniques can also be used to search for categories of script. For example:

    ```
    grep "safe" /usr/share/nmap/scripts/script.db
    ```

    ### Installing scripts:

    1. `sudo apt update && sudo apt install nmap`
    2. (`sudo wget -O /usr/share/nmap/scripts/<script-name>.nse <https://svn.nmap.org/nmap/scripts/><script-name>.nse`) followed by `nmap --script-updatedb` to update the script file

    ### Firewall Invasion:

    Nmap provides an option for this: `-Pn`, which tells Nmap to not bother pinging the host before scanning it. This means that Nmap will always treat the target host(s) as being alive, effectively bypassing the ICMP block; however, it comes at the price of potentially taking a very long time to complete the scan (if the host really is dead then Nmap will still be checking and double checking every specified port).

    * `f`:- Used to fragment the packets (i.e. split them into smaller pieces) making it less likely that the packets will be detected by a firewall or IDS.
    * An alternative to `f`, but providing more control over the size of the packets: `-mtu <number>`, accepts a maximum transmission unit size to use for the packets sent. This _must_ be a multiple of 8.
    * `-scan-delay <time>ms`:- used to add a delay between packets sent. This is very useful if the network is unstable, but also for evading any time-based firewall/IDS triggers which may be in place.
    * `-badsum`:- this is used to generate in invalid checksum for packets. Any real TCP/IP stack would drop this packet, however, firewalls may potentially respond automatically, without bothering to check the checksum of the packet. As such, this switch can be used to determine the presence of a firewall/IDS.
*   Switches

    TARGET SPECIFICATION: Can pass hostnames, IP addresses, networks, etc. Ex: [scanme.nmap.org](http://scanme.nmap.org/), [microsoft.com/24](http://microsoft.com/24), 192.168.0.1; 10.0.0-255.1-254 -iL \<inputfilename>: Input from list of hosts/networks -iR \<num hosts>: Choose random targets --exclude \<host1\[,host2]\[,host3],...>: Exclude hosts/networks --excludefile \<exclude\_file>: Exclude list from file HOST DISCOVERY: -sL: List Scan - simply list targets to scan -sn: Ping Scan - disable port scan -Pn: Treat all hosts as online -- skip host discovery -PS/PA/PU/PY\[portlist]: TCP SYN/ACK, UDP or SCTP discovery to given ports -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes -PO\[protocol list]: IP Protocol Ping -n/-R: Never do DNS resolution/Always resolve \[default: sometimes] --dns-servers \<serv1\[,serv2],...>: Specify custom DNS servers --system-dns: Use OS's DNS resolver --traceroute: Trace hop path to each host SCAN TECHNIQUES: -sS/sT/sA/sW/sM: TCP SYN/Connect()/ACK/Window/Maimon scans -sU: UDP Scan -sN/sF/sX: TCP Null, FIN, and Xmas scans --scanflags \<flags>: Customize TCP scan flags -sI \<zombie host\[:probeport]>: Idle scan -sY/sZ: SCTP INIT/COOKIE-ECHO scans -sO: IP protocol scan -b \<FTP relay host>: FTP bounce scan PORT SPECIFICATION AND SCAN ORDER: -p \<port ranges>: Only scan specified ports Ex: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080,S:9 --exclude-ports \<port ranges>: Exclude the specified ports from scanning -F: Fast mode - Scan fewer ports than the default scan -r: Scan ports sequentially - don't randomize --top-ports \<number>: Scan \<number> most common ports --port-ratio \<ratio>: Scan ports more common than \<ratio> SERVICE/VERSION DETECTION: -sV: Probe open ports to determine service/version info --version-intensity \<level>: Set from 0 (light) to 9 (try all probes) --version-light: Limit to most likely probes (intensity 2) --version-all: Try every single probe (intensity 9) --version-trace: Show detailed version scan activity (for debugging) SCRIPT SCAN: -sC: equivalent to --script=default --script=\<Lua scripts>: \<Lua scripts> is a comma separated list of directories, script-files or script-categories --script-args=\<n1=v1,\[n2=v2,...]>: provide arguments to scripts --script-args-file=filename: provide NSE script args in a file --script-trace: Show all data sent and received --script-updatedb: Update the script database. --script-help=\<Lua scripts>: Show help about scripts. \<Lua scripts> is a comma-separated list of script-files or script-categories. OS DETECTION: -O: Enable OS detection --osscan-limit: Limit OS detection to promising targets --osscan-guess: Guess OS more aggressively TIMING AND PERFORMANCE: Options which take \<time> are in seconds, or append 'ms' (milliseconds), 's' (seconds), 'm' (minutes), or 'h' (hours) to the value (e.g. 30m). -T<0-5>: Set timing template (higher is faster) --min-hostgroup/max-hostgroup \<size>: Parallel host scan group sizes --min-parallelism/max-parallelism \<numprobes>: Probe parallelization --min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout \<time>: Specifies probe round trip time. --max-retries \<tries>: Caps number of port scan probe retransmissions. --host-timeout \<time>: Give up on target after this long --scan-delay/--max-scan-delay \<time>: Adjust delay between probes --min-rate \<number>: Send packets no slower than \<number> per second --max-rate \<number>: Send packets no faster than \<number> per second FIREWALL/IDS EVASION AND SPOOFING: -f; --mtu \<val>: fragment packets (optionally w/given MTU) -D \<decoy1,decoy2\[,ME],...>: Cloak a scan with decoys -S \<IP\_Address>: Spoof source address -e \<iface>: Use specified interface -g/--source-port \<portnum>: Use given port number --proxies \<url1,\[url2],...>: Relay connections through HTTP/SOCKS4 proxies --data \<hex string>: Append a custom payload to sent packets --data-string \<string>: Append a custom ASCII string to sent packets --data-length \<num>: Append random data to sent packets --ip-options \<options>: Send packets with specified ip options --ttl \<val>: Set IP time-to-live field --spoof-mac \<mac address/prefix/vendor name>: Spoof your MAC address --badsum: Send packets with a bogus TCP/UDP/SCTP checksum OUTPUT: -oN/-oX/-oS/-oG \<file>: Output scan in normal, XML, s|\<rIpt kIddi3, and Grepable format, respectively, to the given filename. -oA \<basename>: Output in the three major formats at once -v: Increase verbosity level (use -vv or more for greater effect) -d: Increase debugging level (use -dd or more for greater effect) --reason: Display the reason a port is in a particular state --open: Only show open (or possibly open) ports --packet-trace: Show all packets sent and received --iflist: Print host interfaces and routes (for debugging) --append-output: Append to rather than clobber specified output files --resume \<filename>: Resume an aborted scan --noninteractive: Disable runtime interactions via keyboard --stylesheet \<path/URL>: XSL stylesheet to transform XML output to HTML --webxml: Reference stylesheet from [Nmap.Org](http://nmap.org/) for more portable XML --no-stylesheet: Prevent associating of XSL stylesheet w/XML output MISC: -6: Enable IPv6 scanning -A: Enable OS detection, version detection, script scanning, and traceroute --datadir \<dirname>: Specify custom Nmap data file location --send-eth/--send-ip: Send using raw ethernet frames or IP packets --privileged: Assume that the user is fully privileged --unprivileged: Assume the user lacks raw socket privileges -V: Print version number -h: Print this help summary page. EXAMPLES: nmap -v -A [scanme.nmap.org](http://scanme.nmap.org/) nmap -v -sn 192.168.0.0/16 10.0.0.0/8 nmap -v -iR 10000 -Pn -p 80 SEE THE MAN PAGE ([https://nmap.org/book/man.html](https://nmap.org/book/man.html)) FOR MORE OPTIONS AND EXAMPLES

    ***
* Ques
  *   Which category of scripts would be a _very_ bad idea to run in a production environment?

      Intrusive

***

*   **Live Host Discovery**

    ### ARP Scan: (Address Resolution Protocol)

    [royhills](http://www.royhills.co.uk/wiki/index.php/Main\_Page)

    aims to get the hardware address (MAC address) so that communication over the link-layer becomes possible. all packets generated by your scanner will be routed via the default gateway (router) to reach the systems on another subnet; however, the ARP queries won’t be routed and hence cannot cross the subnet router. ARP is a link-layer protocol, and ARP packets are bound to their subnet.

    TO SPECIFY THE TARGET:

    * list: `MACHINE_IP scanme.nmap.org example.com` will scan 3 IP addresses. You can also provide a file as input for your list of targets, `nmap -iL list_of_hosts.txt`.
    * range: `10.11.12.15-20` will scan 6 IP addresses: `10.11.12.15`, `10.11.12.16`,… and `10.11.12.20`.
    * subnet: `MACHINE_IP/30` will scan 4 IP addresses.

    to check the list of hosts that Nmap will scan, you can use `nmap -sL TARGETS`. This option will give you a detailed list of the hosts that Nmap will scan without scanning them; however, Nmap will attempt a reverse-DNS resolution on all the targets to obtain their names. Names might reveal various information to the pentester.

    sending a frame to the broadcast address on the network segment and asking the computer with a specific IP address to respond by providing its MAC (hardware) address.

    1. When a _privileged_ user tries to scan targets on a local network (Ethernet), Nmap uses _ARP requests_. A privileged user is `root` or a user who belongs to `sudoers` and can run `sudo`.
    2. When a _privileged_ user tries to scan targets outside the local network, Nmap uses ICMP echo requests, TCP ACK (Acknowledge) to port 80, TCP SYN (Synchronize) to port 443, and ICMP timestamp request.
    3. When an _unprivileged_ user tries to scan targets outside the local network, Nmap resorts to a TCP 3-way handshake by sending SYN packets to ports 80 and 443.

    `nmap -sn TARGETS` → To discover online hosts without port-scanning the live systems.

    `nmap -PR -sn TARGETS` → To perform an ARP scan without port-scanning. where `-PR` indicates that you only want an ARP scan.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/4e4c31cc-abfb-4fe3-a2a4-b61df81cc687/Untitled.png)

    To get the MAC address, the OS sends an ARP query. A host that replies to ARP queries is up. The ARP query only works if the target is on the same subnet as yourself, i.e., on the same Ethernet/WiFi.

    Wireshark displays the source MAC address, destination MAC address, protocol, and query related to each ARP request. The source address is the MAC address of our AttackBox, while the destination is the broadcast address as we don’t know the MAC address of the target. However, we see the target’s IP address, which appears in the Info column. In the figure, we can see that we are requesting the MAC addresses of all the IP addresses on the subnet, starting with `10.10.210.1`. The host with the IP address we are asking about will send an ARP reply with its MAC address, and that’s how we will know that it is online.

    `arp-scan --localnet` or simply `arp-scan -l`. This command will send ARP queries to all valid IP addresses on your local networks. Moreover, if your system has more than one interface and you are interested in discovering the live hosts on one of them, you can specify the interface using `-I`. For instance, `sudo arp-scan -I eth0 -l` will send ARP queries for all valid IP addresses on the `eth0` interface.

    ### ICMP Scan:

    ICMP ping uses Type 8 (Echo) and Type 0 (Echo Reply). If you want to ping a system on the same subnet, an ARP query should precede the ICMP Echo.

    To use ICMP echo request to discover live hosts, add the option `-PE`. (Remember to add `-sn` if you don’t want to follow that with a port scan.) As shown in the following figure, an ICMP echo scan works by sending an ICMP echo request and expects the target to reply with an ICMP echo reply if it is online.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/26c01090-7de1-4d84-a220-55b2b19dfaf3/Untitled.png)

    Because ICMP echo requests tend to be blocked, you might also consider ICMP Timestamp or ICMP Address Mask requests to tell if a system is online. Nmap uses timestamp request (ICMP Type 13) and checks whether it will get a Timestamp reply (ICMP Type 14). Adding the `-PP` option tells Nmap to use ICMP timestamp requests. As shown in the figure below, you expect live hosts to reply.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/f1095b92-4d2c-4af4-92f7-fff56ae5275e/Untitled.png)

    Similarly, Nmap uses address mask queries (ICMP Type 17) and checks whether it gets an address mask reply (ICMP Type 18). This scan can be enabled with the option `-PM`. As shown in the figure below, live hosts are expected to reply to ICMP address mask requests.

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/11316d55-3944-4641-a056-91d3cf94dfe9/Untitled.png)

    What is the option required to tell Nmap to use ICMP Timestamp to discover live hosts?

    \-PP

    What is the option required to tell Nmap to use ICMP Address Mask to discover live hosts?

    \-PM

    What is the option required to tell Nmap to use ICMP Echo to discover live hosts?

    \-PE

    ***

    ### TCP/UDP Ping Scan:

    for network scanning purposes, a scanner can send a specially-crafted packet to common TCP or UDP ports to check whether the target will respond. This method is efficient, especially when ICMP Echo is blocked.

    ### **TCP SYN Ping:**

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/0d50974b-0ab7-4cab-9dd6-ecf16577b482/Untitled.png)

    If you want Nmap to use TCP SYN ping, you can do so via the option `-PS` .

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/be848d38-9534-4214-8fdc-d5f2e3c23c04/Untitled.png)

    Privileged users (root and sudoers) can send TCP SYN packets and don’t need to complete the TCP 3-way handshake even if the port is open, as shown in the figure below. Unprivileged users have no choice but to complete the 3-way handshake if the port is open.

    since we didn’t specify any TCP ports to use in the TCP ping scan, Nmap used common ports; in this case, it is TCP port 80. Any service listening on port 80 is expected to reply, indirectly indicating that the host is online.

    ### **TCP ACK Ping:**

    By default, port 80 is used. The syntax is similar to TCP SYN ping. `-PA`

    Requires a priviledged account

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/882690bd-f8f0-4e48-9e29-d0b435640077/Untitled.png)

    ### **UDP Ping:**

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/df8a71eb-cbc1-4c46-95a5-4d335fa4cd96/Untitled.png)

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/db93c4c3-8eed-43bd-b248-685022812562/Untitled.png)

    ### **Masscan:**

    similar but to finish its network scan quickly, Masscan is quite aggressive with the rate of packets it generates.

    The syntax is quite similar: `-p` Target.

    ***

    *   Reverse DNS Server

        Nmap’s default behaviour is to use reverse-DNS online hosts. Because the hostnames can reveal a lot, this can be a helpful step. However, if you don’t want to send such DNS queries, you use `-n` to skip this step.

        By default, Nmap will look up online hosts; however, you can use the option `-R` to query the DNS server even for offline hosts. If you want to use a specific DNS server, you can add the `--dns-servers DNS_SERVER` option.

    | Scan Type              | Example Command                             |
    | ---------------------- | ------------------------------------------- |
    | ARP Scan               | `sudo nmap -PR -sn MACHINE_IP/24`           |
    | ICMP Echo Scan         | `sudo nmap -PE -sn MACHINE_IP/24`           |
    | ICMP Timestamp Scan    | `sudo nmap -PP -sn MACHINE_IP/24`           |
    | ICMP Address Mask Scan | `sudo nmap -PM -sn MACHINE_IP/24`           |
    | TCP SYN Ping Scan      | `sudo nmap -PS22,80,443 -sn MACHINE_IP/30`  |
    | TCP ACK Ping Scan      | `sudo nmap -PA22,80,443 -sn MACHINE_IP/30`  |
    | UDP Ping Scan          | `sudo nmap -PU53,161,162 -sn MACHINE_IP/30` |

    `sn` if you are only interested in host discovery without port-scanning. Omitting `sn` will let Nmap default to port-scanning the live hosts.

    | Option | Purpose                          |
    | ------ | -------------------------------- |
    | `-n`   | no DNS lookup                    |
    | `-R`   | reverse-DNS lookup for all hosts |
    | `-sn`  | host discovery only              |

    ***
* Basic Port Scans
* Advanced Port Scans
* Nmap Post Port Scans
