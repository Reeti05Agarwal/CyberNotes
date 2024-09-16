# Burpsuite

Burp can capture and manipulate all of the traffic between an attacker and a webserver: this is the core of the framework. After capturing requests, we can choose to send them to various other parts of the Burp Suite framework -- we will be covering some of these tools in upcoming rooms. This ability to intercept, view, and modify web requests prior to them being sent to the target server (or, in some cases, the responses before they are received by our browser), makes Burp Suite perfect for any kind of manual web app testing.

*   Proxy

    allows us to intercept and modify requests/responses when interacting with web applications.

    intercept requests between ourselves and the target

    *   Shortcuts

        | **Shortcut**       | **Does**                   |
        | ------------------ | -------------------------- |
        | `Ctrl + Shift + D` | Switch to the Dashboard    |
        | `Ctrl + Shift + T` | Switch to the Target tab   |
        | `Ctrl + Shift + P` | Switch to the Proxy tab    |
        | `Ctrl + Shift + I` | Switch to the Intruder tab |
        | `Ctrl + Shift + R` | Switch to the Repeater tab |
    * **Key Points to Understand About the Burp Proxy**
      *   **Intercepting Requests:**

          When requests are made through the Burp Proxy, they are intercepted and held back from reaching the target server. The requests appear in the Proxy tab, allowing for further actions such as forwarding, dropping, editing, or sending them to other Burp modules.
      * **Taking Control:**
      * **Capture and Logging:**
      * **WebSocket Support:**
      * **Logs and History:**

    ***
*   Repeater

    llows us to capture, modify, then resend the same request numerous times.

    *   Structure:

        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/a75f2b8a-d4c5-4193-92e5-450aa13b9ef1/Untitled.png)

        1. **Request List**: Located at the top left of the tab, it displays the list of Repeater requests. Multiple requests can be managed simultaneously, and each new request sent to Repeater will appear here.
        2. **Request Controls**: Positioned directly beneath the request list, these controls allow us to send a request, cancel a hanging request, and navigate through the request history.
        3. **Request and Response View**: Occupying the majority of the interface, this section displays the **Request** and **Response** views. We can edit the request in the Request view and then forward it, while the corresponding response will be shown in the Response view.
        4. **Layout Options**: Located at the top-right of the Request/Response view, these options enable us to customize the layout of the Request and Response views. The default setting is a side-by-side (horizontal) layout, but we can also choose a vertical layout or combine them in separate tabs.
        5. **Inspector**: Positioned on the right-hand side, the Inspector allows us to analyze and modify requests in a more intuitive manner than using the raw editor. We will explore this feature in a later task.
        6. **Target**: Situated above the Inspector, the Target field specifies the IP address or domain to which the requests are sent. When requests are sent to Repeater from other Burp Suite components, this field is automatically populated.

        ***
    *   Message Analysis Toolbar

        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/38722357-1e3c-41c8-9bb7-376cf007bd66/Untitled.png)

        1. **Pretty**: (default option) which takes the raw response and applies slight formatting enhancements to improve readability.
        2. **Raw**: displays the unmodified response directly received from the server without any additional formatting.
        3. **Hex**: examine the response in a byte-level representation, which is particularly useful when dealing with binary files.
        4. **Render**: visualize the page as it would appear in a web browser.

        `\` —> This functionality enables the display of characters that may not be visible with the **Pretty** or **Raw** options

        ***
    *   Inspector

        obtain a visually organized breakdown of requests and responses, as well as for experimenting to see how changes made using the higher-level Inspector affect the equivalent raw versions.

        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/a83ae4b9-850a-483f-a71e-f6822c98e948/Untitled.png)

        **Request Attributes:**

        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a85498c8-a854-4ca0-be5a-e5bb39c808e6/dc682991-9718-4cc7-8c38-50d1d7bb7f27/Untitled.png)

        modifying the desired resource to retrieve, changing the HTTP method from GET to another variant, or switching the protocol from HTTP/1 to HTTP/2

        1. **Request Query Parameters:** These refer to data sent to the server via the URL. For example, in a GET request like `https://admin.tryhackme.com/?redirect=false`, the query parameter **redirect** has a value of "false".
        2. **Request Body Parameters:** Similar to query parameters, but specific to POST requests. Any data sent as part of a POST request will be displayed in this section, allowing us to modify the parameters before resending.
        3. **Request Cookies:** This section contains a modifiable list of cookies sent with each request.
        4. **Request Headers:** It enables us to view, access, and modify (including adding or removing) any headers sent with our requests. Editing these headers can be valuable when examining how a web server responds to unexpected headers.
        5. **Response Headers:** This section displays the headers returned by the server in response to our request. It cannot be modified, as we have no control over the headers returned by the server. Note that this section becomes visible only after sending a request and receiving a response.

        ***

    Once a request has been captured in the Proxy module, we can send it to Repeater by either right-clicking on the request and selecting **Send to Repeater**, or by utilizing the keyboard shortcut `Ctrl + R`.

    Should we wish to modify any aspect of the request, we can simply type within the Request view and press **Send** once again. This action will update the Response view on the right accordingly. For instance, altering the **Connection** header to "open" instead of "close" yields a response with a **Connection** header containing the value "keep-alive":

    ***
*   intruder

    allows us to spray an endpoint with requests.

    ***
*   Decoder

    transforming data -- either in terms of decoding captured information, or encoding a payload prior to sending it to the target.

    ***
*   Comparer

    compare two pieces of data at either word or byte level.

    ***
*   **Sequencer**

    when assessing the randomness of tokens such as session cookie values or other supposedly random generated data. If the algorithm is not generating secure random values, then this could open up some devastating avenues for attack.

    ***

[Intelligence X](https://intelx.io/)
