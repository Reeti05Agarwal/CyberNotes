# Broken Access Control

*   QUES:

    *   Which category includes XSS in OSWASP Top 10 2021 ?

        In the OWASP Top Ten Project, the category that includes Cross-Site Scripting (XSS) is "Injection."

        XSS is typically categorized as a type of injection attack, where malicious scripts or code are injected into web pages viewed by other users. Specifically, it falls under "A7: Cross-Site Scripting (XSS)" in the OWASP Top 10 list for 2021. XSS vulnerabilities occur when untrusted data is included in web pages without proper validation or escaping, allowing attackers to execute malicious scripts in the context of other users' browsers. It's a common web application security issue that can have severe consequences.
    *   Parameter temepering of GET parameters can be mitigated using

        Using HTTPS instead of HTTP .

        Randomizing GET parameters .

        Client side input validation .
    *   IDOR can be mitigated by

        Using " Hidden " form field for accessing resourcing
    *   The secure file permission(s) are

        * rws---r-x root root
        * rwx------ root root
        * drwxr-x-w-root root
        * r-xr-xr-x- root root

        The one with s (owner's execute permission)
    *   An attack technique that forces a user's session credential or session ID to an explicit value.

        Session Fixation
    *   Which threat can be prevented by having unique usernames generated with a high degree of entropy ?

        Authorization Bypass
    *   Broken authentication is caused due to

        Improper implementation of authentication and session management.
    *   credential stuffing

        Automated injection of breached username / password pairs .
    *   Rate limit prevents what type of attacks ?

        Brute force or other automated attacks

        Rate limiting is a security measure that restricts the number of requests or login attempts that a user or an IP address can make within a certain time frame. This is specifically designed to thwart brute force attacks, where attackers try to gain unauthorized access by repeatedly trying various combinations of usernames and passwords.
    *   Parameter temepering of GET parameters can be mitigated using

        Randomizing GET parameters .

        1. **Input Validation:** Validate and sanitize user input on the server side to ensure that the values provided in GET parameters are valid and conform to expected formats. This can help prevent malicious or unexpected input.
        2. **Authorization and Authentication:** Implement strong authentication and authorization mechanisms to ensure that users can only access and modify data that they are authorized to access. This includes checking the user's identity and permissions before processing the request.
        3. **HTTPS (SSL/TLS):** Use HTTPS to encrypt data transmitted between the client and the server. This helps protect the integrity of the data and prevents eavesdropping, making it harder for attackers to tamper with parameters in transit.
        4. **Parameterization:** When interacting with databases, use parameterized queries or prepared statements to prevent SQL injection attacks. This is particularly relevant if the GET parameters are used in database queries.
        5. **Session Management:** Implement secure session management to ensure that sensitive data is stored and transmitted securely. This helps protect against session fixation and session hijacking attacks.
        6. **Output Encoding:** Encode output properly before sending it to the client to prevent Cross-Site Scripting (XSS) attacks, which could be used to manipulate parameters.
        7. **Rate Limiting:** Implement rate limiting to prevent abuse of the application, which can include excessive parameter tampering attempts.

    Role-based access control helps prevent the OWASP Top 10 weakness related to "Forced Browsing or Failure to Restrict URL.”

    ***

1. **Forced Browsing:** This occurs when an attacker is able to access resources or perform actions that should be protected by access controls. For example, an attacker might manipulate URLs to access unauthorized pages or data.
2. **IDOR (Insecure Direct Object Reference):** This vulnerability allows an attacker to manipulate references to objects (e.g., files, database records) to access or modify data that they shouldn't have access to.
3. **LFI (Local File Inclusion):** LFI vulnerabilities enable attackers to include and read files on a server that they should not have access to. This can lead to disclosure of sensitive information.
