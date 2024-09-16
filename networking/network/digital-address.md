# Digital Address

## Digital Address

IP

MAC

Port Number

* DOMAIN NAMES:
* DOMAIN NAME RESOLUTION:
* **Communication Requirement**: Both MAC (physical) and IP (logical) addresses are necessary for communication on a hierarchical network, analogous to needing both a person's name and address to send a letter.
* **Hierarchical Design in Networking**:
  * Groups devices into multiple networks using a layered approach.
  * Keeps local traffic within local networks.
  * Only routes traffic to higher layers if destined for other networks.
* **Benefits**:
  * **Increased Efficiency**: Optimizes network functions.
  * **Improved Performance**: Enhances network speed.
  * **Scalability**: Allows easy addition of new local networks without affecting existing ones.
* **Three Basic Layers**:
  * **Access Layer**: Connects hosts in a local Ethernet network.
  * **Distribution Layer**: Interconnects smaller local networks.
  * **Core Layer**: Provides high-speed connections between distribution layer devices.
* **Logical Addressing**:
  * Necessary to identify host locations.
  * Common schemes: IPv4 (currently predominant) and IPv6 (being implemented as a replacement).
  * Both IPv4 and IPv6 will coexist for the foreseeable future.
  * "IP" refers to both IPv4 and IPv6.

## **Access Layer**

* **Access Layer**:
  * Provides connection points for end-user devices to the network.
  * Allows multiple hosts to connect via network devices (e.g., switches like Cisco 2960-XR, or wireless access points).
  * All devices within the same access layer share the same network portion of the IP address.
* **Local vs. Remote Traffic**:
  * Messages destined for local hosts stay within the access layer.
  * Messages destined for different networks are passed to the distribution layer.
*   **Connections**:

    * Switches connect to distribution layer devices (e.g., Layer 3 routers or Layer 3 switches).



#### Ethernet Hub

* **Original Ethernet Networks**:
  * Initially connected all hosts with a single cable, sharing bandwidth.
* **Ethernet Hubs**:
  * Developed to simplify connecting and reconnecting multiple devices.
  * Contain multiple ports to connect hosts.
  * Lack electronics to decode messages, merely repeat signals to all ports.
* **Message Handling**:
  * Broadcasts incoming messages to all ports.
  * All hosts share the bandwidth and receive the message.
  * Only the host with the matching destination address processes the message.
* **Collisions**:
  * Only one message can be sent at a time.
  * Simultaneous transmissions by multiple hosts cause collisions.
  * Collisions result in unreadable messages, requiring retransmission.
  * The area where collisions can occur is called a collision domain.
* **Obsolescence**:
  * Hubs cause network congestion due to collisions and retransmissions.
  * Replaced by Ethernet switches, which are more efficient.

#### **Ethernet Switches**:

* Used at the access layer to connect hosts.
* Decodes frames to read the physical (MAC) address portion of the message.
* **MAC Address Table**:
  * Contains a list of active ports and attached host MAC addresses.
  * Checks the table to find the destination MAC address when a message is sent.
  * **Unknown MAC Address Handling**:
    * When a switch receives a frame for a MAC address not in its table, it uses **flooding**.
    * Flooding sends the message to all attached hosts except the sender.
    * Each host checks the destination MAC address; only the correct host processes the message and responds.
  * **Building the MAC Address Table**:
    * The switch learns MAC addresses by examining the source MAC address of each frame.
    * When a new host sends or responds to a message, the switch records its MAC address and connected port.
    * The MAC address table is dynamically updated with new source MAC addresses.
    * This process allows the switch to quickly learn and store the MAC addresses of all connected hosts.
* **Circuit Creation**:
  * Builds a temporary connection (circuit) between source and destination ports.
  * Provides a dedicated communication channel for the two hosts.
* **Bandwidth and Collisions**:
  * Other hosts do not share bandwidth on the dedicated channel.
  * Separate circuits for each conversation prevent collisions.
  * Supports simultaneous sending and receiving of frames over the same Ethernet cable.
* **Performance Improvement**:
  * Eliminates collisions, enhancing network performance.

***

Here are the summarized points:

* **Ethernet Broadcasts**:
  * Used for sending messages to all hosts on the local network simultaneously.
  * Useful when a host needs information from any host or wants to share information with all hosts.
