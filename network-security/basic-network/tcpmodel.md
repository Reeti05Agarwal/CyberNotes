# TCPModel

TCP Model

## TCP Model

\*\*Transmission Control Protocol / Internet Protocol \*\*

* More Used practically
* connection-based protocol
* three-way handshake

### 5 Layers:

#### Application

```
User Interface.

The application layer in the TCP/IP model is similar to the application, presentation, and session layers of the OSI model.
- responsible for making network requests or responding to requests.
- defines which internet services and applications any user can access.
- Protocols in the application layer determine how the data packets will interact with receiving devices. Some common protocols used on this layer are:

    - Hypertext transfer protocol (HTTP)
    - Simple mail transfer protocol (SMTP)
    - Secure shell (SSH)
    - File transfer protocol (FTP)
    - Domain name system (DNS)
```

#### Transport

```
Delivery of a message from a process (running program) to another process.

Three Protocols:

- ***Transmission Control Protocol (TCP)***
- ***User Datagram Protocol (UDP)***

    It is a process-to-process protocol that adds only port addresses, checksum
    error control, and length information to the data from the upper layer.

- ***Stream Control Transmission Protocol (SCTP)***

---
```

#### Network/**Internet layer**

```
responsible for ensuring the delivery to the destination host, which potentially resides on a different network. It ensures IP addresses are attached to data packets to indicate the location of the sender and receiver. The internet layer also determines which protocol is responsible for delivering the data packets and ensures the delivery to the destination host. Here are some of the common protocols that operate at the internet layer:

- **Internet Protocol (IP)**. IP sends the data packets to the correct destination and relies on the Transmission Control Protocol/User Datagram Protocol (TCP/UDP) to deliver them to the corresponding service. IP packets allow communication between two networks. They are routed from the sending network to the receiving network. The TCP/UDP retransmits any data that is lost or corrupt.
In the internet layer of the TCP/IP model, the IP formats data packets into IP datagrams. The information provided in the datagram of an IP packet can provide security analysts with insight into suspicious data packets in transit.
- **Internet Control Message Protocol (ICMP)**. The ICMP shares error information and status updates of data packets. This is useful for detecting and troubleshooting network errors. The ICMP reports information about packets that were dropped or that disappeared in transit, issues with network connectivity, and packets redirected to other routers.
```

#### Data Link/**Network access layer**

```
Deals with creation of data packets and their transmission across a network. This includes hardware devices connected to physical cables and switches that direct data to its destination.

One Protocol:

- Internetworking Protocol (IP)
    - It is an unreliable and connectionless protocol-a best-effort delivery service.
    - Host-to-host
    - IP transports data in packets called datagrams, each of which is transported separately. Datagrams can travel along different routes and can arrive out of sequence or be duplicated. IP does not keep track of the routes and has no facility for reordering datagrams once they arrive at their destination.
    - ***Four Protocols:***
        1. ***Address Resolution Protocol (ARP)***

            associate a logical address with a
            physical address.

        2. ***Reverse Address Resolution Protocol (RARP)***

            allows a host to discover its Internet address when it knows only its physical address.

        3. ***Internet Control Message Protocol (ICMP)***

            used by hosts and gateways to send notification of datagram problems back to the sender.

        4. ***Internet Group Message Protocol (IGMP)***

            used to facilitate the simultaneous
            transmission of a message to group of recipients.
```

#### Physical

```
does not define any specific protocol. It supports all the standard and proprietary protocols.
```

### Comparison:

![image](https://github.com/user-attachments/assets/e9a6dbff-344c-4ab9-8aaa-674426f7ac00)

![image](https://github.com/user-attachments/assets/f9645741-de2a-4e2f-9ce3-bdf3742807a7)
