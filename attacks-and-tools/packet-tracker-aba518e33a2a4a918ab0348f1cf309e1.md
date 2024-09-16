# Packet Tracker aba518e33a2a4a918ab0348f1cf309e1

## Packet Tracker

practice your network configuration and troubleshooting skills via your desktop computer or an Android or iOS based mobile device. acket Tracer allows you to easily explore how data traverses your network. Packet Tracer provides an easy way to design and build networks of varying sizes without expensive lab equipment.

Packet Tracer is a tool that allows you to simulate real networks. It provides three main menus that allow you to:

* add devices and connect them via cables or wireless
* select, delete, inspect, label, and group components within your network
* manage your network

The network management menu allows you to:

* open an existing/sample network
* save your current network
* modify your user profile or your preferences

Finding a device to deploy requires looking in the Device-Type Selection Box. The Device-Type Selection Box works on the concept of categories and sub-categories as shown in the figure.

The top row of icons represents the category list consisting of: \[Networking Devices], \[End Devices], \[Components], \[Connections], \[Miscellaneous], and \[Multiuser]. Each category contains at least one sub-category group.

[Packet Tracer – Deploying Devices Instructions](https://contenthub.netacad.com/legacy/I2PT/1.1/en/course/files/2.1.1.2%20Packet%20Tracer%20-%20Deploying%20Devices.pdf)

[Packet Tracer - Deploying Devices Packet Tracer File](https://contenthub.netacad.com/legacy/I2PT/1.1/en/course/files/2.1.1.2-Deploying%20Devices.pkt)

[Packet Tracer – Deploying and Cabling Devices Instructions](https://contenthub.netacad.com/legacy/I2PT/1.1/en/course/files/2.1.1.2%20Packet%20Tracer%20-%20Deploying%20and%20Cabling%20Devices.pdf)

[Packet Tracer – Deploying and Cabling Devices Packet Tracer File](https://contenthub.netacad.com/legacy/I2PT/1.1/en/course/files/2.1.1.2-Deploying%20and%20Cabling%20Devices.pkt)

To access the configuration interface of any devices first click on the device that you wish to configure. A popup window will appear displaying a series of tabs. Different types of devices have different interfaces.

## Packet Tracer - GUI and CLI Configuration

For intermediate devices such as routers and switches, there are two methods of configuration available. Devices can be configured or investigated via a Config tab (a GUI interface) or a command line interface (CLI) (Figure 1). The Config tab does not exist in most physical equipment. This tab is a learning tab in Packet Tracer. If you don’t know how to use the command line interface, this tab provides a way to “fill in the blank” to do basic configurations. It will show the equivalent CLI commands that would do the same thing if using the Command Line Interface. The CLI interface requires knowledge of device configuration.

For some of the end devices, such as PCs and laptops, Packet Tracer provides a desktop interface that gives you access to IP configuration, wireless configuration, a command prompt, a Web browser, and much more (Figure 2).

If you are configuring a server, the server has all of the functions of the Host with the addition of one more tab, the services tab (Figure 3). This tab allows a server to be configured as a web server, a DHCP server, a DNS server, or various other servers visible in the graphic.

[Packet Tracer – Configure End devices Instructions](https://contenthub.netacad.com/legacy/I2PT/1.1/en/course/files/2.1.1.4%20Packet%20Tracer%20-%20Configure%20End%20Devices.pdf)

*   Physical

    The Physical tab provides an interface for interacting with the device including powering it on or off or installing different modules, such as a wireless network interface card (NIC).
*   Config

    The Config tab does not provide a real world environment. This tab is a learning tab in Packet Tracer. If you don’t know how to use the command line interface, this tab provides a way to “fill in the blank” to do basic configurations. It will show the equivalent CLI commands that perform the same action if someone was configuring using the CLI tab.
*   CLI

    The CLI tab provides access to the CLI interface, which requires knowledge of device configuration. Here, you can practice configuring the device at the command line. CLI configuration is a necessary skill for more advanced networking implementations.
*   Desktop

    For some of the end devices, such as PCs and laptops, Packet Tracer provides a desktop interface that gives you access to IP configuration, wireless configuration, a command prompt, a web browser, and much more.
*   Services

    This tab allows a server to be configured as a web server, a DHCP server, a DNS server, or various other servers visible in the graphic.

**Simulation Mode**

verify device connectivity and to study how the various types of data traverse your network.

## Viewing the Contents of PDUs

Once the PDUs have been captured, you have several ways to view their contents. Viewing the contents of the PDUs can be used to verify connectivity, verify functionality, and troubleshoot issues. It is also a great tool for studying or reviewing the contents of the OSI model layers and the mechanisms of communication.

If viewed in OSI Model mode, you see a summary of the addresses and contents of the headers at each layer. If you select Inbound or Outbound PDU Details, the exact format of the appropriate headers is displayed.

## The Packet Tracer Physical View

Now that you know the purpose and the use of the menus in the logical workspace, we will move on to learn about the physical workspace in Packet Tracer. The default view for Packet Tracer is Logical, which is equivalent to creating a logical diagram for the network. The other type of diagram used in networking is the physical diagram which not only shows the relationships of the network devices but also applies building and distance factors in making the design.

Packet Tracer has the physical workspace that allows you to make your network more realistic by adding backgrounds, buildings, and wiring closets. These features are important for documentation, design, and visualization. You can see the actual layout of the network within a room or a building. This provides valuable information into the flow of traffic and the suitability and placement of equipment. The Physical view also has a great feature that shows the wireless coverage areas based on your equipment placement within buildings.

In this section, you will learn to:

* Navigate the physical workspace.
* Add cities, corporate offices, and branch offices.
* Add backgrounds into the cities and offices.
* Add wiring closets to the offices.
* Place networking devices into racks within the closets.

When the Physical view is shown, the basic organizational scheme is the following:

a.    intercity

b.    city

c.    building

d.    wiring closet

A user is able to add as many cities, buildings, and wiring closets as they need; however, there can only be one intercity. Containers of smaller sizes can be added at any level but larger containers cannot be added into smaller containers. For example, a building can be added to the intercity, but a city cannot be added to a building, and a building cannot be added to a wiring closet.

## Packet Tracer File Types

Packet Tracer has the ability to create three different types of files. These file types are used for different purposes and include: .pkt, .pkz, and .pka.

The .pkt file type is used when a simulated network is built in Packet Tracer and saved. The .pkt file can also have backgrounds embedded within it.

The .pkz file type is not used very often. It is a compressed file that allows the inclusion of other files, such as .pdf files, along with the Packet Tracer files.

The .pka file type is a Packet Tracer Activity file. This file type contains a Packet Tracer activity plus an instruction window. The instructions provide a walkthrough of the necessary processes required to complete the activity, assignment, or assessment. The instruction window also contains a completion percentage to track how much of the activity has been successfully completed. There is also a Check Results feature that can be configured to provide feedback.

## Configure IoT Devices using Packet Tracer.

Packet Tracer has a wide variety of sensors and smart devices that will allow you to design smart homes, smart cities, smart factories, and smart power grids.

To locate the available sensors and smart devices, select End Devices from the Device Selection box at the lower left-hand side of the screen. Next select one of the subcategories such as Home. In the Home subcategory, you will see many IoT devices such as an air conditioner, ceiling fan, coffee maker, and CO detector. These devices can be connected to your network wirelessly or with a physical cable.

To connect the devices to your network, you need a device, such as a home gateway or registration server. To find a home gateway, select Network Devices from the Device Selection box and then select Wireless Devices from the subcategories.

To control the devices, you have two options:

1. You can interact directly with a device. Hold down the Alt key and at the same time click on the device to turn it on or off.
2. You can connect remotely over the network. Using a remote PC, tablet or smart phone, you can use a web browser to connect to the home gateway or registration server. From here, you can turn the devices on or off using the features of the home gateway or registration server.

To configure devices, click on the device to open it. Once opened, you have a multiple tabs to select:

* Specifications – describes the features, usage, local and remote control of the device
* Physical – available modules and power connections
* Config – shows display name, serial number, network configuration, and IoT server
* Attributes – display the device attributes such as MTBF, power consumption, and cost

To configuration the home gateway, you click on the device. Within the device you have multiple tabs to select.

* Physical – available modules, and power
* Config – shows display name, interfaces (Internet, LAN, and wireless) to be configured
* GUI – shows services to be turned on/off
* Attributes – shows features and values related to device such as: mean time between failure (MTBF), cost, power sources, and wattage

## Connecting and Monitoring IoT Devices Using a Home Gateway.

The Home Gateway device acts as a local connection to your IoT smart devices. This device was designed to provide Internet access, wireless connectivity, and local logic for smart devices. The Home Gateway device provides an IoT registration service that is always turned on and an auto discovery service for Things in the local Ethernet and wireless network. Once connected to the home gateway, the user can control and monitor the smart devices from their smartphone, tablet, or PC.

Once a home gateway device has been added to the logical workspace, click on the device. You will see the following:

* Physical tab – The Physical tab provides an interface for interacting with the device including powering it on or off or installing different modules, such as a wireless network interface card (NIC).
* Config tab – this shows the interfaces and network settings that are configurable
* GUI tab – this shows the registration server inside the device that allows for interaction with IoT devices. It is on by default but can be turned off.
* Attributes tab – This is blank by default but can show features and values such as MTBF, cost, power source, and wattage.

After connecting the home gateway to an existing network, select the Config tab. The internet and the wireless interfaces should obtain IP addressing information from the network.

To connect an IoT device, such as a fan, wirelessly, click on the fan and select the Config tab. The simple config tab appears. Select the Advanced button in the lower right hand corner to view more options.

To configure and register the fan with the home gateway:

* Select I/O Config and then select wireless adapter from the network adaptors dropdown list.
* Select Config to verify that the fan has established a wireless connection to the correct SSID. This can also be done visually by viewing the fan in the workspace.
* Select Config/Settings and select the home gateway as the IoT server registration device.

To control the fan remotely:

* Add a tablet, PC, or smart phone to the workspace and connect it to the home gateway. Click on the remote device and select Desktop/IPConfig to verify connectivity.
* Return to the desktop and select the web browser. Use the default gateway address from the remote device as the URL. This is the address of the home gateway. Once into the home gateway, you should see the registered fan and be able to modify its settings.

## Registering Devices to a Dedicated Registration Server.

IoT devices can also be registered to a dedicated Registration Server for remote monitoring, configuration, or programming. The dedicated registration server has the benefit of being able to provide many other services to your network, such as Web, DHCP, DNS, email, and FTP.

With a dedicated server, IoT devices would first be connected to a wireless network and would then be configured to register to the server.

To connect and configure the registration server:

* Connect the server to your network using a wired or wireless connection.
* Click on the server and select Desktop/IP configuration. Ensure that DHCP has been turned on and then verify that the server is obtaining an IP addresse.
* Select Services/IoT and turn the Registration Server on.

To configure a remote device to interact with the registration server:

* Connect a remote device such as a tablet, PC, or smart phone to the wireless network.
* Click on the remote device and select Desktop/Web Browser. Use the IP address of the registration server as the URL.
* The first time you access the server, you will have to create a user login. Subsequent visits will require you to login using the login credentials. For security reasons, it is important to protect your IoT devices by using strong passwords on your server.

To register IoT devices with the Dedicated Server:

* Click on each device and select the Config tab.
* Select the remote server option under IoT server and supply the IP address of the server, plus the login information.
* Use the remote device to verify the presence of the registered IoT devices.

#### Packet Tracer DHCP Configuration on a Wireless Router

**Internet Setup:**

* **Internet Connection Type:** Automatic Configuration – DHCP
* **Optional Settings:** Host Name and Domain Name are blank.
* **MTU Size:** 1500

**Network Setup:**

* **Router IP:** 192.168.0.1
* **Subnet Mask:** 255.255.255.0

**DHCP Server Settings:**

* **DHCP Server:** Enabled
* **Start IP Address:** 192.168.0.100
* **Maximum Number of Users:** 50
* **IP Address Range:** 192.168.0.100 - 192.168.0.149
* **Client Lease Time:** 0 (interpreted as 1 day)
* **Static DNS and WINS Server Addresses:** Blank

**Key Points:**

* The default IP address of the router (192.168.0.1) serves as the default gateway for all local network hosts and as the internal DHCP server address.
* The DHCP range can be customized, ensuring the starting address doesn't overlap with the router's IP address.
* The lease time is adjustable; the default lease time in the example is set to 24 hours.
* The DHCP configuration screen provides information about connected hosts, including their IPv4 addresses, MAC addresses, and lease times.

**Usage Notes:**

* Most home wireless routers have DHCP Server enabled by default.
* Configuration ensures that devices on the local network receive appropriate IP addresses and can communicate effectively within the network.

**Example Configuration Steps:**

1. **Access Router Interface:**
   * Open a web browser and enter the router’s default IP address (192.168.0.1).
2. **Navigate to DHCP Settings:**
   * Log in and go to the DHCP settings section.
   * Enable DHCP Server if not already enabled.
3. **Set DHCP Range:**
   * Specify the start IP address (e.g., 192.168.0.100).
   * Set the maximum number of users (e.g., 50 users, resulting in an IP range from 192.168.0.100 to 192.168.0.149).
4. **Adjust Lease Time:**
   * Modify the lease time if needed (default is typically 24 hours).
5. **Save Configuration:**
   * Save and apply the settings to ensure DHCP is properly configured.

## Primary Command Modes

In the previous topic, you learned that all network devices require an OS and that they can be configured using the CLI or a GUI. Using the CLI may provide the network administrator with more precise control and flexibility than using the GUI. This topic discusses using CLI to navigate the Cisco IOS.

As a security feature, the Cisco IOS software separates management access into the following two command modes:

* **User EXEC Mode** - This mode has limited capabilities but is useful for basic operations. It allows only a limited number of basic monitoring commands but does not allow the execution of any commands that might change the configuration of the device. The user EXEC mode is identified by the CLI prompt that ends with the > symbol.
* **Privileged EXEC Mode** - To execute configuration commands, a network administrator must access privileged EXEC mode. Higher configuration modes, like global configuration mode, can only be reached from privileged EXEC mode. The privileged EXEC mode can be identified by the prompt ending with the # symbol.

The table summarizes the two modes and displays the default CLI prompts of a Cisco switch and router.

| **Command Mode**                                                                              | **Description**                                                             | **Default Device Prompt** |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | ------------------------- |
| **User Exec Mode**                                                                            | • Mode allows access to only a limited number of basic monitoring commands. |                           |
| • It is often referred to as “view-only" mode.                                                | `Switch> Router>`                                                           |                           |
| **Privileged EXEC Mode**                                                                      | • Mode allows access to all commands and features.                          |                           |
| • The user can use any monitoring commands and execute configuration and management commands. | `Switch# Router#`                                                           |                           |

**Basic IOS Command Structure:**

* **Keyword** - This is a specific parameter defined in the operating system (in the figure, **ip protocols**).
* **Argument** - This is not predefined; it is a value or variable defined by the user (in the figure, **192.168.10.5**).

## IOS Command Syntax

A command might require one or more arguments. To determine the keywords and arguments required for a command, refer to the command syntax. The syntax provides the pattern, or format, that must be used when entering a command.

As identified in the table, boldface text indicates commands and keywords that are entered as shown. Italic text indicates an argument for which the user provides the value.

| **Convention**           | **Description**                                                                  |
| ------------------------ | -------------------------------------------------------------------------------- |
| **boldface**             | Boldface text indicates commands and keywords that you enter literally as shown. |
| _italics_                | Italic text indicates arguments for which you supply values.                     |
| **\[x]**                 | Square brackets indicate an optional element (keyword or argument).              |
| **{x}**                  | Braces indicate a required element (keyword or argument).                        |
| \*\*\[\*\*x **{** y \*\* | \*\* z **}]**                                                                    |

For instance, the syntax for using the **description** command is **description** _string._ The argument is a _string_ value provided by the user. The **description** command is typically used to identify the purpose of an interface. For example, entering the command, **description Connects to the main headquarter office switch**, describes where the other device is at the end of the connection.

The following examples demonstrate conventions used to document and use IOS commands:

* **ping** _ip-address_ - The command is **ping** and the user-defined argument of _ip-address_ is the IP address of the destination device. For example, **ping 10.10.10.5**.
* **traceroute** _ip-address_ - The command is **traceroute** and the user-defined argument of _ip-address_ is the IP address of the destination device. For example, **traceroute 192.168.254.254**.

If a command is complex with multiple arguments, you may see it represented like this:

`Switch(config-if)# **switchport port-security aging** { **static** | **time** *time* | **type** {**absolute** | **inactivity**}}`

| **Keystroke**                          | **Description**                                                                             |
| -------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Tab**                                | Completes a partial command name entry.                                                     |
| **Backspace**                          | Erases the character to the left of the cursor.                                             |
| **Ctrl+D**                             | Erases the character at the cursor.                                                         |
| **Ctrl+K**                             | Erases all characters from the cursor to the end of the command line.                       |
| **Esc D**                              | Erases all characters from the cursor to the end of the word.                               |
| **Ctrl+U** or **Ctrl+X**               | Erases all characters from the cursor back to the beginning of the command line.            |
| **Ctrl+W**                             | Erases the word to the left of the cursor.                                                  |
| **Ctrl+A**                             | Moves the cursor to the beginning of the line.                                              |
| **Left Arrow** or **Ctrl+B**           | Moves the cursor one character to the left.                                                 |
| **Esc B**                              | Moves the cursor back one word to the left.                                                 |
| **Esc F**                              | Moves the cursor forward one word to the right.                                             |
| **Right Arrow** or **Ctrl+F**          | Moves the cursor one character to the right.                                                |
| **Ctrl+E**                             | Moves the cursor to the end of command line.                                                |
| **Up Arrow** or **Ctrl+P**             | Recalls the previous command in the history buffer, beginning with the most recent command. |
| **Down Arrow** or **Ctrl+N**           | Goes to the next line in the history buffer.                                                |
| **Ctrl+R** or **Ctrl+I** or **Ctrl+L** | Redisplays the system prompt and command line after a console message is received.          |

| **Keystroke**   | **Description**                                                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Enter**       | Displays the next line.                                                                                                                          |
| **Space**       | Displays the next screen.                                                                                                                        |
| Any other key\* | Ends the display string, returning to previous prompt.\*Except "y", which answers "yes" to the **--More--** prompt, and acts like the **Space**. |

| **Keystroke**    | **Description**                                                                                                                                         |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ctrl-C**       | When in any configuration mode, ends the configuration mode and returns to privileged EXEC mode. When in setup mode, aborts back to the command prompt. |
| **Ctrl-Z**       | When in any configuration mode, ends the configuration mode and returns to privileged EXEC mode.                                                        |
| **Ctrl-Shift-6** | All-purpose break sequence used to abort DNS lookups, traceroutes, pings, and to interrupt an IOS process.                                              |

| Command                 | Used to                                                              |
| ----------------------- | -------------------------------------------------------------------- |
| **show running-config** | Verify the current configuration and settings.                       |
| **show interfaces**     | Verify the interface status and see if there are any error messages. |
| **show ip interface**   | Verify the Layer 3 information of an interface.                      |
| **show arp**            | Verify the list of known hosts on the local Ethernet LANs.           |
| **show ip route**       | Verify the Layer 3 routing information.                              |
| **show protocols**      | Verify which protocols are operational.                              |
| **show version**        | Verify the memory, interfaces, and licenses of the device.           |

## Basic Switch Configuration Steps

The Cisco switch comes preconfigured and only needs to be assigned basic security information before being connected to the network. Elements that are usually configured on a LAN switch include: host name, management IP address information, passwords, and descriptive information.

The switch host name is the configured name of the device. Just like each computer or printer is assigned a name, networking equipment should be configured with a descriptive name. It is helpful if the device name includes the location where the switch will be installed. An example might be: SW\_Bldg\_R-Room\_216.

A management IP address is only necessary if you plan to configure and manage the switch through an in-band connection on the network. A management address enables you to reach the device through Telnet, SSH, or HTTP clients. The IP address information that must be configured on a switch is essentially the same as you configure on a PC: IP address, subnet mask, and default gateway.

In order to secure a Cisco LAN switch, it is necessary to configure passwords on each of the various methods of access to the command line. The minimum requirements include assigning passwords to remote access methods, such as Telnet, SSH and the console connection. You must also assign a password to the privileged mode in which configuration changes can be made.

**Note**: Telnet sends the username and password in plaintext and is not considered secure. SSH encrypts the username and password and is, therefore, a more secure method.

*   Configuration task

    **Configuration Tasks**

    Before configuring a switch, review the following initial switch configuration tasks:

    Configure the device name.

    * **hostname** _name_

    Secure user EXEC mode.

    * **line console 0**
    * **password** _password_
    * **login**

    Secure remote Telnet / SSH access.

    * **line vty 0 15**
    * **password** _password_
    * **login**

    Secure privileged EXEC mode.

    * **enable secret** _password_

    Secure all passwords in the config file.

    * **service password-encryption**

    Provide legal notification.

    * **banner motd** _delimiter message delimiter_

    Configure the management SVI.

    * **interface vlan 1**
    * **ip address** _ip-address subnet-mask_
    * **no shutdown**

    Save the configuration.

    * **copy running-config startup-config**

    ##

## Switch Virtual Interface Configuration

To access the switch remotely, an IP address and a subnet mask must be configured on the switch virtual interface (SVI). To configure an SVI on a switch, use the **interface vlan 1** global configuration command. Vlan 1 is not an actual physical interface but a virtual one. Next, assign an IPv4 address using the **ip address** _ip-address subnet-mask_ interface configuration command. Finally, enable the virtual interface using the **no shutdown** interface configuration command.

After the switch is configured with these commands, the switch has all the IPv4 elements ready for communication over the network.

**Note**: Similar to Windows hosts, switches configured with an IPv4 address will typically also need to have a default gateway assigned. This can be done using the **ip default-gateway** _ip-address_ global configuration command. The _ip-address_ parameter would be the IPv4 address of the local router on the network, as shown in the example. However, in this topic you will only be configuring a network with switches and hosts. Routers will be configured later.

`Sw-Floor-1# **configure terminal** Sw-Floor-1(config)# **interface vlan 1** Sw-Floor-1(config-if)# **ip address 192.168.1.20 255.255.255.0** Sw-Floor-1(config-if)# **no shutdown** Sw-Floor-1(config-if)# **exit** Sw-Floor-1(config)# **ip default-gateway 192.168.1.1**`

## Basic Router Configuration Steps

The following tasks should be completed when configuring initial settings on a router.

**Step 1.** Configure the device name.

`Router(config)# **hostname** *hostname*`

**Step 2.** Secure privileged EXEC mode.

`Router(config)# **enable secret** *password*`

**Step 3.** Secure user EXEC mode.

`Router(config)# **line console 0** Router(config-line)# **password** *password* Router(config-line)# **login**`

**Step 4.** Secure remote Telnet / SSH access

`Router(config-line)# **line vty 0 4** Router(config-line)# **password** *password* Router(config-line)# **login** Router(config-line)# **transport input** {**ssh** | **telnet** | **none** | **all**}`

**Step 5.** Secure all passwords in the config file

`Router(config-line)# **exit** Router(config)# **service password-encryption**`

**Step 6.** Provide legal notification.

`Router(config)# **banner motd** *delimiter message delimiter*`

**Step 7.** Save the configuration.

`Router(config)# **copy running-config startup-config**`

*   **Basic Router Configuration Example**

    In this example, router R1 will be configured with initial settings. To configure the device name for R1, use the following commands.

    `Router> **enable** Router# **configure terminal** Enter configuration commands, one per line. End with CNTL/Z. Router(config)# **hostname R1** R1(config)#`

    **Note:** Notice how the router prompt now displays the router host name.

    All router access should be secured. Privileged EXEC mode provides the user with complete access to the device and its configuration, so you must secure it.

    The following commands secure privileged EXEC mode and user EXEC mode, enable Telnet and SSH remote access, and encrypt all plaintext (i.e., user EXEC and vty line) passwords. It is very important to use a strong password when securing privileged EXEC mode because this mode allows access to the configuration of the device.

    `R1(config)# **enable secret class** R1(config)# R1(config)# **line console 0** R1(config-line)# **password cisco** R1(config-line)# **login** R1(config-line)# **exit** R1(config)# R1(config)# **line vty 0 4** R1(config-line)# **password cisco** R1(config-line)# **login** R1(config-line)# **transport input ssh telnet** R1(config-line)# **exit** R1(config)# R1(config)# **service password-encryption** R1(config)#`

    The legal notification warns users that the device should only be accessed by permitted users. Legal notification is configured as follows:

    `R1(config)# **banner motd #Enter TEXT message. End with the character '#'.***********************************************WARNING: Unauthorized access is prohibited!***********************************************#** R1(config)#`

    If the router were to be configured with the previous commands and it accidently lost power, the router configuration would be lost. For this reason, it is important to save the configuration when changes are implemented. The following command saves the configuration to NVRAM:

    `R1# **copy running-config startup-config** Destination filename [startup-config]? Building configuration... [OK] R1#`

## Syntax Checker - Configure Initial Router Settings

Use this syntax checker to practice configuring the initial settings on a router.

* Configure the device name.
* Secure the privileged EXEC mode.
* Secure and enable remote SSH and Telnet access.
* Secure all plaintext passwords.
* Provide legal notification.

```jsx
Enter global configuration mode to configure the name of the router as “R1”.

Router>enable
Router#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#hostname R1
Configure 'class' as the secret password.

R1(config)#enable secret class
Configure 'cisco' as the console line password, require users to login, and return to global configuration mode.

R1(config)#line console 0
R1(config-line)#password cisco
R1(config-line)#login
R1(config-line)#exit
For vty lines 0 through 4, configure 'cisco' as the password, require users to login, enable SSH and Telnet access, and return to global configuration mode.

R1(config)#line vty 0 4
R1(config-line)#password cisco
R1(config-line)#login
R1(config-line)#transport input ssh telnet
R1(config-line)#exit
Encrypt all clear text passwords.

R1(config)#service password-encryption
Enter the banner 'Authorized Access Only!' and use # as the delimiting character.

R1(config)#banner motd #Authorized Access Only!#
Exit global configuration mode.

R1(config)#exit
R1#
You have successfully configured the initial settings on router R1.
```

## Secure Remote Access

There are multiple ways to access a device to perform configuration tasks. One of these ways is to use a PC attached to the console port on the device. This type of connection is frequently used for initial device configuration.

Setting a password for console connection access is done in global configuration mode. These commands prevent unauthorized users from accessing user mode from the console port.

```jsx

Switch(config)# **line console 0**
Switch(config-line)# **password** *password*
Switch(config-line)# **login**
```

When the device is connected to the network, it can be accessed over the network connection using SSH or Telnet. SSH is the preferred method because it is more secure. When the device is accessed through the network, it is considered a vty connection. The password must be assigned to the vty port. The following configuration is used to enable SSH access to the switch.

```jsx

Switch(config)# **line vty 0 15**
Switch(config-line)# **password** *password*
Switch(config-line)# **transport input ssh**
Switch(config-line)# **login**
```

An example configuration is shown in the command window.

```jsx

S1(config)# **line console 0**
S1(config-line)# **password cisco**
S1(config-line)# **login**
S1(config-line)# **exit**
S1(config)#  
S1(config)# **line vty 0 15**
S1(config-line)# **password cisco**
S1(config-line)# **login**
S1(config-line)#
```

By default, many Cisco switches support up to 16 vty lines that are numbered 0 to 15. The number of vty lines supported on a Cisco router varies with the type of router and the IOS version. However, five is the most common number of vty lines configured on a router. These lines are numbered 0 to 4 by default, though additional lines can be configured. A password needs to be set for all available vty lines. The same password can be set for all connections.

To verify that the passwords are set correctly, use the **show running-config** command. These passwords are stored in the running-configuration in plaintext. It is possible to set encryption on all passwords stored within the router so that they are not easily read by unauthorized individuals. The global configuration command **service password-encryption** ensures that all passwords are encrypted.

With remote access secured on the switch, you can now configure SSH.

## Configure SSH

Before configuring SSH, the switch must be minimally configured with a unique hostname and the correct network connectivity settings.

**Step 1. Verify SSH support.**

Use the **show ip ssh** command to verify that the switch supports SSH. If the switch is not running an IOS that supports cryptographic features, this command is unrecognized.

**Step 2. Configure the IP domain.**

Configure the IP domain name of the network using the **ip domain-name** _domain-name_ global configuration mode command. In the example configuration below, the _domain-name_ value is **cisco.com**.

**Step 3. Generate RSA key pairs.**

Not all versions of the IOS default to SSH version 2, and SSH version 1 has known security flaws. To configure SSH version 2, issue the **ip ssh version 2** global configuration mode command. Generating an RSA key pair automatically enables SSH. Use the **crypto key generate rsa** global configuration mode command to enable the SSH server on the switch and generate an RSA key pair. When generating RSA keys, the administrator is prompted to enter a modulus length. The sample configuration in the figure uses a modulus size of 1,024 bits. A longer modulus length is more secure, but it takes more time to generate and to use.

**Note**: To delete the RSA key pair, use the **crypto key zeroize rsa** global configuration mode command. After the RSA key pair is deleted, the SSH server is automatically disabled.

**Step 4. Configure user authentication.**

The SSH server can authenticate users locally or use an authentication server. To use the local authentication method, create a username and password pair with the **username** _username_ **secret** _password_ global configuration mode command. In the example, the user **admin** is assigned the password **ccna**.

**Step 5. Configure the vty lines.**

Enable the SSH protocol on the vty lines using the **transport input ssh** line configuration mode command. The Catalyst 2960 has vty lines ranging from 0 to 15. This configuration prevents non-SSH (such as Telnet) connections and limits the switch to accept only SSH connections. Use the **line vty** global configuration mode command and then the **login local** line configuration mode command to require local authentication for SSH connections from the local username database.

**Step 6. Enable SSH version 2.**

By default, SSH supports both versions 1 and 2. When supporting both versions, this is shown in the **show ip ssh** output as supporting version 1.99. Version 1 has known vulnerabilities. For this reason, it is recommended to enable only version 2. Enable SSH version using the **ip ssh version 2** global configuration command.

```jsx

S1# **show ip ssh**
SSH Disabled - version 1.99
%Please create RSA keys (of at least 768 bits size) to enable SSH v2.
Authentication timeout: 120 secs; Authentication retries: 3
S1# **configure terminal**
S1(config)# **ip domain-name cisco.com**
S1(config)# **crypto key generate rsa**
The name for the keys will be: S1.cisco.com 
... 
How many bits in the modulus [512]: **1024** 
... 
S1(config)# **username admin secret ccna**
S1(config-line)# **line vty 0 15**
S1(config-line)# **transport input ssh**
S1(config-line)# **login local**
S1(config-line)# **exit**
S1(config)# **ip ssh version 2**
S1(config)# **exit**
S1#
```

**Syntax Checker - Configure SSH**

```jsx
Set the domain name to cisco.com and generate the 1024 bit rsa key.

S1(config)#ip domain-name cisco.com
S1(config)#crypto key generate rsa
The name for the keys will be: S1.cisco.com  
Choose the size of the key modulus in the range of 360 to 4096 for your General Purpose Keys. Choosing a key modulus greater than 512 may take a few minutes.
How many bits in the modulus [512]:1024
% Generating 1024 bit RSA keys, keys will be non-exportable...  
[OK] (elapsed time was 4 seconds)  
  
S1(config)#  
*Mar 1 02:20:18.529: %SSH-5-ENABLED: SSH 1.99 has been enabled
Create a local user admin with the password ccna. Set all vty lines to use ssh and local login for remote connections. Exit out to global configuration mode.

S1(config)#username admin secret ccna
S1(config)#line vty 0 15
S1(config-line)#transport input ssh
S1(config-line)#login local
S1(config-line)#exit
S1(config)#  
%SYS-5-CONFIG_I: Configured from console by console
Configure S1 to use SSH 2.0.

S1(config)#ip ssh version 2
S1(config)#
You successfully configured SSH on all VTY lines.
```

## Verify SSH

On a PC, an SSH client such as PuTTY, is used to connect to an SSH server. For the examples, the following have been configured:

* SSH enabled on switch S1
* Interface VLAN 99 (SVI) with IPv4 address 172.17.99.11 on switch S1
* PC1 with IPv4 address 172.17.99.21

After clicking Open in PuTTY, the user is prompted for a username and password. Using the configuration from the previous example, the username **admin** and password **ccna** are entered. After entering the correct combination, the user is connected via SSH to the CLI on the Catalyst 2960 switch.

To display the version and configuration data for SSH on the device that you configured as an SSH server, use the **show ip ssh** command. In the example, SSH version 2 is enabled. To check the SSH connections to the device, use the **show ssh** command.

```jsx

Login as: **admin**
Using keyboard-interactive authentication.
Password: **<ccna>**

S1> enable
Password: **<class>**
S1# **show ip ssh**
SSH Enabled - version 2.0 
Authentication timeout: 90 secs; Authentication retries: 2 
Minimum expected Diffie Hellman key size : 1024 bits 
IOS Keys in SECSH format(ssh-rsa, base64 encoded): 
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQCdLksVz2QlREsoZt2f2scJHbW3aMDM8 /8jg/srGFNL 
i+f+qJWwxt26BWmy694+6ZIQ/j7wUfIVNlQhI8GUOVIuKNqVMOMtLg8Ud4qAiLbGJfAaP3fyrKmViPpO 
eOZof6tnKgKKvJz18Mz22XAf2u/7Jq2JnEFXycGMO88OUJQL3Q==  
                            
S1# **show ssh**
Connection Version Mode Encryption  Hmac       State        Username 
0          2.0     IN   aes256-cbc  hmac-sha1 Session started admin 
0          2.0     OUT  aes256-cbc  hmac-sha1 Session started admin 
%No SSHv1 server connections running. 
S1#
```

## Default Gateway for a Host

If your local network has only one router, it will be the gateway router and all hosts and switches on your network must be configured with this information. This topic explains how to configure the default gateway on hosts and switches.

For an end device to communicate over the network, it must be configured with the correct IP address information, including the default gateway address. The default gateway is only used when the host wants to send a packet to a device on another network. The default gateway address is generally the router interface address attached to the local network of the host. The IP address of the host device and the router interface address must be in the same network.

For example, assume an IPv4 network topology consisting of a router interconnecting two separate LANs. G0/0/0 is connected to network 192.168.10.0, while G0/0/1 is connected to network 192.168.11.0. Each host device is configured with the appropriate default gateway address.

## Default Gateway on a Switch

A switch that interconnects client computers is typically a Layer 2 device. As such, a Layer 2 switch does not require an IP address to function properly. However, an IP configuration can be configured on a switch to give an administrator remote access to the switch.

To connect to and manage a switch over a local IP network, it must have a switch virtual interface (SVI) configured. The SVI is configured with an IPv4 address and subnet mask on the local LAN. The switch must also have a default gateway address configured to remotely manage the switch from another network.

The default gateway address is typically configured on all devices that will communicate beyond their local network.

To configure an IPv4 default gateway on a switch, use the **ip default-gateway** _ip-address_ global configuration command. The _ip-address_ that is configured is the IPv4 address of the local router interface connected to the switch.

**Syntax Checker - Configure the Default Gateway**

```jsx
nter global configuration mode.

S1#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Configure 192.168.10.1 as the default gateway for S1.

S1(config)#ip default-gateway 192.168.10.1
S1(config)#
You have successfully set the default gateway on switch S1.
```
