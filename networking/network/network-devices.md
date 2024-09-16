# Network Devices

WIFI

Routers

The computer would send information to the router, and the router would then transfer the information through the modem to the internet. The intended recipient's modem receives the information, and transfers it to the router. Finally, the recipient's router forwards that information to the destination device.

*   MODEM:

    Convert Digital Signals into analog/electrical signals and visa versa. Modems receive transmissions from the internet and translate them into digital signals that can be understood by the devices on the network.

    A modem is a device that connects your router to the internet, and brings internet access to the LAN.
* ETHERNAT CARD:
*   REPEATER:

    At physical layer

    2 port device

    When the signal becomes weak, they copy the signal bit by bit and regenerate it as original strength, in the same network.

    Do not amplify the signals
*   HUB:

    Multiport repeater. It Connects multiple wires.

    A hub is a network device that broadcasts information to every device on the network.

    Cannot filter data, so data packets are sent to all connected devices that is collision domain of all hosts connected through hub remians one. It doesn't have the ability to smartly manage data traffic.

    Now, because the hub doesn't know which device the data is intended for, all connected devices receive and hear the data packet that is collision doamins means that if two or more devices try to send data at the same time, their data packets can collide and interfere with each other, potentially leading to data corruption.

    In this scenario, all the devices connected to the hub share the same collision domain, just like cars navigating through a busy intersection. If one car enters the intersection without checking for other cars, a collision can happen. Similarly, if multiple devices send data simultaneously through a hub, a collision can occur, leading to data loss or errors.

    This is in contrast to switches, which create separate collision domains for each pair of connected devices. This helps reduce the chances of collisions and makes the network more efficient.

    ***
*   SWITCH:

    Multi Port bridge + buffer

    perform error checking before forwarding data.

    It divides collision domain of hosts but broadcast domain remians same.

    A switch makes connections between specific devices on a network by sending and receiving data between them. A switch is more intelligent than a hub. It only passes data to the intended destination. This makes switches more secure than hubs, and enables them to control the flow of traffic and improve network performance.
*   ROUTER:

    It routes the data packets based on their IP adrress.
*   GATEWAY:

    To connect two networks that may work upon diff networking models.

    Opperate on any network layer.

    Messenger agents—> Take data from one system, interpret it and transfer it to another system.
*   Brouter:

    Bridge + router

    At data link layer or network layer
* WIFI CARD:
*   Bridge:

    Opperates at data link layer

    Repeater + Filter content by reading MAC addresses of sourse and destination.

    1. Transparent Bridges:
    2. Source Routing Bridges:
*   **Wireless access point**

    A wireless access point uses radio waves to create a Wi-Fi network. Devices with wireless adapters connect to it, employing Wi-Fi standards for wireless communication. Data is sent via radio waves, routed through routers and switches to its destination.
*   Visualization Tools:

    ***

[Google Cloud Networking overview | Google Cloud Blog](https://cloud.google.com/blog/topics/developers-practitioners/google-cloud-networking-overview)

Switches
