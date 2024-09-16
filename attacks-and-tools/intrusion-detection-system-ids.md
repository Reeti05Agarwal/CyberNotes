# Intrusion Detection System (IDS)

An **intrusion detection system** (IDS) is an application that monitors system activity and alerts on possible intrusions. The system scans and analyzes network packets, which carry small amounts of data through a network. The small amount of data makes the detection process easier for an IDS to identify potential threats to sensitive data. Other occurrences an IDS might detect can include theft and unauthorized access.

A **signature** specifies the rules that an IDS uses to monitor activity. Signature analysis is one of the most common methods of detection used by IDS tools.

Suricata

*   **Intrusion Detection System (IDS)**:

    Monitors system and network activity for suspicious activity.

    Sends alerts when unusual activity is detected.
*   **Intrusion Prevention System (IPS)**:

    Has all the capabilities of an IDS, plus the ability to take action to stop intrusions.
*   **Host-based IDS**

    Monitors the activity of the host on which it's installed. It detects suspicious activity and generates alerts.

    A **host-based intrusion detection system (HIDS)** is an application that monitors the activity of the host on which it's installed. A HIDS is installed as an agent on a host. A host is also known as an **endpoint**, \*\*\*\*which is any device connected to a network like a computer or a server.

    Typically, HIDS agents are installed on all endpoints and used to monitor and detect security threats. A HIDS monitors internal activity happening on the host to identify any unauthorized or abnormal behavior. If anything unusual is detected, such as the installation of an unauthorized application, the HIDS logs it and sends out an alert.

    In addition to monitoring inbound and outbound traffic flows, HIDS can have additional capabilities, such as monitoring file systems, system resource usage, user activity, and more.

    This diagram shows a HIDS tool installed on a computer. The dotted circle around the host indicates that it is only monitoring the local activity on the single computer on which it’s installed.

    [https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/r9hBQHsQSv-hult8KB1V8g\_17a68a6257c143738588e048ca8d26f1\_FhxPKoFNfXgXc6ReM\_Srb2o974QJ0U-ULsPViUoB-bhM\_iCgEJA4kCxBBaXg8V\_I8OgPIpF5g77EffByf9aub\_pTG33UzSLum4eyKCK7YZPXGvZjqG1jLW-bJ4yozWlzoOSJ7i99ZiyAfKfNBe0DyFMKE3UyQv--RRTEACIegsbPdyqlv4gHQAGRdIyMMQ?expiry=1711497600000\&hmac=Rx3K\_YlHYubbEVjhJFKoX9nwI6CmbM1la8vxJ2JXLtY](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/r9hBQHsQSv-hult8KB1V8g\_17a68a6257c143738588e048ca8d26f1\_FhxPKoFNfXgXc6ReM\_Srb2o974QJ0U-ULsPViUoB-bhM\_iCgEJA4kCxBBaXg8V\_I8OgPIpF5g77EffByf9aub\_pTG33UzSLum4eyKCK7YZPXGvZjqG1jLW-bJ4yozWlzoOSJ7i99ZiyAfKfNBe0DyFMKE3UyQv--RRTEACIegsbPdyqlv4gHQAGRdIyMMQ?expiry=1711497600000\&hmac=Rx3K\_YlHYubbEVjhJFKoX9nwI6CmbM1la8vxJ2JXLtY)

    ***
*   **Network-based IDS**

    Collects and analyzes network traffic and network data. It detects suspicious or unusual network activity and generates alerts.

    A **network-based intrusion detection system** **(NIDS)** is an application that collects and monitors network traffic and network data. NIDS software is installed on devices located at specific parts of the network that you want to monitor. The NIDS application inspects network traffic from different devices on the network. If any malicious network traffic is detected, the NIDS logs it and generates an alert.

    This diagram shows a NIDS that is installed on a network. The highlighted circle around the server and computers indicates that the NIDS is installed on the server and is monitoring the activity of the computers.

    ![https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/m2NQ9waXQzm\_kmnrpieaAQ\_081c3ddbccb64cf8aa0ad09806fdf8f1\_CS\_R-137\_NIDS.png?expiry=1711497600000\&hmac=z1fqm8yAF5lATe1uyQikNnA\_GyywsFR8nTQxMeOIzCU](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/m2NQ9waXQzm\_kmnrpieaAQ\_081c3ddbccb64cf8aa0ad09806fdf8f1\_CS\_R-137\_NIDS.png?expiry=1711497600000\&hmac=z1fqm8yAF5lATe1uyQikNnA\_GyywsFR8nTQxMeOIzCU)

    Using a combination of HIDS and NIDS to monitor an environment can provide a multi-layered approach to intrusion detection and response. HIDS and NIDS tools provide a different perspective on the activity occurring on a network and the individual hosts that are connected to it. This helps provide a comprehensive view of the activity happening in an environment.

    ***
