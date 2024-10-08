# Suricata

[Home - Suricata](https://suricata.io/)

*   Resourses

    * [Suricata user guide](https://suricata.readthedocs.io/en/latest/index.html)
    * [Suricata features](https://suricata.io/features/)
    * [Rule management](https://suricata.readthedocs.io/en/latest/rule-management/suricata-update.html)
    * [Rule performance analysis](https://suricata.readthedocs.io/en/latest/configuration/suricata-yaml.html#engine-analysis-and-profiling)
    * [Suricata threat hunting webinar](https://youtu.be/kaDGolhTu94)
    * [Introduction to writing Suricata rules](https://youtu.be/tvoqFBVSShA)
    * [Eve.json jq examples](https://suricata.readthedocs.io/en/latest/output/eve/eve-json-examplesjq.html)

    ***
* Suricata is an open-source signature-based IDS that allows you to examine and customize signatures.
* Signatures in Suricata consist of an action (e.g., alert), a header (e.g., HTTP), source and destination IP addresses and ports, and rule options (e.g., message, flow, content).
* The content option in Suricata allows you to inspect the content of a packet for specific text or patterns.
* Every environment is different, so signatures should be tested and tailored to improve detection and reduce false positives.
* Suricata logs events for further analysis and investigation.

The key components of a signature in Suricata are:

* **Action:** The action to be taken when the signature is matched, such as alert, drop, or reject.
* **Header:** The protocol or service that the signature applies to, such as HTTP, FTP, or SSH.
* **Source and destination IP addresses and ports:** The IP addresses and ports of the source and destination of the traffic that the signature matches.
* **Rule options:** Additional options that can be used to customize the signature, such as the message to be displayed when the signature is matched, the direction of the traffic that the signature matches, and the content of the packet that the signature matches.

For example, the following signature matches any HTTP traffic from the home network to the external network that contains the text "GET":

```
alert http $HOME_NET any -> $EXTERNAL_NET any (msg:"GET on wire"; flow:established; content:"GET";)

```

This signature would generate an alert any time Suricata observes the text "GET" in an HTTP connection from the home network to the external network.

**Log Types in Suricata**

Suricata generates two types of log data:

* **Alert logs:** Contain information relevant to security investigations, such as the output of signatures that have triggered an alert.
  * Event type: alert
  * Details: IP addresses, protocol, signature message and ID
* **Network telemetry logs:** Contain information about network traffic flows, such as connections being made to specific ports.
  * Event type: http log
  * Details: HTTP request details, website accessed, user agent, content type

There are two log files that Suricata generates when alerts are triggered:

* **eve.json**: The eve.json file is the standard Suricata log file. This file contains detailed information and metadata about the events and alerts generated by Suricata stored in JSON format. For example, events in this file contain a unique identifier called flow\_id which is used to correlate related logs or alerts to a single network flow, making it easier to analyze network traffic. The eve.json file is used for more detailed analysis and is considered to be a better file format for log parsing and SIEM log ingestion.
* **fast.log**: The fast.log file is used to record minimal alert information including basic IP address and port details about the network traffic. The fast.log file is used for basic logging and alerting and is considered a legacy file format and is not suitable for incident response or threat hunting tasks.
* **Identify the source and scope of a security incident:** By correlating alerts with network traffic data.
* **Determine the impact of an incident:** By analyzing the affected systems and data.
* **Identify potential vulnerabilities:** By examining network traffic patterns and identifying suspicious activity.
* **Develop mitigation strategies:** By understanding the nature and scope of the incident.

Rule order refers to the order in which rules are evaluated by Suricata. Rules are processed in the order in which they are defined in the configuration file. However, Suricata processes rules in a different default order: pass, drop, reject, and alert. Rule order affects the final verdict of a packet especially when conflicting actions such as a drop rule and an alert rule both match on the same packet.

* The `sample.pcap` file is a packet capture file that contains an example of network traffic data, which you’ll use to test the Suricata rules. This will allow you to simulate and repeat the exercise of monitoring network traffic.
* The `custom.rules` file contains a custom rule when the lab activity starts. You’ll add rules to this file and run them against the network traffic data in the `sample.pcap` file.
* The `fast.log` file will contain the alerts that Suricata generates. The `fast.log` file is empty when the lab starts. Each time you test a rule, or set of rules, against the sample network traffic data, Suricata adds a new alert line to the `fast.log` file when all the conditions in any of the rules are met. The `fast.log` file can be located in the `/var/log/suricata` directory after Suricata runs.The `fast.log` file is considered to be a depreciated format and is not recommended for incident response or threat hunting tasks but can be used to perform quick checks or tasks related to quality assurance.
* The `eve.json` file is the main, standard, and default log for events generated by Suricata. It contains detailed information about alerts triggered, as well as other network telemetry events, in JSON format. The `eve.json` file is generated when Suricate runs, and can also be located in the `/var/log/suricata` directory.

```c
alert http $HOME_NET any -> $EXTERNAL_NET any (msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;)
```

The **action** is the first part of the signature. It determines the action to take if all conditions are met.

Actions differ across network intrusion detection system (NIDS) rule languages, but some common actions are `alert`, `drop`, `pass`, and `reject`.

Using our example, the file contains a single `alert` as the action. The `alert` keyword instructs to alert on selected network traffic. The IDS will inspect the traffic packets and send out an alert in case it matches.

Note that the `drop` action also generates an alert, but it drops the traffic. A `drop` action only occurs when Suricata runs in IPS mode.

The `pass` action allows the traffic to pass through the network interface. The pass rule can be used to override other rules. An exception to a drop rule can be made with a pass rule. For example, the following rule has an identical signature to the previous example, except that it singles out a specific IP address to allow only traffic from that address to pass:

The `reject` action does not allow the traffic to pass. Instead, a TCP reset packet will be sent, and Suricata will drop the matching packet. A TCP reset packet tells computers to stop sending messages to each other.

The next part of the signature is the **header**. The header defines the signature’s network traffic, which includes attributes such as protocols, source and destination IP addresses, source and destination ports, and traffic direction.

The next field after the action keyword is the protocol field. In our example, the protocol is `http`, which determines that the rule applies only to HTTP traffic.

The parameters to the protocol `http` field are `$HOME_NET any -> $EXTERNAL_NET any`. The arrow indicates the direction of the traffic coming from the `$HOME_NET` and going to the destination IP address `$EXTERNAL_NET`.

`$HOME_NET` is a Suricata variable defined in `/etc/suricata/suricata.yaml` that you can use in your rule definitions as a placeholder for your local or home network to identify traffic that connects to or from systems within your organization.

In this lab `$HOME_NET` is defined as the 172.21.224.0/20 subnet.

The word `any` means that Suricata catches traffic from any port defined in the `$HOME_NET` network.

_The `$` symbol indicates the start of a variable. Variables are used as placeholders to store values._

The many available **rule options** allow you to customize signatures with additional parameters. Configuring rule options helps narrow down network traffic so you can find exactly what you’re looking for. As in our example, rule options are typically enclosed in a pair of parentheses and separated by semicolons.

Let's further examine the rule options in our example:

* The `msg:` option provides the alert text. In this case, the alert will print out the text `“GET on wire”`, which specifies why the alert was triggered.
* The `flow:established,to_server` option determines that packets from the client to the server should be matched. (In this instance, a server is defined as the device responding to the initial SYN packet with a SYN-ACK packet.)
* The `content:"GET"` option tells Suricata to look for the word `GET` in the content of the `http.method` portion of the packet.
* The `sid:12345` (signature ID) option is a unique numerical value that identifies the rule.
* The `rev:3` option indicates the signature's revision which is used to identify the signature's version. Here, the revision version is 3.

Run `suricata` using the `custom.rules` and `sample.pcap` files:

```c
sudo suricata -r sample.pcap -S custom.rules -k none
```

* The `r sample.pcap` option specifies an input file to mimic network traffic. In this case, the `sample.pcap` file.
* The `S custom.rules` option instructs Suricata to use the rules defined in the `custom.rules` file.
* The `k none` option instructs Suricata to disable all checksum checks.
