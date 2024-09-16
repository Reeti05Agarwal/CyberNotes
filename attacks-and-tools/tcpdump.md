# tcpdump

[tcpdump(1) man page | TCPDUMP & LIBPCAP](https://www.tcpdump.org/manpages/tcpdump.1.html)

**Tcpdump** is a popular network analyzer that can be used to capture and monitor network traffic. It is a command line tool, which means that it does not have a graphical user interface. Tcpdump can be used to filter network traffic so that you can find exactly what you are looking for. You can filter for a specific IP address, protocol, or port number.

**sudo tcpdump \[-i interface] \[option(s)] \[expression(s)]**

* The **sudo tcpdump** command begins running tcpdump using elevated permissions as sudo.\*\*
* The **i** parameter specifies the network interface to capture network traffic. You must specify a network interface to capture from to begin capturing packets. For example, if you specify **i any** you’ll sniff traffic from all network interfaces on the system.
* The **option(s)** are optional and provide you with the ability to alter the execution of the command. The **expression(s)** are a way to further filter network traffic packets so that you can isolate network traffic. You’ll learn more about **option(s)** and **expression(s)** in the next section.

The following is a simple tcpdump command that can be used to capture packets:

```
sudo tcpdump -i any -v -c 1

```

This command will capture one packet from any available network interface. The output of the command will include the following information:

* The packet's timestamp
* The packet's IP address
* The packet's protocol
* The packet's length
* The packet's TCP flags

To capture and analyze a specific protocol, you can use the `-w` option to write the captured traffic to a file. You can then use a protocol analyzer, such as Wireshark, to open and analyze the captured traffic.

Here is an example of how to capture and analyze HTTP traffic using tcpdump:

```
sudo tcpdump -i any -w http.pcap port 80
```

To filter network traffic based on a specific criterion, you can use the `-f` option. For example, to filter for all traffic to or from a specific IP address, you can use the following command:

```
sudo tcpdump -i any -f "host 192.168.1.1"

```

To filter for all traffic on a specific port, you can use the following command:

```
sudo tcpdump -i any -f "port 80"

```

To filter for all traffic using a specific protocol, you can use the following command:

```
sudo tcpdump -i any -f "tcp"

```

You can also combine multiple filters to create more complex filtering rules. For example, to filter for all TCP traffic to or from a specific IP address on port 80, you can use the following command:

```
sudo tcpdump -i any -f "tcp and host 192.168.1.1 and port 80"

```

Tcpdump filters are a powerful tool that can be used to isolate and analyze specific types of network traffic.

Here are some additional examples of how to use tcpdump filters:

* To filter for all traffic to or from a specific domain name, you can use the following command:

```
sudo tcpdump -i any -f "dst host example.com or src host example.com"

```

* To filter for all traffic using a specific application, you can use the following command:

```
sudo tcpdump -i any -f "app ssh"

```

* To filter for all traffic that is encrypted using SSL/TLS, you can use the following command:

```
sudo tcpdump -i any -f "ssl"

```

Tcpdump filters are a valuable tool for anyone who wants to learn more about network traffic and how to troubleshoot network problems.

Tcpdump captures and displays TCP flags in the output using a combination of the `-v` (verbose) and `-S` (show TCP sequence numbers and flags) options.

The `-v` option tells tcpdump to display detailed packet information, including the TCP flags. The `-S` option tells tcpdump to display the TCP sequence numbers and flags in a human-readable format.

When tcpdump captures a TCP packet, it extracts the TCP flags from the packet header and displays them in the output. The TCP flags are represented by a single character, which corresponds to the following values:

* **U:** Urgent pointer field significant
* **A:** Acknowledgment field significant
* **P:** Push function active
* **R:** Reset the connection
* **S:** Synchronize sequence numbers
* **F:** Finish
* **C:** Congestion experienced

For example, the following tcpdump output shows a TCP packet with the SYN and ACK flags set:

```
15:07:08.813523 IP 192.168.1.1.5000 > 192.168.1.100.80: Flags [S], seq 1234567890, win 65535, options [mss 1460,sackOK,TS val 1234567890 ecr 0,nop,wscale 7], length 0

```

The `[S]` in the Flags field indicates that the SYN flag is set. The `[A]` in the Flags field indicates that the ACK flag is set.

Tcpdump can also be used to filter for specific TCP flags. For example, to filter for all TCP packets with the SYN flag set, you can use the following command:

```
sudo tcpdump -i any -f "tcp[tcpflags] & (tcp-syn) != 0"

```

Tcpdump filters are a powerful tool that can be used to isolate and analyze specific types of network traffic.

### **w**

Using the **-w** flag, you can write or save the sniffed network packets to a packet capture file instead of just printing it out in the terminal. This is very useful because you can refer to this saved file for later analysis. In this command, tcpdump is capturing network traffic from all network interfaces and saving it to a packet capture file named **packetcapture.pcap**:

### **sudo tcpdump -i any -w packetcapture.pcap**

### **r**

Using the **-r** flag, you can read a packet capture file by specifying the file name as a parameter. Here is an example of a tcpdump command that reads a file called **packetcapture.pcap**:

### **sudo tcpdump -r packetcapture.pcap**

### **v**

As you’ve learned, packets contain a lot of information. By default, tcpdump will not print out all of a packet's information. This option, which stands for verbose, lets you control how much packet information you want tcpdump to print out.

There are three levels of verbosity you can use depending on how much packet information you want tcpdump to print out. The levels are **-v**, **-vv**, and **-vvv**. The level of verbosity increases with each added v. The verbose option can be helpful if you’re looking for packet information like the details of a packet’s IP header fields. Here’s an example of a tcpdump command that reads the **packetcapture.pcap** file with verbosity:

### **sudo tcpdump -r packetcapture.pcap -v**

### **c**

The **-c** option stands for count. This option lets you control how many packets tcpdump will capture. For example, specifying **-c 1** will only print out one single packet, whereas **-c 10** prints out 10 packets. This example is telling tcpdump to only capture the first three packets it sniffs from **any** network interface:

### **sudo tcpdump -i any -c 3**

### **n**

By default, tcpdump will perform name resolution. This means that tcpdump automatically converts IP addresses to names. It will also resolve ports to commonly associated services that use these ports. This can be problematic because tcpdump isn’t always accurate in name resolution. For example, tcpdump can capture traffic from port 80 and automatically translates port 80 to HTTP in the output. However, this is misleading because port 80 isn’t always going to be using HTTP; it could be using a different protocol.

Additionally, name resolution uses what’s known as a reverse DNS lookup. A reverse DNS lookup is a query that looks for the domain name associated with an IP address. If you perform a reverse DNS lookup on an attacker’s system, they might be alerted that you are investigating them through their DNS records.

Using the **-n** flag disables this automatic mapping of numbers to names and is considered to be best practice when sniffing or analyzing traffic. Using **-n** will not resolve hostnames, whereas **-nn** will not resolve _both_ hostnames or ports. Here’s an example of a tcpdump command that reads the **packetcapture.pcap** file with verbosity and disables name resolution:

## Expressions

Using filter expressions in tcpdump commands is also optional, but knowing how and when to use filter expressions can be helpful during packet analysis. There are many ways to use filter expressions.

If you want to specifically search for network traffic by protocol, you can use filter expressions to isolate network packets. For example, you can filter to find only IPv6 traffic using the filter expression **ip6**.

You can also use boolean operators like **and**, **or**, or **not** to further filter network traffic for specific IP addresses, ports, and more. The example below reads the **packetcapture.pcap** file and combines two expressions **ip and port 80** using the **and** boolean operator:

**sudo tcpdump -r packetcapture.pcap -n 'ip and port 80'**

**Pro tip:** You can use single or double quotes to ensure that tcpdump executes all of the expressions. You can also use parentheses to group and prioritize different expressions. Grouping expressions is helpful for complex or lengthy commands. For example, the command **ip and (port 80 or port 443)** tells tcpdump to prioritize executing the filters enclosed in the parentheses before filtering for IPv4.

Not all the data packets are the same color. Coloring rules are used to provide high-level visual cues to help you quickly classify the different types of data. Since network packet capture files can contain large amounts of data, you can use coloring rules to quickly identify the data that is relevant to you. The example packet lists a group of light blue packets that all contain DNS traffic, followed by green packets that contain a mixture of TCP and HTTP protocol traffic.
