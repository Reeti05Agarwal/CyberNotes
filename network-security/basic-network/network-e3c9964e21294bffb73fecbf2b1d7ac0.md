# Network e3c9964e21294bffb73fecbf2b1d7ac0

## Network

Protocols

Network Devices

Digital Address

Networking Tools

Network Attacks

Status Codes

3 Media Types

[Packet Tracker](https://www.notion.so/Packet-Tracker-aba518e33a2a4a918ab0348f1cf309e1?pvs=21)

* ACRONYMS (NETWORK PROTOCOLS):
  1. POP:
  2. SMTP:
  3. VOIP:
  4. GMS:
  5. WLL:
  6. MBPS:
  7. WAN:
  8. COMA:
  9. FTP:
  10. PPP:
  11. WWW:
  12. XML:
  13. HTML:
  14. ASP:
  15. HTTP:
  16. TCP/IP:
  17. TELNET:
  18. ARPANET:
  19. URL:
  20. MODEM:
  21. WIFI:
  22. MAC ADDRESS:
  23. SMPP:

***

## BASICS

* **TYPES OF NETWORK:**
  *   PAN:

      Personel Area Networking
  *   LAN:

      Local Area Networking
  *   MAN:

      Metropolitan Area Networking
  *   WAN:

      Wide Area Networking

      1.  SONET: Sincronuse Optical Networking

          Transmit the data using optical fibre cables, hence it can carry larger distaces
      2.  Frame Relay:

          To connect local area network to wider area.
* **EVOLUTION OF NETWORK:**
  * ARPANET:
  * NSFNET:
  * INTERNET:
*   **TOPOLOGY:**

    *   Mesh

        * Every device has a dedicated point-to-point link to every other device.
        *   No of links with n number of nodes:

            $\[n(n-1)]/2$

            One node is connected to (n-1) nodes. There are n number of nodes. and the connected between the links is two and fro.
        * ADVANTAGES:
          1. Each connection can carry its own data load, thus eliminating the traffic problems that can occur when links must be shared by multiple devices.
          2. Robust. If one link becomes unusable, it does not incapacitate the entire system.
          3. Privacy and security
          4. Make fault identification and fault isolation easy.
        * DISADVANTAGES:
          1. amount of cabling and the number of I/O ports required. installation and reconnection are difficult
          2. Needs a huge sapce for wiring and stuff
          3. Expensive
        *   USES:

            A backbone connecting main comp of hybrid network that can include several other topologies.

        ***
    *   Star

        * Each device has a dedicated point-to-point link only to a central controller, usually called a hub.
        * The controller acts as an exchange: If one device wants to send data to another, it sends the data to the controller, which then relays the data to the other connected device
        * ADVANTAGES:
          1. Less expensive
          2. Easier to install and reconfigure
          3. less cabling, hence need less amount of space
          4. Robustness. If one link fails, only that link is affected. hence easier fault identification & fault isolation.
        * DISADVANTAGES:
          1. Dependency of whole topology on hub
          2. more cabling than other topologies.
        * USED:
          1. LAN

        ***
    * Bus
      * Multipoint
      * One long cable acts as a backbone to link all the devices in a network.
      * DROPLINE: connection running between the device and the main cable.
      * TAP: connector that either splices into the main cable or punctures the sheathing of a cable to create a contact with the metallic core.
      * ADVANTAGES:
        1. Ease of installation
        2. Most efficient path, less cabling
      * DISADVANTAGES:
        1. Diff reconnection
        2. Fault isolationSignal reflection at the taps can cause degradation in quality.
        3. In addition, a fault or break in the bus cable stops all transmission, even between devices on the same side of the problem. The damaged area reflects signals back in the direction of origin, creating noise in both directions
    *   Ring

        * Point-to-point with onlt 2 devices on either side of it.
        * A signal is passed along the ring in one direction, from device to device, until it reaches its destination. Each device in the ring incorporates a repeater. When a device receives a signal intended for another device, its repeater regenerates the bits and passes them along.
        * ADVANTAGE:
          1. Fault isolation: If one device does not receive a signal within a specified period, it can issue an alarm. The alarm alerts the network operator to the problem and its location.
          2. To add or delete a device requires changing only two connections.
        * DISADVANTAGE:
          1. A break in ring that disable the entire network. **The problem can be solved by using DUAL RING or a SWITCH capable of clossing off the break.**

        ***
    *   Hybrid

        Mix of multiple topologies.

    ***
*   **Three Way Handshake:**

    When a computer wants to extablish connection with another comp, it sends syn packets \[SYN] → **synchronize**, and when the recieving computer ecknowledge that syn packet \[SYN, ACK], and then the sender ack \[ACK], then a connection is formed between the computers.

***

* SWITCHING TECH:
  * CIRCUIT SWITCHING:
  * PACKET SWITCHING:
* TRANSMISSION MEDIA:
  * WIRED CM:
    1. TWISTED PAIR CABLE:
    2. CO-AXIAL CABLE:
    3. FIBRE-OPTIC CABLE:
  * WIRELESS CM:
    1. RADIO-WAVES:
    2. MICRO-WAVES:
    3. INFRARED WAVES:

***

* WEB SERVICES:
  * WWW:
  * HTML:
  * XML:
  * URL:
  * WEBSITE:
  * WEB BROWSER:
  * WEB SERVERS:
  * WEB HOSTING:

***

* How does the communication between two computers happen:
  *   Guided:

      A set of path is already defined.

      EG: Two computers are already connected by a wire.
  * Unguided:
*   COLLISION DOMAIN

    A collision domain is like a busy intersection where cars (data packets) from different streets (devices) meet. In computer networking, it's an area where devices share the same communication pathway and might interfere with each other.

    Imagine you have multiple devices connected to the same network segment, like a bunch of computers plugged into a hub. When two devices send data at the same time, there can be a "collision" where the signals interfere and the data becomes garbled. This is similar to cars colliding at an intersection.

    To avoid these collisions, Ethernet networks often use a method called CSMA/CD (Carrier Sense Multiple Access with Collision Detection). This method helps devices listen for ongoing data transmissions before sending their own data, reducing the chances of collisions.

    In more modern networks, like those using switches, the collision domain concept becomes less relevant because switches create separate paths for communication, reducing the chances of collisions and improving network efficiency.
*   SOCKETS:

    Where you need to send messages from one system to another.
*   SUBNETTING

    Subnetting is the term given to splitting up a network into smaller, miniature networks within itself.

    Network administrators use subnetting to categorise and assign specific parts of a network to reflect this.

    Subnetting is achieved by splitting up the number of hosts that can fit within the network, represented by a number called a subnet mask.

    Represented as a number of four bytes (32 bits), ranging from 0 to 255 (0-255).

    Subnets use IP addresses in three different ways:

    *   Identify the network address

        This address identifies the start of the actual network and is used to identify a network's existence.
    *   Identify the host address

        An IP address here is used to identify a device on the subnet
    *   Identify the default gateway

        The default gateway address is a special address assigned to a device on the network that is capable of sending information to another network. usually use either the first or last host address in a network (.1 or .254)

    ***
*   COOKIES

    Its a unique string stored in client browser.

    When you visit a website for the first time, the site sets a cookie on your device. When you make subsequent requests to the site, your request header includes this cookie. This helps the server identify your device and allows it to check its database to find the corresponding state or information related to your visit.
* ENCAPSULATIONTING
*   National Vulnerability Database (NVD) is

    US Govn repository of data regarding vulnerability standards
* Eyewitness tool
* Sublist3r tool
*   ASN Eagle tool

    A tool **to discover ASN of any host and fetch IP ranges**.

    ***
*   Which tool is used to enumerate website old content ?

    **Wayback Machine**
*   GitHub dorks

    github-dork.py is **a simple python tool that can search through your repository or your organization/user repositories**.
*   rooted device mean on Android?

    What does rooted device mean on Android?

    To root a device is **to obtain superuser access on an android device**.
*   What address is used as a physical identifier for a device on a network?

    MAC Address
*   What address is used as a logical identifier for a device on a network?

    IP Address
*   enumeration

    The action of mentioning a number of things one by one.
*   **Sender Policy Framework** (SPF)

    email authentication method that helps to identify the mail servers that are allowed to send email for a given domain. By using SPF, ISPs can identify email from spoofers, scammers and phishers as they try to send malicious email from a domain that belongs to a company or brand.
*   subdomain takeover

    **an attacker is able to seize control of an organization's subdomain via cloud services like AWS or Azure**.

    part of SMTP Configuration

### Network Analysis

Network traffic analysis is looking at network across various application and network layers and seeing what that traffic is doing, how we can secure that traffic, as well as identify any vulnerabilities and concerns.

Network performance can be measured by bandwidth.

Play video starting at :1:44 and follow transcript1:44

### Bandwidth

Bandwidth refers to the amount of data a device receives every second. Calculate by dividing the quantity of data by the time in seconds. Speed refers to the rate at which data packets are received or downloaded. Security personnel are interested in network bandwidth and speed because if either are irregular, it could be an indication of an attack.

| **Unit of Bandwidth** | **Abbreviation** | **Equivalence**                           |
| --------------------- | ---------------- | ----------------------------------------- |
| Bits per second       | bps              | 1 bps = fundamental unit of bandwidth     |
| Kilobits per second   | Kbps             | 1 Kbps = 1,000 bps = 103 bps              |
| Megabits per second   | Mbps             | 1 Mbps = 1,000,000 bps = 106 bps          |
| Gigabits per second   | Gbps             | 1 Gbps = 1,000,000,000 bps = 109 bps      |
| Terabits per second   | Tbps             | 1 Tbps = 1,000,000,000,000 bps = 1012 bps |

## Throughput

Like bandwidth, throughput is the measure of the transfer of bits across the media over a given period of time. However, due to a number of factors, throughput does not usually match the specified bandwidth. Many factors influence throughput including:

* The amount of data being sent and received over the connection
* The types of data being transmitted
* The latency created by the number of network devices encountered between source and destination

Latency refers to the amount of time, including delays, for data to travel from one given point to another.

Throughput measurements do not take into account the validity or usefulness of the bits being transmitted and received. Many messages received through the network are not destined for specific user applications. An example would be network control messages that regulate traffic and correct errors.

In an internetwork or network with multiple segments, throughput cannot be faster than the slowest link of the path from sending device to the receiving device. Even if all or most of the segments have high bandwidth, it will only take one segment in the path with lower bandwidth to create a slowdown of the throughput of the entire network.

### **Clients and Server:**

All computers connected to a network that participate directly in network communication are classified as hosts. Hosts can send and receive messages on the network. In modern networks, computer hosts can act as a client, a server, or both, as shown in the figure. The software installed on the computer determines which role the computer plays.

Servers are hosts that have software installed which enable them to provide information, like email or web pages, to other hosts on the network. Each service requires separate server software. For example, a host requires web server software in order to provide web services to the network. Every destination that you visit online is provided to you by a server located somewhere on a network that is connected to the global internet.

Clients are computer hosts that have software installed that enables the hosts to request and display the information obtained from the server. An example of client software is a web browser, such as Internet Explorer, Safari, Mozilla Firefox, or Chrome.

## Peer-to-Peer Networks

Client and server software usually run on separate computers, but it is also possible for one computer to run both client and server software at the same time. In small businesses and homes, many computers function as the servers and clients on the network. This type of network is called a peer-to-peer (P2P) network.

The simplest P2P network consists of two directly connected computers using either a wired or wireless connection. Both computers are then able to use this simple network to exchange data and services with each other, acting as either a client or a server as necessary.

Multiple PCs can also be connected to create a larger P2P network, but this requires a network device, such as a switch, to interconnect the computers.

The main disadvantage of a P2P environment is that the performance of a host can be slowed down if it is acting as both a client and a server at the same time. The figure lists some of the advantages and disadvantages of peer-to-peer networks.

## Network Topologies and Representations

In a simple network consisting of a few computers, it is easy for you to visualize how all of the various components connect. As networks grow, it becomes more difficult to keep track of the location of each component, and how each is connected to the network. Wired networks require lots of cabling and network devices to provide connectivity for all network hosts. A diagram provides an easy way to understand how the devices in a large network are connected.

When networks are installed, a physical topology diagram is created to record where each host is located and how it is connected to the network. The physical topology diagram also shows where the wiring is installed and the locations of the networking devices that connect the hosts. Such a diagram uses symbols or icons to represent the different devices and connections that make up a network. The figure illustrates some of the icons used to represent network components on diagrams.

Image shows symbols used in network diagrams. At the top are the following end devices: desktop computer, laptop, printer, IP phone, wireless tablet, and TelePresence endpoint. In the middle are the following intermediary devices: wireless router, LAN switch, router, multilayer switch, and firewall appliance. At the bottom are the following network media: blue waves depicting wireless media, a solid black line depicting LAN media, and a red lighting bolt depicting WAN media.

#### Typical Home Network Routers

Home and small business routers typically feature two primary types of ports to manage network connections:

1. **Ethernet Ports**
   * **Description:** These ports connect to the internal switch portion of the router and are usually labeled “Ethernet” or “LAN.”
   * **Function:** All devices connected to these ports are on the same local network.
   * **Use Case:** Connecting devices such as desktop PCs, smart TVs, and gaming consoles directly to the router for a stable and high-speed wired connection.
2.  **Internet Port**

    * **Description:** This port is used to connect the router to another network, often labeled as “Internet” or “WAN.”
    * **Function:** Connects the router to an external network, typically via a cable or DSL modem, to access the internet.
    * **Use Case:** Establishing a connection between the home network and the internet service provided by an ISP (Internet Service Provider).

    ## LAN Wireless Frequencies

    #### **Wired Network Technologies**

    **Despite the prevalence of wireless communications in home networks, certain applications benefit from wired connections due to their reliability, speed, and dedicated bandwidth. The most commonly used wired protocol in these networks is Ethernet.**

    #### **Ethernet Protocol**

    * **Function: Enables network devices to communicate over a wired LAN connection.**
    * **Flexibility: Can connect devices using various types of wiring media.**

    #### **Ethernet Patch Cable**

    * **Description: A direct connection medium, typically unshielded twisted-pair (UTP) cables.**
    * **Connectors: Equipped with RJ-45 connectors, available in various lengths.**
    * **Installation: Some modern homes have pre-installed Ethernet jacks for easy connectivity.**

    #### **Alternative Wiring Technologies**

    **For homes lacking UTP wiring, technologies like powerline networking can extend wired connectivity throughout the premises by utilizing existing electrical wiring.**

    #### **Common Wiring Media**

    1. **Category 5e (Cat 5e) Cable**
       * **Description:** The most common wiring used in LANs.
       * **Structure:** Composed of 4 pairs of wires twisted together to reduce electrical interference.
       * **Usage:** Ideal for most household and small business applications due to its balance of performance and cost.
    2. **Coaxial Cable**
       * **Description:** Features an inner wire surrounded by a tubular insulating layer and a conducting shield, with an external insulating sheath.
       * **Structure:**
         * **Inner Conductor:** Carries the signal.
         * **Insulating Layer:** Prevents signal loss and interference.
         * **Conducting Shield:** Protects against electromagnetic interference (EMI).
       * **Usage:** Commonly used for cable television and internet connections.
    3. **Fiber-Optic Cable**
       * **Description:** Made of glass or plastic fibers about the diameter of a human hair.
       * **Function:** Carries digital information at very high speeds over long distances.
       * **Bandwidth:** Very high, capable of transmitting large amounts of data efficiently.
       * **Usage:** Suitable for high-speed internet connections and data transmission over long distances.
