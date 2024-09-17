# Networking Tools

*   ping

    to test whether a connection to a remote resource is possible.

    * be a website on the internet
    * remote computer
    * ICMP protocol

    ```c
    ping <target>
    ```

    It returns the IP address of the server is it linked to rather than its URL.

    ```c
    ping -c n <target>
    ```

    \-c flag is used to specify that we want to ping n number of times. if this isnt mentioned, then it will ping indefinitely.

    ***
*   traceroot

    used to map the path your request takes as it heads to the target machine.

    ICMP protocol

    ```c
    traceroute <destination>
    ```

    ***
*   whois

    ```c
    whois <domain>
    ```

    to query WHOIS records

    Domains are leased out by companies called Domain Registrars. If you want a domain, you go and register with a registrar, then lease the domain for a certain length of time.

    allows you to query who a domain name is registered to.

    listens on TCP port 43 for incoming requests.

    follows the [RFC 3912](https://www.ietf.org/rfc/rfc3912.txt) specification.

    provides us with:

    * Registrar WHOIS server
    * Registrar URL
    * Record creation date
    * Record update date
    * Registrant contact info and address (unless withheld for privacy)
    * Admin contact info and address (unless withheld for privacy)
    * Tech contact info and address (unless withheld for privacy)

    ***
*   Dig

    Domain Information Groper

    to query DNS database records

    DNS (**D**omain **N**ame **S**ystem) allows us to ask a special server to give us the IP address of the website whos URL we typed

    💡 Dig command returns more info than nslookup

    even allows you to specify a different DNS server to use.

    details for a recursive DNS server are stored in your router. This server will also maintain a cache of results for popular domains; however, if the website you've requested isn't stored in the cache, the recursive server will pass the request on to a _root name_ server.

    Top-Level Domain (TLD) servers are split up into extensions. So, for example, if you were searching for tryhackme\*\*.com\*\* your request would be redirected to a TLD server that handled `.com` domains. If you were searching for bbc\*\*.co.uk\*\* your request would be redirected to a TLD server that handles `.co.uk` domains. As with root name servers, TLD servers keep track of the next level down: _Authoritative name servers_. When a TLD server receives your request for information, the server passes it down to an appropriate Authoritative name server.

    > The most common Linux DNS server is the Berkeley Internet Name Domain (BIND).

    Dig allows us to manually query recursive DNS servers of our choice for information about domains

    ```c
    dig <domain> @<dns-server-ip>
    ```

    dig gives us is the TTL (**T**ime **T**o **L**ive){measured in _seconds_} of the queried DNS record.

    when your computer queries a domain name, it stores the results in its local cache. The TTL of the record tells your computer when to stop considering the record as being valid -- i.e. when it should request the data again, rather than relying on the cached copy.

    ```c
    dig @SERVER DOMAIN_NAME TYPE
    ```

    * SERVER is the DNS server that you want to query.
    * DOMAIN\_NAME is the domain name you are looking up.
    * TYPE contains the DNS record type, as shown in the table provided earlier.

    TYPE:

    | Type | Full Form            |
    | ---- | -------------------- |
    | ns   | NameServer           |
    | mx   | Mail Exchange Server |

    ***
*   nslookup

    Name Server Look Up

    to query DNS database records

    Find the IP address of a domain name

    ```c
    nslookup DOMAIN_NAME
    ```

    or

    ```c
    nslookup OPTIONS DOMAIN_NAME SERVER
    ```

    Three main parameters:

    *   OPTIONS contains the query type.

        | Query type | Result             |
        | ---------- | ------------------ |
        | A          | IPv4 Addresses     |
        | AAAA       | IPv6 Addresses     |
        | CNAME      | Canonical Name     |
        | MX         | Mail Servers       |
        | SOA        | Start of Authority |
        | TXT        | TXT Records        |
    * DOMAIN\_NAME
    *   SERVER is the DNS server that you want to query. You can choose any local or public DNS server to query. Cloudflare offers `1.1.1.1` and `1.0.0.1`, Google offers `8.8.8.8` and `8.8.4.4`, and Quad9 offers `9.9.9.9` and `149.112.112.112`.

        [public dns at DuckDuckGo](https://duckduckgo.com/?q=public+dns)

    ***
*   host

    useful alternative for querying DNS servers for DNS records

    ***
*   gobuster

    [gobuster | Kali Linux Tools](https://www.kali.org/tools/gobuster/)

    To see Usage of gobuster:

    ```c
    gobuster -h
    ```

    To scan a URL with a wordlist and output in ‘grep mode’

    ```dart
    gobuster -u http://IPADDRESS/ -w /usr/share/wordlists/dirb/common.txt -q -n -e
    ```

    DNS mode will search for the subdomains using the given wordlists

    ```dart
    gobuster -m dns -t 100 -u google.com -w /usr/share/wordlists/metasploit/namelist.txt
    ```

    ***
* dirb

***

*   DNS Dumpster

    [DNSdumpster.com - dns recon and research, find and lookup dns records](https://dnsdumpster.com/)

    ***
*   **ViewDNS.info**

    offers _Reverse IP Lookup_

    Initially, each web server would use one or more IP addresses; however, today, it is common to come across shared hosting servers. With shared hosting, one IP address is shared among many different web servers with different domain names.

    to find other servers sharing the same IP addresses

    💡 knowing the IP address does not necessarily lead to a single website.

    ***
*   **Threat Intelligence Platform**

    [Threat Intelligence Platform (TIP) | Integrate #1 Cyber Threat Intel APIs](https://threatintelligenceplatform.com/)

    requires you to provide a domain name or an IP address, and it will launch a series of tests from malware checks to WHOIS and DNS queries.

    Additionally, we see that Name Server (NS) records were resolved to their respective IPv4 and IPv6 addresses

    we could also get a list of other domains on the same IP address.

    ***
*   **Censys**

    [Censys Search](https://search.censys.io/)

    provide a lot of information about IP addresses and domains.

    ***
*   **Shodan**

    [Shodan](https://www.shodan.io/)

    Using shodam from command line:

    1.  configure `shodan` to use your API key

        ```c
        shodan init API_KEY
        ```
    2.  looking up information about one of the IP addresses

        ```c
        shodan host IP_ADDRESS
        ```

    Provides:

    * IP address
    * hosting company
    * geographic location
    * server type and version

    ***

    Devices run services, and Shodan stores information about them. The information is stored in a _banner_

    ***

    [Shodan - The Complete Guide, Featured on TryHackMe](https://skerritt.blog/shodan/)

    [TryHackMe | Shodan.io](https://tryhackme.com/room/shodan)
*   CrunchBase

    [Crunchbase: Discover innovative companies and the people behind them](https://www.crunchbase.com/)

    To understand the company

***

## Email Addresses of company:

*   Hunter.io

    [Find email addresses in seconds • Hunter (Email Hunter)](https://hunter.io/)
*   snov.io

    [Sales automation & acceleration at scale | Snov.io](https://snov.io/)
*   Emailhippo

    [Email verification for marketers and fraud fighters | Email Hippo](https://www.emailhippo.com/)

    To verify the email

***

The three options the user can use to add redundancy to the routers in a company are:

1. VRRP (Virtual Router Redundancy Protocol)
2. HSRP (Hot Standby Router Protocol)
3. GLBP (Gateway Load Balancing Protocol)

The Spanning Tree Protocol (STP) is a network protocol that ensures a loop-free topology in a Layer 2 network by blocking redundant paths. It works by identifying and shutting down redundant links to prevent loops while allowing for network redundancy in case of link failures. This helps to maintain network stability and prevent broadcast storms and other network issues caused by loops.
