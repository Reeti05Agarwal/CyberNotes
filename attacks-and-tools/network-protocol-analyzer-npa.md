# Network Protocol Analyzer (NPA)

* **Network Protocol Analyzer (NPA)**:
  * Also known as a packet sniffer or packet analyzer.
  * Designed to capture and analyze network data traffic.
* **Network Traffic Analysis**:
  * Monitors network activity to identify potential security threats.
  * Understanding normal traffic patterns aids in spotting anomalies.
* **Indicators of Compromise (IoCs)**:
  * Observable signs indicating potential security incidents.
  * Detecting IoCs, like abnormal outbound traffic, prompts further investigation.
* **Data Exfiltration**:
  * Unauthorized transmission of data from a system.
  * Used by attackers to steal sensitive information like usernames, passwords, or intellectual property.
* **Common Analyzers**:
  * SolarWinds NetFlow Traffic Analyzer
  * ManageEngine OpManager
  * Azure Network Watcher
  * Wireshark
  * tcpdump
* **Command and Control (C2)**:
  * Malicious communication techniques used by attackers to control compromised systems.

### **Temporal Patterns**:

* Network packets contain time-related information.
* Deviations from normal traffic patterns can indicate potential security breaches.
* **Packet Capture**:
  * Intercepting and recording network traffic for analysis.
  * Essential for network monitoring, incident investigation, and security analysis.
* **Packet Structure**:
  * Comprises header, payload, and footer sections.
  * Headers contain vital information like source/destination IP addresses and protocol type.
* **IPv4 Header Fields**:
  * Various fields including version, total length, TTL, protocol, source/destination addresses, and more.

### **IPv6**:

* IPv6 header includes fields like version, traffic class, flow label, payload length, next header, hop limit, and source/destination addresses.
* **Packet Analysis**:
  * Examining captured packets to identify patterns and security threats.
  * Essential for troubleshooting network issues and enhancing performance.
* **Packet Sniffers**:
  * Tools capturing and analyzing network traffic.
  * Examples include Wireshark, tcpdump, and Snort.

### **How Network Protocol Analyzers Work**:

1. **Packet Collection**:
   * Network Interface Cards (NICs) capture raw binary data.
   * NICs must be in monitoring or promiscuous mode to access all network traffic.
2. **Data Conversion**:
   * Network protocol analyzers convert binary data into human-readable formats.

* **Packet Crafting**:
  * Creating customized packets for attacks and vulnerability exploitation.
  * Involves packet assembly, editing, playing, and analysis.
* **Steps in Packet Crafting**:
  1. **Packet Assembly**: Selecting target network, gathering vulnerability information, and creating invisible packets.
  2. **Packet Editing**: Testing and editing packets for optimal data retrieval.
  3. **Packet Playing**: Sending packets to the target and analyzing the results.
  4. **Packet Analysis**: Analyzing received packets using tools like Wireshark and tcpdump.

However, malicious actors can use protocols and ports that are not commonly associated to maintain communications between the compromised system and their own machine. These communications are what’s known as **command and control (C2)**, \*\*\*\*which are the techniques used by malicious actors to maintain communications with compromised systems.

### **Temporal patterns**

Network packets contain information relating to time. This information is useful in understanding time patterns. For example, a company operating in North America experiences bulk traffic flows between 9 a.m. to 5 p.m., which is the baseline of normal network activity. If large volumes of traffic are suddenly outside of the normal hours of network activity, then this is considered _off baseline_ and should be investigated.

Through network monitoring, organizations can promptly detect network intrusions and work to prevent them from happening by securing network components.

**security operations centers** (**SOC**) and their role in monitoring systems against security threats and attacks. Organizations may deploy a **network operations center** (**NOC**), which is an organizational unit that monitors the performance of a network and responds to any network disruption, such as a network outage. While a SOC is focused on maintaining the security of an organization through detection and response, a NOC is responsible for maintaining network performance, availability, and uptime.&#x20;

