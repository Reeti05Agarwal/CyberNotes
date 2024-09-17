# Injections

An injection attack is malicious code inserted into a vulnerable application. The infected application often appears to work normally. That's because the injected code runs in the background, unknown to the user. Applications are vulnerable to injection attacks because they are programmed to receive data inputs.

*   Server Side Injection

    * Code Injection
    * Email Header Injection
    * Template Injection
    * LPAD Injection
    * OS Command Injection
    * XPath Injection
    * SQL Injection

    ***
*   Client Side Injection

    * CRLF Injection
    * Host Header Injection

    ***

***

*   OS Injection

    \=Shell Injection

    It allows an attacker to execute operating system (OS) commands on the server that is running an application, and typically fully compromise the application and its data.

    ```cpp
    #OUTPUT
    https://insecure-website.com/stockStatus?productID=381&storeID=29

    #INPUT
    stockreport.pl 381 29
    ```

    ```cpp
    #INPUT
    & echo aiwefwlguh &

    #OUTPUT
    stockreport.pl & echo aiwefwlguh & 29

    #OUTPUT
    Error - productID was not provided
    aiwefwlguh
    29: command not found
    ```

    The `echo` command causes the supplied string to be echoed in the output. This is a useful way to test for some types of OS command injection. The `&` character is a shell command separator. In this example, it causes three separate commands to execute, one after another.

    * The original `stockreport.pl` command was executed without its expected arguments, and so returned an error message.
    * The injected `echo` command was executed, and the supplied string was echoed in the output.
    * The original argument `29` was executed as a command, which caused an error.

    ## Commands:

    | Purpose of command    | Linux         | Windows         |
    | --------------------- | ------------- | --------------- |
    | Name of current user  | `whoami`      | `whoami`        |
    | Operating system      | `uname -a`    | `ver`           |
    | Network configuration | `ifconfig`    | `ipconfig /all` |
    | Network connections   | `netstat -an` | `netstat -an`   |
    | Running processes     | `ps -ef`      | `tasklist`      |

    ***

## Categories of SQL injection:

*   In-band

    In-band, or classic, SQL injection is the most common type. An in-band injection is one that uses the _same communication channel_ to launch the attack and gather the results.

    For example, this might occur in the search box of a retailer's website that lets customers find products to buy. If the search box is vulnerable to injection, an attacker could enter a malicious query that would be executed in the database, causing it to return sensitive information like user passwords. The data that's returned is displayed back in the search box where the attack was initiated.
*   Out-of-band

    An out-of-band injection is one that uses a _different communication channel_  to launch the attack and gather the results.

    For example, an attacker could use a malicious query to create a connection between a vulnerable website and a database they control. This separate channel would allow them to bypass any security controls that are in place on the website's server, allowing them to steal sensitive data
*   Inferential

    Inferential SQL injection occurs when an attacker is unable to directly see the results of their attack. Instead, they can interpret the results by analyzing the _behavior_ of the system.

    For example, an attacker might perform a SQL injection attack on the login form of a website that causes the system to respond with an error message. Although sensitive data is not returned, the attacker can figure out the database's structure based on the error. They can then use this information to craft attacks that will give them access to sensitive data or to take control of the system.

## **Prevent injection attacks:**

* **Prepared statements**: a coding technique that executes SQL statements before passing them on to a database
* **Input sanitization**: programming that removes user input which could be interpreted as code.
* **Input validation**: programming that ensures user input meets a system's expectations.
