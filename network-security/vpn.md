# VPN

* **VPN Functionality**:
  * **Privacy Enhancement**: It alters your public IP address and conceals your virtual location, safeguarding your data when using public networks like the internet.
  * **Confidentiality Preservation**: Encrypts your data during transmission, preventing unauthorized access and maintaining privacy.
  * **Encapsulation for Security**: Utilizes encapsulation, a process where sensitive data is wrapped within other data packets, ensuring that your information remains protected while retaining routing information necessary for successful delivery.
* **Encapsulation Process**:
  * **Data Protection**: Encrypts data packets to prevent deciphering, ensuring your information remains secure.
  * **Routing Information Preservation**: Wraps encrypted data within other data packets that routers can interpret, allowing network requests to reach their intended destinations.
  * **Balancing Privacy and Functionality**: Solves the dilemma of encrypting data while maintaining the ability for routers to read IP and MAC addresses, ensuring seamless internet connectivity while safeguarding privacy.
* **VPN Tunnel**:
  * **Secure Connection Establishment**: Forms an encrypted tunnel between your device and the VPN server, ensuring data security throughout transmission.
  * **Unhackable Encryption**: Utilizes encryption protocols that are virtually impenetrable without the appropriate cryptographic key, preventing unauthorized access to your data.
* **Combination with SD-WAN**:
  * **Enhanced Network Security**: Organizations adopt a combination of VPN and SD-WAN capabilities to bolster network security.
  * **SD-WAN Benefits**: Software-defined wide area network (SD-WAN) services provide a virtualized approach to connecting users and applications securely across multiple locations and over extensive geographical distances.
  * **Integrated Solution**: Integration of VPN and SD-WAN technologies offers a comprehensive solution for organizations seeking to enhance their network security posture while ensuring reliable connectivity.
*   **Remote access VPN**

    Individual users use remote access VPNs to establish a connection between a personal device and a VPN server. Remote access VPNs encrypt data sent or received through a personal device. The connection between the user and the remote access VPN is established through the internet.

    ***
*   **site-to-site VPNs**

    Enterprises use site-to-site VPNs largely to extend their network to other networks and locations. This is particularly useful for organizations that have many offices across the globe. IPSec is commonly used in site-to-site VPNs to create an encrypted tunnel between the primary network and the remote network. One disadvantage of site-to-site VPNs is how complex they can be to configure and manage compared to remote VPNs.

    ***

### VPN Protocols:

It’s a set of rules or instructions that will determine how data moves between endpoints.

*   **WireGuard VPN**

    WireGuard is a high-speed VPN protocol, with advanced encryption, to protect users when they are accessing the internet. It’s designed to be simple to set up and maintain. WireGuard can be used for both site-to-site connection and client-server connections. WireGuard is relatively newer than IPSec, and is used by many people due to the fact that its download speed is enhanced by using fewer lines of code. WireGuard is also open source, which makes it easier for users to deploy and debug. This protocol is useful for processes that require faster download speeds, such as streaming video content or downloading large files.

    ***
*   **IPSec VPN**

    IPSec is another VPN protocol that may be used to set up VPNs. Most VPN providers use IPSec to encrypt and authenticate data packets in order to establish secure, encrypted connections. Since IPSec is one of the earlier VPN protocols, many operating systems support IPSec from VPN providers.

    ***
