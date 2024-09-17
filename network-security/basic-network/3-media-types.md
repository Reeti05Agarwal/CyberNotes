# 3 Media Types

## 3 Media Types

Modern networks primarily use three types of media to interconnect devices, as shown in the figure:

* **Metal wires within cables** - Data is encoded into electrical impulses.
* **Glass or plastic fibers within cables (fiber-optic cable)** - Data is encoded into pulses of light.
* **Wireless transmission** - Data is encoded via modulation of specific frequencies of electromagnetic waves.

**Twisted-Pair Cable**

Ethernet technology generally uses twisted-pair cables to interconnect devices. Because Ethernet is the foundation for most local networks, twisted-pair is the most commonly encountered type of network cabling.

In twisted-pair, wires are grouped in pairs and twisted together to reduce interference. The pairs of wires are colored so that you can identify the same wire at each end. Typically, in each pair, one of the wires is a solid color and its partner is the same color striped onto a white background.

**Coaxial Cable**

Coaxial was one of the earliest types of network cabling developed. Coaxial cable is the kind of copper cable used by cable TV companies. It is also used for connecting the various components which make up satellite communication systems. Coaxial cable has a single rigid copper core that conducts the signal. This core is typically surrounded by a layer of insulation, braided metal shielding, and a protective jacket. It is used as a high-frequency transmission line to carry high-frequency or broadband signals.

**Fiber-Optic Cable**

Fiber-optic cable can be either glass or plastic with a diameter about the same as a human hair and it can carry digital information at very high speeds over long distances. Because light is used instead of electricity, electrical interference does not affect the signal. Fiber-optic cables have many uses as well as communications. They are also used in medical imaging, medical treatment, and mechanical engineering inspection.

They have a very high bandwidth, which enables them to carry very large amounts of data. Fiber is used in backbone networks, large enterprise environments, and large data centers. It is also used extensively by telephone companies.

## Ethernet Cabling

Here are the summarized points:

* **Common Usage**: Twisted-pair copper cable is widely used in homes and schools.
* **Cost and Availability**: Inexpensive and readily available.
* **Example**: Ethernet patch cables.
* **Construction**: Consists of insulated copper wire pairs twisted together in a protective jacket.
* **Data Transmission**: Uses electrical pulses to transmit data.
* **Interference Sensitivity**: Susceptible to electromagnetic interference (EMI) from devices like microwaves and fluorescent lights.
* **Crosstalk**: Interference from adjacent cables, especially when cables are improperly installed or terminated.
* **Impact of Interference**: Can reduce data throughput and require retransmission, degrading data capacity.

There are two commonly installed types of twisted-pair cable:

*   **Unshielded twisted-pair (UTP)** - This is the most commonly encountered type of network cable in North America and many other areas.

    UTP cable is inexpensive, offers a high bandwidth, and is easy to install. This type of cable is used to connect workstations, hosts and network devices. It can come with many different numbers of pairs inside the jacket, but the most common number of pairs is four. Each pair is identified by a specific color code.
*   **Shielded cables (STP**) - These are used almost exclusively in European countries.

    There are electrical environments in which EMI and RFI are so strong that shielding is a requirement to make communication possible, such as in a factory. In this instance, it may be necessary to use a cable that contains shielding, such as shielded twisted-pair (STP). Unfortunately, STP cables are very expensive, not as flexible, and have additional requirements because of the shielding that make them difficult to work with.

## RJ-11 and RJ-45 Connectors

All categories of data grade UTP cable are traditionally terminated into an **RJ-45** connector. There are still some applications that require the smaller **RJ-11** connector, such as analog phones and some fax machines. In the figure below, an example of an RJ-11 connector is on the left. The RJ-45 connector is on the right.

