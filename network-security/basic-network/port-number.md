# Port Number

### PORT NUMBER:

Now we have given internet for some permission, and when internet sends back data, its the IP address decide which device to send the data. In the device, port numbers decide which application to send data to.

When data packets are sent and received across a network, they are assigned a port.

Within the operating system of a network device, a port is a software-based location that organizes the sending and receiving of data between devices on a network. Ports divide network traffic into segments based on the service they will perform between two devices. The computers sending and receiving these data segments know how to prioritize and process these segments based on their port number.

This is like sending a letter to a friend who lives in an apartment building. The mail delivery person not only knows how to find the building, but they also know exactly where to go in the building to find the apartment number where your friend lives.

Port Number is a 16 bits number. So, total port numbers that are possible is 2^16.

HTTP will happen at port 80

MongoDB = 27017 port

0 - 1023 ports are reserved ports

1024 - 49152 ports reserved for applications

***

server should have well defined port number cause clients need to know about it.

Ephemeral Ports

IP addresses can change from device to device but cannot be active simultaneously more than once within the same network.

A public address is used to identify the device on the Internet, whereas a private address is used to identify a device amongst other devices.

***