* **Broadcast Mechanism**:
  * A message can only have one destination MAC address.
  * Broadcast messages use a unique MAC address recognized by all hosts: FFFF.FFFF.FFFF (a 48-bit address of all ones).
* **Broadcast Address**:
  * The broadcast MAC address in binary is all ones.
  * Represented in hexadecimal notation as FFFF.FFFF.FFFF.
  * Each 'F' in hexadecimal represents four ones in binary.

## Broadcast Domains

When a host receives a message addressed to the broadcast address, it accepts and processes the message as though the message was addressed directly to it. When a host sends a broadcast message, switches forward the message to every connected host within the same local network. For this reason, a local area network, a network with one or more Ethernet switches, is also referred to as a broadcast domain.

If too many hosts are connected to the same broadcast domain, broadcast traffic can become excessive. The number of hosts and the amount of network traffic that can be supported on the local network is limited by the capabilities of the switches used to connect them. As the network grows and more hosts are added, network traffic, including broadcast traffic, increases. To improve performance, it is often necessary to divide one local network into multiple networks, or broadcast domains, as shown in the figure. Routers are used to divide the network into multiple broadcast domains.

## **Distribution Layer**:

* Connects separate networks and manages information flow between them.
* Contains more powerful switches (e.g., Cisco C9300 series) and routers for inter-network routing.
* Controls traffic type and amount between the access layer and core layer.

## **Core Layer**:

* Functions as a high-speed backbone layer with redundant connections.
* Transports large amounts of data between multiple end networks.
* Utilizes very powerful, high-speed switches and routers (e.g., Cisco Catalyst 9600).
* Main goal is to ensure fast data transport.
* **Frame Acceptance**:
  * A NIC accepts a frame if the destination address is the broadcast MAC address or matches the NIC's MAC address.
* **Logical vs. Physical Addresses**:
  * Network applications rely on logical IP addresses for identifying servers and clients.
  * The challenge arises when a sending host only knows the destination IP address and not the MAC address.
* **Address Resolution**:
  * IPv4 uses the Address Resolution Protocol (ARP) to discover the MAC address of any host on the same local network.
  * IPv6 uses a similar method called Neighbor Discovery.
* **Example Network**:
  * Hosts connected to a switch with the following IP addresses:
    * Host 1: 192.168.1.5
    * Host 2: 192.168.1.6
    * Host 3: 192.168.1.8
    * Host 4: 192.168.1.7
  * Host 1 needs to send information to 192.168.1.7 but only knows the IP address, not the MAC address.
* **Solution**:
  * Host 1 uses ARP to find the MAC address associated with IP address 192.168.1.7.
* **ARP Process**:
  * **Step 1**: The sending host creates a frame addressed to the broadcast MAC address. The frame contains a message with the IPv4 address of the destination host.
  * **Step 2**: Each host on the network receives the broadcast frame and compares the IPv4 address inside the message with its own IPv4 address. The host with the matching address sends its MAC address back to the original sender.
  * **Step 3**: The sending host receives the response and stores the MAC and IPv4 address information in an ARP table.
* **ARP Table**:
  * Stores the MAC address and IPv4 address mapping.
  * Allows the sending host to send frames directly to the destination host without further ARP requests.
* **Broadcast Domain**:
  * ARP messages use broadcast frames, so all hosts must be in the same broadcast domain for ARP to function properly.
* **Broadcast Containment**:
  * Routers in the distribution layer limit broadcasts to the local network where they are needed.
  * This helps control excessive broadcast traffic, which can slow down the network.
* **Broadcast Management**:
  * Broadcasts are necessary for network functions, but excessive broadcasts from too many hosts on the same local network can degrade performance.
  * Routers help manage and contain broadcast traffic, maintaining network efficiency.

**Security**

Routers in the distribution layer can separate and protect certain groups of computers where confidential information resides. Routers can also hide the addresses of internal computers from the outside world to help prevent attacks, and control who can get into or out of the local network.

**Locations**

Routers in the distribution layer can be used to interconnect local networks at various locations of an organization that are geographically separated.

**Logical Grouping**

Routers in the distribution layer can be used to logically group users, such as departments within a company, who have common needs or for access to resources.