*   **Detection Methods**

    IDS uses different detection methods, including signature analysis.
*   **Signature Analysis**

    A detection method that uses a set of rules to identify events of interest. If the activity matches the rules, the IDS logs it and sends out an alert.

    **Signature analysis**, or signature-based analysis, is a detection method that is used to find events of interest. A **signature** is a pattern that is associated with malicious activity. Signatures can contain specific patterns like a sequence of binary numbers, bytes, or even specific data like an IP address.

    Previously, you explored the Pyramid of Pain, which is a concept that prioritizes the different types of **indicators of compromise** (IoCs) associated with an attack or threat, such as IP addresses, tools, tactics, techniques, and more. IoCs and other indicators of attack can be useful for creating targeted signatures to detect and block attacks.

    Different types of signatures can be used depending on which type of threat or attack you want to detect. For example, an anti-malware signature contains patterns associated with malware. This can include malicious scripts that are used by the malware. IDS tools will monitor an environment for events that match the patterns defined in this malware signature. If an event matches the signature, the event gets logged and an alert is generated.

    #### **Advantages**

    * **Low rate of false positives:** Signature-based analysis is very efficient at detecting known threats because it is simply comparing activity to signatures. This leads to fewer false positives. Remember that a **false positive** is an alert that incorrectly detects the presence of a threat.

    #### **Disadvantages**

    * **Signatures can be evaded:** Signatures are unique, and attackers can modify their attack behaviors to bypass the signatures. For example, attackers can make slight modifications to malware code to alter its signature and avoid detection.
    * **Signatures require updates:** Signature-based analysis relies on a database of signatures to detect threats. Each time a new exploit or attack is discovered, new signatures must be created and added to the signature database.
    * **Inability to detect unknown threats:** Signature-based analysis relies on detecting known threats through signatures. Unknown threats can't be detected, such as new malware families or **zero-day** attacks, which are exploits that were previously unknown.

    ***
*   Anomaly-based analysis

    **Anomaly-based analysis** is a detection method that identifies abnormal behavior. There are two phases to anomaly-based analysis: a training phase and a detection phase. In the training phase, a baseline of normal or expected behavior must be established. Baselines are developed by collecting data that corresponds to normal system behavior. In the detection phase, the current system activity is compared against this baseline. Activity that happens outside of the baseline gets logged, and an alert is generated.

    #### **Advantages**

    * **Ability to detect new and evolving threats:** Unlike signature-based analysis, which uses known patterns to detect threats, anomaly-based analysis _can_ detect unknown threats.

    #### **Disadvantages**

    * **High rate of false positives:** Any behavior that deviates from the baseline can be flagged as abnormal, including non-malicious behaviors. This leads to a high rate of false positives.
    * **Pre-existing compromise:** The existence of an attacker during the training phase will include malicious behavior in the baseline. This can lead to missing a pre-existing attacker.

    ***
*   **IDS Logs**

    IDS technologies record the information of the devices, systems, and networks which they monitor as IDS logs. IDS logs can then be sent, stored, and analyzed in a centralized log repository like a SIEM.
* **Popular IDS/IPS Tools:**
  * Snort
  * Zeek
  * Kismet
  * Sagan
  * Suricata
*   **Detection categories**

    As a security analyst, you will investigate alerts that an IDS generates. There are four types of detection categories you should be familiar with:

    *   **A true positive**

        alert that correctly detects the presence of an attack.
    *   **A true negative**

        where there is no detection of malicious activity. This is when no malicious activity exists and no alert is triggered.
    *   **A false positive**

        alert that incorrectly detects the presence of a threat. This is when an IDS identifies an activity as malicious, but it isn't. False positives are an inconvenience for security teams because they spend time and resources investigating an illegitimate alert.
    *   **A false negative**

        where the presence of a threat is not detected. This is when malicious activity happens but an IDS fails to detect it. False negatives are dangerous because security teams are left unaware of legitimate attacks that they can be vulnerable to.

    ***

    *   **Endpoint detection and response** (**EDR**)

        An application that monitors an endpoint for malicious activity. EDR tools are installed on endpoints. Remember that an **endpoint** is any device connected on a network. Examples include end-user devices, like computers, phones, tablets, and more.

        EDR tools monitor, record, and analyze endpoint system activity to identify, alert, and respond to suspicious activity. Unlike IDS or IPS tools, EDRs collect endpoint activity data and perform _behavioral analysis_ to identify threat patterns happening on an endpoint. Behavioral analysis uses the power of machine learning and artificial intelligence to analyze system behavior to identify malicious or unusual activity. EDR tools also use _automation_ to stop attacks without the manual intervention of security professionals. For example, if an EDR detects an unusual process starting up on a user’s workstation that normally is not used, it can automatically block the process from running.

        Tools like Open EDR®, Bitdefender™ Endpoint Detection and Response, and FortiEDR™ are examples of EDR tools.
    *   **User and Entity Behavior Analytics (UEBA)**

        UEBA is a tool that analyzes user and entity behavior to detect anomalous or malicious activity.
    *   **Network Traffic Analysis (NTA)**

        NTA is a tool that analyzes network traffic to detect suspicious or malicious activity.
    *   **Log Management Systems (LMS)**

        LMS is a tool that collects, stores, and analyzes log data from multiple sources. It can be used to detect and respond to security incidents.
    * **Security Information and Event Management (SIEM)**

    ***
