# protocols

Protocols

## Protocols

### NAT (Network Address Translation)

Devices in a local network use private IPs for internal communication but need a public IP to access the internet. Network Address Translation (NAT) on the router swaps private IPs with its public IP, allowing internet access. NAT operates at TCP/IP layers 2 and 3.

### TCP

Transmission Control Protocol

* connection-based protocol
* three-way handshake
* High reliability data transfer over speed

**TCP Flag codes include:**

**Flags \[S]**  - Connection **S**tart **Flags \[F]**  - Connection **F**inish **Flags \[P]**  - Data **P**ush **Flags \[R]**  - Connection **R**eset **Flags \[.]**  - Acknowledgment

### UDP

User Datagram Protocol

* Connectionless Protocol
* fast Connection as data send over is not tracked extensively
* video streaming

### HTTP

Hypertext Transfer Protocol

* Client-Server Protocol
* method of communication between clients and website servers.
* Application Layer
* Stateless Protocol {server will not store client info by default}

#### Methods

1. GET
2. POST
3. PUT
4. DELETE

> Port: 80

> Port: 8080

### HTTPS {secured}

Hypertext Transfer Protocol Secure

* Secured version of HTTP
* uses secure sockets layer/transport layer security (SSL/TLS) encryption on all transmissions

> Port: 443

### FTP

File Transfer Protocol

```bash
ftp ip_address
```

> Port: 20 udp Port: 21 tcp

### Telnet

* To connect remotely to host device
* Application Layer
* Not as secured as SSH

```bash
telnet host_name
```

> Port: 23

### DNS

Domain Name System

Domain Name -> IP Address

* It sends Domain name and web address to DNS Server. It then retrieves IP address of that website.
* Application Layer

> Port: 53 udp if the DNS reply to a request is large, it will switch to using the TCP protocol

### SMTP

Simple Mail Transfer Protocol

* Send the email
* Transmit and route email from sender to recipient's address.
* It works with Message Transfer Protocol (MTA) software, which searched DNS servers to resolve email addresses to IP addresses.

> Port:25 uses TCP/UDP for unencrypted emails Used by high volume spam

> Port: 587 uses TCP/UDP using TLS for encrypted emails

### POP3

Post Office Protocol

* Manage and retrieve email from email server.
* User devices will send requests to the remote mail server and download email messages locally. If you have ever refreshed your email application and had new emails populate in your inbox, you are experiencing POP and internet message access protocol (IMAP) in action.
* When using POP, mail has to finish downloading on a local device before it can be read and it does not allow a user to sync emails.
* Application Layer

> Port: 110 Unencrypted, plaintext authentication

> Port:995 Encrypted emails over SSL/TLS {Secured Sockets Layer/ Transport Layer Security}

### IMAC

Internet Message Access Protocol

* Used for incoming email
* Downloads the header but not the content {which remains on email server}, which allows users to access their email from multiple devices
* allows users to partially read email before it is finished downloading and to sync emails.
* Slower than POP3

> Port:143 unencrypted email

> Port:993 TLS Protocol

### DHCP

Dynamic Host Configuration Protocol

* Allocate unique IP address to the device connected to your network. Also assign default gateway
* When device is connected to network, it sends a DHCP Discover request to see if DHCP servers are on the network
* Application Layer

#### FOUR way handshake

```
1. DHCP Discover {client -> server}
2. DHCP Offer {server (free ip_address) -> client}
3. DHCP Request {client (yes, i want that ip)-> server}
4. DHCP ACK {server (ok, use it for 2 hours) -> client}
```

> Port: 67 udp, servers Port: 68 tcp, clients

### SSH

Secure Shell

* Create secure connection with remote system
* Application Layer
* Alternative for secure authentication & encrypted communication
* Replacement of less secure protocol: telnet
* Uses AES and other types of encryption

> Port: 22 tcp

### ICMP

Internet Control Message Protocol

* Management Protocol
* used by devices to tell each other about data transmission errors across the network
* used as a quick way to troubleshoot network connectivity and latency by issuing the “ping” command on a Linux operating system
* Internet Layer {TCP/IP Model}

### SNMP

Simple Network Management Protocol

* Management Protocol
* Monitoring and managing the devices on network
* can change password and baseline configuration of a device connected to the network
* give logs on bandwidth usage
* Application Layer

### SFTP

Secure File Transfer Protocol

* Security Protocol Uses SSH to transfer files from one device to another over a network
* Application Layer
* used often with cloud storage. Every time a user uploads or downloads a file from cloud storage, the file is transferred using the SFTP protocol.

### ARP

Address Resolution Protocol

* Security Protocol
* Allows devices to identify themselves on network
