# OSI\_Model

OSI Model

## OSI Model

## Purpose

The OSI model is a network architecture model that facilitates communication between different systems without requiring changes to the underlying hardware and software. It is not a protocol, but rather a model for designing network architecture.

![osi](../Networking/image.png)

## Seven Layers in OSI Model

*   Application

    Implemented in software.providing an interface for them to use in order to transmit data.
*   Presentation

    This data tends to be in a format that the application understands, but it's not necessarily in a standardised format that could be understood by the application layer in the _receiving_ computer.

    Convert the characters received from application into binary.

    Before data moving forward, it is first encrypted, so that its only redable to the person the data was send to.
*   Session

    Setting up and managing the connections and termination of the connected sessions.If it can't then it sends back an error and the process goes no further.

    Authentification and Authorization.

    It assumes that the below layer will do their work.

    it creates is unique to the communication in question. This is what allows you to make multiple requests to different endpoints simultaneously without all the data getting mixed up (think about opening two tabs in a web browser at the same time)!
*   Transport Layer

    Here are the summarized points:

    * **Data Transfer**: Transfers variable-length data sequences between source and destination hosts across a network.
    * **Quality of Service**: Maintains quality-of-service functions during data transfer.
    * **Transport Protocols**: Can be connection-oriented (TCP) or connectionless (UDP).
    * **Protocol Selection**: Chooses between TCP or UDP for data transmission.
    * **Segmentation**: Divides data from the session layer into smaller segments, each with a source, destination port number, and sequence number.
    * **Flow Control**: Manages the amount of data being transmitted.
    * **Error Control**: Ensures data integrity during transmission.
*   Network Layer

    responsible for locating the destination of your request.

    Transmission of received data segments from one computer to another that is located in different network.

    The router lives here.

    IP addressing done in the network layer is called logical addressing.

    It assigns the sender and receiver’s address to the segment and it forms an IP packet, So that every data packet reach a correct destination.

    PACKET CONTAINS: Sender’s, receiver’s address and subnet mask.
*   Data Link Layer

    Here are the summarized points:

    * **Node-to-Node Transfer**: Provides data transfer between two directly connected nodes.
    * **Error Handling**: Detects and possibly corrects errors from the physical layer.
    * **Connection Protocol**: Defines protocols for establishing and terminating connections.
    * **Flow Control**: Manages flow control protocols between connected devices.
    * **IEEE 802 Sublayers**:
      * **MAC Layer**: Controls network access and permissions for data transmission.
      * **LLC Layer**: Identifies and encapsulates network layer protocols, handles error checking, and frame synchronization.
    * **Physical Addressing**: Adds physical (MAC) addresses to packets from the network layer.
    * **Network Interface Card (NIC)**: Contains a unique, manufacturer-set MAC address, used for identifying devices in a network.
    * **MAC Address**: Used for identifying the destination of transmitted information; can be spoofed but not changed.
    * **Data Formatting**: Presents data in a transmission-suitable format.
    * **Error Checking**: Verifies data integrity upon reception to ensure no corruption occurs during transmission.
*   Physical Layers

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/f2c657bb-3cb9-4bbc-a080-33cf4c51521f/Untitled.png)

    It converts binary received data into bits.

    The Physical Layer is responsible for transmitting and receiving unstructured raw data between a device, such as a network interface controller, Ethernet hub or network switch and a physical transmission medium. It converts the digital bits into electrical, radio, or optical signals.

    Coordinates the functions required to carry a bit stream over a physical medium.

    * _**Physical characteristics of interfaces and medium**_
    *   _**Representation of bits**_

        Bits must be encoded into signals--electrical or optical.
    *   _**Data rate**_

        The number of bits sent each second.
    * _**Synchronization of bits**_
    * _**Line configuration**_
    * _**Physical topology**_
    *   _**Transmission mode**_

        The transmission direction between two devices: simplex, half-duplex, or full-duplex.