*   **Alert Management:**

    Alerts from IDS/IPS systems are typically managed using Security Information and Event Management (SIEM) tools.
*   Signatures in Network Intrusion Detection Systems (NIDS)

    Signatures specify detection rules for NIDS to identify network intrusions.

    NIDS rules consist of three components: Action: Determines the response when rule criteria are met (e.g., alert, pass, reject). Header: Defines the network traffic to be monitored (e.g., source/destination IP addresses, ports, protocols). Rule Options: Customizes signatures with additional parameters (e.g., matching specific packet content). Example Signature:

    alert tcp 10.120.170.17 any -> 133.113.202.181 80 (msg:"This is a message"; sid:1; rev:1);

    ```
    Action: Alert on suspicious traffic.
    Header: Traffic from source IP 10.120.170.17 on any port to destination IP 133.113.202.181 on port 80.
    Rule Options:
    	msg: Alert message text.
    	sid: Signature ID.
    	rev: Revision number.

    ```

    To detect suspicious traffic originating from specific IP addresses using the header component in a Network Intrusion Detection System (NIDS) rule, you can specify the source IP address in the header. Here's an example:

    alert tcp 10.120.170.17 any -> 133.113.202.181 80 (msg:"Suspicious traffic from 10.120.170.17"; sid:1; rev:1);

    In this example, the header specifies that the rule should monitor for TCP traffic originating from the source IP address 10.120.170.17 and going to any destination IP address on port 80. If traffic matching these criteria is detected, the NIDS will generate an alert with the message "Suspicious traffic from 10.120.170.17".

    You can also use the header component to specify multiple IP addresses or ranges of IP addresses. For example, the following rule would detect suspicious traffic originating from any IP address in the range 10.0.0.0 to 10.255.255.255:

    alert tcp 10.0.0.0/16 any -> 133.113.202.181 80 (msg:"Suspicious traffic from 10.0.0.0/16"; sid:1; rev:1); By using the header component to specify specific IP addresses or ranges of IP addresses, you can effectively detect and monitor suspicious traffic originating from those sources.

    Rule options can be used to customize signatures in NIDS in a variety of ways. Here are a few examples:

    Match specific content in network packets: Rule options can be used to match specific content within network packets, such as the payload or header information. This allows you to create signatures that detect specific types of attacks or malicious activity. For example, you could create a rule option to match a specific string of text in the payload of a packet, or to match a specific pattern in the header information. Set thresholds and limits: Rule options can be used to set thresholds and limits on various parameters, such as the number of packets per second that match a signature or the size of a packet. This allows you to fine-tune your signatures to reduce false positives and focus on the most critical threats. Configure actions: Rule options can be used to configure the actions that are taken when a signature is matched. For example, you could configure a signature to generate an alert, block the traffic, or take other actions. Add context and metadata: Rule options can be used to add context and metadata to signatures, such as the name of the analyst who created the signature or the date it was created. This information can be helpful for managing and tracking your signatures. By using rule options, you can customize signatures to meet your specific needs and requirements. This allows you to create more effective and efficient NIDS rules that can help you detect and prevent security threats.

    Here is an example of a rule option that matches a specific string of text in the payload of a packet:

    alert tcp any any -> any any (msg:"Suspicious traffic containing the string 'attack'"; content:"attack"; sid:1; rev:1); This rule will generate an alert if it detects any TCP traffic that contains the string "attack" in the payload.

    Here is an example of a rule option that sets a threshold on the number of packets per second that match a signature:

    alert tcp any any -> any any (msg:"Suspicious traffic exceeding 100 packets per second"; count:100; sid:1; rev:1); This rule will generate an alert if it detects more than 100 packets per second that match the signature.

    By using rule options, you can create more sophisticated and effective NIDS signatures that can help you protect your network from security threats.