* If you would like to learn more about network components organizations can monitor, check out [network traffic - MITRE ATT\&CK®](https://attack.mitre.org/datasources/DS0029/)
* Attackers can leverage different techniques to exfiltrate data, should you like to learn more, check out [data exfiltration techniques - MITRE ATT\&CK®](https://attack.mitre.org/tactics/TA0010/)

**Data exfiltration attack**

Let's discuss how the detection and response process might work in a data exfiltration attack.

**Attacker's perspective**

* Gain initial access into a network and computer system
* Perform lateral movement to expand and maintain access to other systems on the network
* Identify valuable assets
* Collect, package, and prepare the data for exfiltration
* Exfiltrate the data to their destination of choice

**Organization's defense**

* Prevent attacker access (e.g., multi-factor authentication)
* Monitor network activity to identify suspicious activity
* Identify, classify, and protect assets using asset inventories and security controls
* Detect and stop the exfiltration (e.g., network monitoring, SIEM tools, firewall rules)

**Indicators of unusual data collection**

* Large internal file transfers
* Large external uploads
* Unexpected file writes

📖 The Internet Layer accepts and delivers packets for the network.

**Packet Capture**

Packet capture is the process of intercepting and recording network traffic. This can be done using a variety of tools, including packet sniffers. Packet captures can be used for a variety of purposes, including:

* **Network monitoring and analysis**
* **Incident investigation and response**
* **Security analysis**

**Packet Structure**

Packets have a specific structure, which includes:

* **Header:** Contains information such as the source and destination IP addresses, the type of packet, and the port numbers.
* **Payload:** Contains the actual data that is being transmitted.
* **Footer:** Signifies the end of the packet.

**IP Headers**

IP headers contain essential data fields for transmitting data to its intended destination. Different protocols use different headers. IPv4 is the most widely used version of the Internet Protocol.

**IPv4 Header Fields**

* **Version:** Specifies the version of IP being used (IPv4 or IPv6).
* **IHL:** Internet Header Length, specifies the length of the IP header plus any options.
* **ToS:** Type of Service, indicates if certain packets should be treated with different care.
* **Total Length:** Identifies the length of the entire packet, including headers and data.
* **Identification, Flags, and Fragment Offset:** Deals with information related to fragmentation.
* **TTL:** Time to Live, determines how long a packet can live before it gets dropped.
* **Protocol:** Specifies the protocol used by providing a value corresponding to a protocol (e.g., TCP is represented by 6).
* **Header Checksum:** Stores a value called a checksum, used to determine if any errors have occurred in the header.
* **Source Address:** Specifies the source IP address.
* **Destination Address:** Specifies the destination IP address.
* **Options:** Not required, commonly used for network troubleshooting.
* **Data:** The packet's data resides at the end of the packet header.

### **IPv6**

IPv6 adoption has been increasing because of its large address space. There are eight fields in the header:

* **Version**: This field indicates the IP version. For an IPv6 header, IPv6 is used.
* **Traffic Class**: This field is similar to the IPv4 Type of Service field. The Traffic Class field provides information about the packet's priority or class to help with packet delivery.
* **Flow Label**: This field identifies the packets of a flow. A flow is the sequence of packets sent from a specific source.
* **Payload Length**: This field specifies the length of the data portion of the packet.
* **Next Header**: This field indicates the type of header that follows the IPv6 header such as TCP.
* **Hop Limit**: This field is similar to the IPv4 Time to Live field. The Hop Limit limits how long a packet can travel in a network before being discarded.
* **Source Address**: This field specifies the source address of the sender.
* **Destination Address**: This field specifies the destination address of the receiver.

**Packet Analysis**

Packet analysis is the process of examining packet captures to identify patterns and trends. This can be done manually or using automated tools. Packet analysis can be used to:

* **Identify security threats**
* **Troubleshoot network problems**
* **Improve network performance**

**Packet Sniffers**

Packet sniffers are tools that are used to capture and analyze network traffic. There are a variety of packet sniffers available, both free and commercial. Some of the most popular packet sniffers include:

* **Wireshark**
* **tcpdump**
* **Snort**

### **How network protocol analyzers work**

Network protocol analyzers use both software and hardware capabilities to capture network traffic and display it for security analysts to examine and analyze. Here’s how:

1. First, packets must be collected from the network via the **Network Interface Card (NIC)**, which is hardware that connects computers to a network, like a router. NICs receive and transmit network traffic, but by default they only listen to network traffic that’s addressed to them. To capture all network traffic that is sent over the network, a NIC must be switched to a mode that has access to all visible network data packets. In wireless interfaces this is often referred to as monitoring mode, and in other systems it may be called promiscuous mode. This mode enables the NIC to have access to all visible network data packets, but it won’t help analysts access all packets across a network. A network protocol analyzer must be positioned in an appropriate network segment to access all traffic between different hosts.
2. The network protocol analyzer collects the network traffic in raw binary format. Binary format consists of 0s and 1s and is not as easy for humans to interpret. The network protocol analyzer takes the binary and converts it so that it’s displayed in a human-readable format, so analysts can easily read and understand the information.

**Packet sniffing** is the practice of capturing and inspecting data packets across a network. A **packet capture (p-cap)** is a file containing data packets intercepted from an interface or network. Packet captures can be viewed and further analyzed using network protocol analyzers. For example, you can filter packet captures to only display information that's most relevant to your investigation, such as packets sent from a specific IP address.

P-cap files can come in many formats depending on the packet capture library that’s used. Each format has different uses and network tools may use or support specific packet capture file formats by default. You should be familiar with the following libraries and formats:

1. **Libpcap** is a packet capture library designed to be used by Unix-like systems, like Linux and MacOS®. Tools like tcpdump use Libpcap as the default packet capture file format.
2. **WinPcap** is an open-source packet capture library designed for devices running Windows operating systems. It’s considered an older file format and isn’t predominantly used.
3. **Npcap** is a library \*\*\*\*designed by the port scanning tool Nmap that is commonly used in Windows operating systems.
4. **PCAPng** is a modern file format that can simultaneously capture packets and store data. Its ability to do both explains the “ng,” which stands for “next generation.”

**Packet crafting: a serious crime!**

Packet crafting is the art of creating a packet according to various requirements to carry out attacks and to exploit vulnerabilities in a network. It's mainly used to penetrate into a network's structure. There are various vulnerability assessment tools used to craft such packets. As a coin has two sides, these tools could be used by hackers to find the vulnerabilities of a targeted system. Crafting is technically advanced and a complex type of vulnerability exploitation, and it's difficult to detect and diagnose.

[Packet crafting: a serious crime! | Infosec](https://www.infosecinstitute.com/resources/hacking/packet-crafting-a-serious-crime/)

The following are the steps involved in packet crafting:

* **Packet Assembly:** This is the first step involved in packet crafting. In this process, the attacker selects the network to be cracked, collects the possible vulnerability information and creates the packet. The packet should be designed in such a way that it should be invisible while passing through a network. For example, for a packet to be invisible, the source address could be spoofed before sending it to a network.
* **Packet Editing:** In this step, the packets are tested before sending. The packets are edited in such a way that maximum information could be retrieved by injecting a minimum number of packets.
* **Packet Playing:** When the packets are ready, packet playing sends them to the targeted machine and collects the resultant packets for further analysis. If the required information is not obtained, the attacker again moves to the editing phase to modify the packet to obtain the required result.
* **Packet Analysis:** The sent packets are received by the attacker and they are analyzed to extract the information. Various sniffing tools like Wireshark, tcpdump, dsniff, etc. are used for this purpose. This step gives a route to the targeted system, or at least gives attackers enough data to tune up the attack.

**Tools For Packet Crafting:** Hping, Nemesis, Netcat, Scapy, Socat

**tcpdump**

Wireshark