* **Routing Necessity**:
  * Devices often need to connect beyond the local network to remote hosts (e.g., other homes, businesses, the internet).
  * Routing is needed to send packets to remote destinations by identifying the best path.
* **Router Functionality**:
  * Routers connect multiple Layer 3, IP networks.
  * At the distribution layer, routers direct traffic and perform critical network operations.
  * Routers read and decode messages, making forwarding decisions based on Layer 3 IP addresses, unlike switches that use Layer 2 MAC addresses.
* **Packet Handling**:
  * The packet format includes destination and source IP addresses and message data.
  * Routers use the network portion of the destination IP address to find the best path to forward the message.
*   **Routing Process**:

    * When source and destination IP network portions don't match, a router forwards the message.
    * Example: A host on network 1.1.1.0 sends a message to a host on network 5.5.5.0.
    * The router de-encapsulates the Ethernet frame, reads the destination IP address, determines the forwarding path, re-encapsulates the packet, and forwards it to the destination.

    Here are the summarized points:

    * **Path Selection**:
      * **Router Interfaces**: Each interface on a router connects to a different local network.
      * **Routing Table**: Contains information about locally connected networks and paths to remote networks.
      * **Frame Decoding**: Router decodes the received frame to access the destination IP address in the packet.
    * **Routing Process**:
      * **Table Matching**: Router matches the destination IP network portion with networks in the routing table.
      * **Frame Encapsulation**: If the destination network is found in the table, the router encapsulates the packet in a new frame.
      * **New Frame Details**: Inserts a new destination MAC address and recalculates the FCS field.
      * **Forwarding**: The new frame is forwarded out of the corresponding interface to the destination network.
      * **Routing**: The overall process of forwarding packets to their destination network.
    * **Broadcast Control**:
      * Router interfaces do not forward messages addressed to the local network broadcast IP address, preventing local network broadcasts from crossing into other networks.

    Here are the summarized points:

    * **Packet Forwarding**:
      * **Forwarding Destinations**:
        * Directly connected network with the destination host.
        * Another router on the path to the destination host.
    * **Encapsulation Requirements**:
      * **Ethernet Interface**: The router must include a destination MAC address in the frame.
        * **Destination Host on Local Network**: Uses the MAC address of the destination host.
        * **Another Router**: Uses the MAC address of the connected router.
    * **MAC Address Acquisition**:
      * **ARP Tables**: Routers obtain MAC addresses from ARP tables.
        * Each router interface maintains its own ARP table for the local network it is attached to.
        * ARP tables contain MAC addresses and IPv4 addresses of all hosts on that network.

    Here are the summarized points:

    * **Routing Table Entries**:
      * **Function**: Routers use routing tables to store network addresses and the best path to those networks, not individual host addresses.
      * **Update Methods**:
        * Dynamically by information from other routers.
        * Manually by a network administrator.
    * **Routing Decision**:
      * **Forwarding**: Routers use the routing table to decide which interface to use to forward messages to their destinations.
      * **Default Route**: Configured by administrators to handle unknown destination IP network addresses, preventing packet drops by forwarding them to another router.
    * **Example Network Setup**:
      * Hosts with IP addresses in the 10.1.21.0/8 and 172.16.0.0/16 networks connected to switches and a router.
      * Routing table entries:
        * Network 10.0.0.0/8 via Fast Ethernet 0/0.
        * Network 172.16.0.0/16 via Fast Ethernet 0/1.
      * **Type**: 'C' indicates directly connected networks.

    #### Summary of "The Default Gateway"

    * **Local Network Communication**:
      * Hosts send messages directly to other hosts on the same network.
      * Uses ARP to discover the destination host's MAC address.
      * IPv4 packet contains destination IP and frame contains destination MAC.
    * **Remote Network Communication**:
      * Hosts must use a router to send messages to a different network.
      * Packet still contains the destination IP address.
      * Frame uses the router's MAC address as the destination.
    * **Default Gateway**:
      * Hosts obtain the router's MAC address using ARP, directed by the default gateway IP configured in TCP/IP settings.
      * The default gateway is the router interface connected to the local network.
      * All hosts use this default gateway to send messages to remote networks.
    * **Importance of Proper Configuration**:
      * Correct default gateway configuration is crucial for proper message delivery to remote networks.
      * Incorrect or missing default gateway configuration prevents communication with remote networks.
