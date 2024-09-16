# Metasploit

Used in all phases of a penetration testing engagement, from information gathering to post-exploitation.

*   Ques:

    *   Which programming language can be used to write Metasploit scripts for Metasploit 4.x Framework?

        Ruby
    *   **Which command sets the SHELLCODE?**

        set PAYLOAD payloadname
    *   What is black box pentesting?

        cybersecurity assessment approach where the tester has no prior knowledge of the target system or network being tested. In other words, the tester doesn't have access to the internal workings, architecture, or source code of the system under examination.

    ***

#### The main components

* **msfconsole**: The main command-line interface.
* **Modules**: supporting modules such as exploits, scanners, payloads, etc.
* **Tools**: Stand-alone tools that will help vulnerability research, vulnerability assessment, or penetration testing. Some of these tools are msfvenom, pattern\_create and pattern\_offset. We will cover msfvenom within this module, but pattern\_create and pattern\_offset are tools useful in exploit development which is beyond the scope of this module.
* **Exploit:** A piece of code that uses a vulnerability present on the target system.
* **Vulnerability:** A design, coding, or logic flaw affecting the target system. The exploitation of a vulnerability can result in disclosing confidential information or allowing the attacker to execute code on the target system.
* **Payload:** An exploit will take advantage of a vulnerability. Payloads are the code that will run on the target system.

***

#### Auxiliary

Any supporting module, such as scanners, crawlers and fuzzers, can be found here.

#### **Encoders**

Encoders will allow you to encode the exploit and payload in the hope that a signature-based antivirus solution may miss them.

Signature-based antivirus and security solutions have a database of known threats. They detect threats by comparing suspicious files to this database and raise an alert if there is a match. Thus encoders can have a limited success rate as antivirus solutions can perform additional checks.

#### Evasion

While encoders will encode the payload, they should not be considered a direct attempt to evade antivirus software. On the other hand, “evasion” modules will try that, with more or less success.

#### Exploits

Exploits, neatly organized by target system.

#### NOPs

NOPs (No OPeration) do nothing, literally. They are represented in the Intel x86 CPU family they are represented with 0x90, following which the CPU will do nothing for one cycle. They are often used as a buffer to achieve consistent payload sizes.

## Payloads

* **Payloads Overview**:
  * Codes designed to execute on the target system.
* **Interactive Connection**:
  * Importance of an interactive command line, known as a "shell".
* **Metasploit Capability**:
  * Metasploit provides various payloads facilitating the opening of shells on the target system.

four directories under payloads:

*   **Adapters:**

    An adapter wraps single payloads to convert them into different formats. For example, a normal single payload can be wrapped inside a Powershell adapter, which will make a single powershell command that will execute the payload.
*   **Singles:**

    Self-contained payloads (add user, launch notepad.exe, etc.) that do not need to download an additional component to run.
*   **Stagers:**

    Responsible for setting up a connection channel between Metasploit and the target system. Useful when working with staged payloads. “Staged payloads” will first upload a stager on the target system then download the rest of the payload (stage). This provides some advantages as the initial size of the payload will be relatively small compared to the full payload sent at once.
*   **Stages:**

    Downloaded by the stager. This will allow you to use larger sized payloads.

Subtle way to help you identify single payloads and staged payloads:

* generic/shell\_reverse\_tcp
* windows/x64/shell/reverse\_tcp

Both are reverse Windows shells. The former is an inline (or single) payload, as indicated by the “\_” between “shell” and “reverse”. While the latter is a staged payload, as indicated by the “/” between “shell” and “reverse”.

#### Post

Post modules will be useful on the final stage of the penetration testing process, post-exploitation.

## Msfconsole

To launch:

```cpp
$ msfconsole
```

command line changes to msf6

```cpp
msf6 > ping -c 1 8.8.8.8
```

Google's DNS IP address (8.8.8.8)

add the `-c 1` option, so only a single ping was sent. Otherwise, the ping process would continue until it is stopped using `CTRL+C`.

Msfconsole is managed by context; this means that unless set as a global variable, all parameter settings will be lost if you change the module you have decided to use.

To use a module:

```cpp
use Module_Name
```

While the prompt has changed, you will notice we can still run the commands previously mentioned. This means we did not "enter" a folder as you would typically expect in an operating system command line.

To print the options in the module

```cpp
show options
```

To list payloads in the module:

```cpp
show payloads
```

To leave the context/module:

```cpp
back
```

To print further info of context/module:

```cpp
info
```

To search a module by giving some info:

```cpp
search Module_info
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/35ea3658-8938-467a-965b-bac5650e3fdb/Untitled.png)

direct the search function using keywords such as type and platform:

```cpp
search type:auxiliary telnet
```

set the RHOSTS parameter to the IP address of our target system using the `set` command.:

```cpp
set rhosts 10.10.165.39
```

#### Parameters

*   **RHOSTS:**

    “Remote host”, the IP address of the target system. A single IP address or a network range can be set. This will support the CIDR (Classless Inter-Domain Routing) notation (/24, /16, etc.) or a network range (10.10.10.x – 10.10.10.y). You can also use a file where targets are listed, one target per line using file:/path/of/the/target\_file.txt, as you can see below.
*   **RPORT:**

    “Remote port”, the port on the target system the vulnerable application is running on.
*   **PAYLOAD:**

    The payload you will use with the exploit.
*   **LHOST:**

    “Localhost”, the attacking machine (your AttackBox or Kali Linux) IP address.
*   **LPORT:**

    “Local port”, the port you will use for the reverse shell to connect back to. This is a port on your attacking machine, and you can set it to any port not used by any other application.
*   **SESSION:**

    Each connection established to the target system using Metasploit will have a session ID. You will use this with post-exploitation modules that will connect to the target system using an existing connection.

clear any parameter value:

```cpp
unset all
```

to set values that will be used for all modules:

```cpp
setg rhosts 10.10.165.39
```

The `setg` command sets a global value that will be used until you exit Metasploit or clear it using the `unsetg` command.

To launch the module:

```cpp
exploit
```

The `exploit -z` command will run the exploit and background the session as soon as it opens.

check if the target system is vulnerable without exploiting it:

```cpp
check
```

#### meterpreter

This console is used when a session is established between metasploit and the target system.

To background the session prompt and go back to the msfconsole prompt:

```cpp
meterpreter > background
```

Alternatively, `CTRL+Z` can be used to background sessions.

To get to session:

```cpp
msf6 > sessions

Active sessions
===============

  Id  Name  Type                     Information                   Connection
  --  ----  ----                     -----------                   ----------
  1         meterpreter x64/windows  NT AUTHORITY\\SYSTEM @ JON-PC  10.10.44.70:4444 -> 10.10.12.229:49163 (10.10.12.229)
  2         meterpreter x64/windows  NT AUTHORITY\\SYSTEM @ JON-PC  10.10.44.70:4444 -> 10.10.12.229:49186 (10.10.12.229)

msf6 > sessions -i 2
[*] Starting interaction with 2...
```

can be used to create a printscreen from the target machine:

```python
screenshot
```

***