![https://contenthub.netacad.com/courses/netess/2f319cc5-e0e3-11ea-a9e5-a13ba5e257a4/ce2d6320-e3dd-11ea-a2cf-05cabc561422/assets/f2f1d100-fc3d-11ea-ba1f-67cdae3a6c51.jpg](https://contenthub.netacad.com/courses/netess/2f319cc5-e0e3-11ea-a9e5-a13ba5e257a4/ce2d6320-e3dd-11ea-a2cf-05cabc561422/assets/f2f1d100-fc3d-11ea-ba1f-67cdae3a6c51.jpg)

Cable TV and Satellite Cables:

Here are the summarized points:

* **Data Transmission**: Coaxial cable (coax) carries data as electrical signals, similar to twisted-pair.
* **Improved Shielding**: Provides better shielding and higher data capacity than unshielded twisted pair (UTP).
* **Construction**: Typically made of copper or aluminum.
* **Uses**:
  * Used by cable TV companies for service delivery.
  * Connects components in satellite communication systems.
  * Common in home setups for connecting TV sets to signal sources (cable TV, satellite TV, or antennas).
  * With a cable modem, supports data, internet, TV, and telephone services.
*   **Comparison with Twisted-Pair**:

    * Coax has superior data carrying capabilities.
    * Twisted-pair has replaced coax in local area networks (LANs).
    * Coax is more difficult to install, more expensive, and harder to troubleshoot than UTP.

    ## Fiber-Optic Cables

    Unlike UTP and coax, fiber-optic cables transmit data using pulses of light. Although not normally found in home or small business environments, fiber-optic cabling is widely used in enterprise environments and large data centers.

    Fiber-optic cable is constructed of either glass or plastic, neither of which conducts electricity. This means that it is immune to EMI and RFI, and is suitable for installation in environments where interference is a problem. Fiber connections are a good choice to extend networks from one building to another, both because of distance considerations and because fiber cables are more resistant to outdoor environmental conditions than copper cables. Each fiber-optic circuit is actually two fiber cables. One is used to transmit data; the other is used to receive data.

    The figure shows the structure of a fiber-optic cable.

    The image shows the construction of a fiber-optic cable. A cut-away of the cable reveals its layers, much like those of a tree. Each layer is named. This description will go from the outside of the cable to the center. Jacket, strengthening material, buffer, cladding, core. At the bottom is a graphic of a fiber optic cable with each of the layers exposed.

    ![https://contenthub.netacad.com/courses/netess/2f319cc5-e0e3-11ea-a9e5-a13ba5e257a4/d3849320-e3dd-11ea-a2cf-05cabc561422/assets/ddffe010-eeb0-11ea-ad44-67ee2be1a3a8.png](https://contenthub.netacad.com/courses/netess/2f319cc5-e0e3-11ea-a9e5-a13ba5e257a4/d3849320-e3dd-11ea-a2cf-05cabc561422/assets/ddffe010-eeb0-11ea-ad44-67ee2be1a3a8.png)

    JacketStrengthening MaterialBufferCladdingCore

    In the figure above, the parts of a fiber-optic cable are as follows:

    * **Jacket** - Typically a PVC jacket that protects the fiber against abrasion, moisture, and other contaminants. This outer jacket composition can vary depending on the cable usage.
    * **Strengthening Material** - Surrounds the buffer, prevents the fiber cable from being stretched when it is being pulled. The material used is often the same material used to produce bulletproof vests.
    * **Buffer** - Used to help shield the core and cladding from damage.
    * **Cladding** - Made from slightly different chemicals than those used to create the core. It tends to act like a mirror by reflecting light back into the core of the fiber. This keeps light in the core as it travels down the fiber.
    * **Core** - The core is actually the light transmission element at the center of the optical fiber. This core is typically silica or glass. Light pulses travel through the fiber core.

    Fiber-optic cables can reach distances of several miles or kilometers before the signal needs to be regenerated. Either lasers or light emitting diodes (LEDs) generate the light pulses that are used to represent the transmitted data as bits on the media. In addition to its resistance to EMI, fiber-optic cables support a large amount of bandwidth, making them ideally suited for high-speed data networks. Bandwidth on fiber-optic links can reach speeds of 100 Gbps and is continually increasing as standards are developed and adopted. Fiber-optic links are found in many corporations and are also used to connect ISPs on the internet.

    ## Twisted-Pair Operation

    ## Twisted-Pair Wiring Schemes

    Have you ever looked closely at the plastic RJ-45 connector at the end of an Ethernet patch cable? Did you ever wonder why each of the wires terminating in the connector has a specific color or pattern? The color coding of the wire pairs in an UTP cable is determined by the type of standard that is used to make the cable. Different standards have different purposes and are closely governed by the standards organizations.

    For typical Ethernet installations, there are two standards that are widely implemented. The TIA/EIA organization defines two different patterns, or wiring schemes, called T568A and T568B, as shown in the figure. Each wiring scheme defines the pinout, or order of wire connections, on the end of the cable.

    On a network installation, one of the two wiring schemes (T568A or T568B) should be chosen and followed. It is important that the same wiring scheme is used for every termination in that project.

    The figure shows diagrams of the T568A and T568B wiring standards. Each shows the correct pinout for the individual wire pairs. Each color wire pair is numbered and consists of a solid color wire and a white striped wire. Pair 1 is blue, pair 2 is orange, pair 3 is green, and pair 4 is brown. Each standard alternates between white striped and solid wires. For the T568A standard, the blue pair are terminated at pins 4 and 5, the orange pair are terminated at pins 3 and 6, the green pair is terminated at pins 1 and 2, and the brown pair is terminated at pins 7 and 8. For the T568B standard, the blue pair is terminated at pins 4 and 5, the orange pair is terminated at pins 1 and 2, the green pair is termination at pins 3 and 6, and the brown pair is terminated at pins 7 and 8.

    ## T568A and T568B Standards

    1234567812345678

    Pair 2Pair 2Pair 4Pair 1Pair 3T568AT568BPair 3Pair 4Pair 1

    4.4.2

    ## Twisted-Pair Transmit and Receive Pairs

    Ethernet NICs and the ports on networking devices are designed to send data over UTP cables. Specific pins on the connector are associated with a transmit function and a receive function. The interfaces on each device are designed to transmit and receive data on designated wires within the cable.

    When two devices are directly connected using an UTP Ethernet cable, it is important that the transmit function and the receive function on each end of the cable are reversed. One device sends data on a specific set of wires and the device on the other end of the cable listens for the data on the same wires.

    Two devices that use different wires for transmit and receive are known as unlike devices. They require a straight-through cable to exchange data. Straight-through cables have the same color patterns on both ends of the cable.

    Devices that are directly connected and use the same pins for transmit and receive, are known as like devices. They require the use of a crossover cable in order to reverse the transmit function and receive function so that the devices can exchange data.

    ## The traceroute Command

    The internet is not really a place; it is the interconnection of many different networks that provide services to the users. We can see this connectivity by using a network utility call **traceroute**.

    As shown in the figure, the traceroute utility traces the route a message takes from its source to the destination. Each individual network through which the message travels is referred to as a hop. The **traceroute** command displays each hop along the way and the time it takes for the message to get to that network and back.

    If a problem occurs, use the output of the traceroute utility to help determine where a message was lost or delayed. The traceroute utility is called **tracert** in the Windows environment.
