# Google Chronicle

[Data ingestion to Chronicle overview  |  Google Cloud](https://cloud.google.com/chronicle/docs/data-ingestion-flow)

* cloud-native SIEM tool that stores security data for search and analysis
* Chronicle enables searching and filtering of log data using its search field.
* YARA-L language is utilized by Chronicle to define rules for detection within ingested log data.
* YARA-L allows the creation of rules for detecting specific activities, such as data exfiltration.
* Searchable fields in Chronicle include hostname, domain, IP, URL, email, username, and file hash.
* Two types of searches are available: UDM search, which looks through normalized data, and raw log search, which examines unnormalized logs.
* Normalization during the SIEM process extracts and formats relevant information from raw logs for easier searching.
* Raw log search may be necessary to find data not included in normalized logs or to troubleshoot data ingestion issues.\\

<details>

<summary>Yara-L</summary>



* YARA-L is a computer language used to create rules for searching through ingested log data.
* It allows you to define rules for detection, such as detecting specific activities related to the exfiltration of valuable data.
* Using Chronicle's search field, you can search for fields like hostname, domain, IP, URL, email, username, or file hash.
* You can enter different types of searches, including UDM search (Unified Data Model) and raw log search.
* UDM search searches through normalized data, while raw log search searches through logs that have not been normalized.
* A reason we might need to search raw logs is to find data that may not have been included in the normalized logs, like specific fields that have not been normalized, or to troubleshoot data ingestion problems.

</details>

<details>

<summary>UDM Search</summary>



Unified Data Model

Let's examine a UDM search for a failed login using Chronicle. First, let's click on the structured query builder icon, so that we can perform a UDM search. I'll type in the search:

```
metadata.event_type = "USER_LOGIN" AND security_result.action = "BLOCK"
```

Since we are searching for normalized data, we need to specify a search that uses UDM format. UDM events have a set of common fields.

* The metadata.event\_type field specifies the type of event being searched, such as authentication activity.
* The search query includes logical operators like AND to ensure both specified terms are contained in the results.
* The security\_result.action field indicates the security action taken, such as allow or block.
* Upon pressing the query button, the search focuses on normalized data.
* Search results include a timeline graph visualizing events like failed logins over time, aiding in pattern recognition. Each event in the search results is associated with a timestamp and asset (device name), providing context.
* Clicking on an event allows access to the associated raw log for detailed investigation.
* Quick Filters on the left offer additional fields or values for refining search results, such as target IP addresses. Utilizing Quick Filters helps in locating specific data efficiently and saving time during analysis.

***

*   **Entities**:

    Entities are also known as nouns. All UDM events must contain at least one entity. This field provides additional context about a device, user, or process that’s involved in an event. For example, a UDM event that contains entity information includes the details of the origin of an event such as the hostname, the username, and IP address of the event.
*   **Event metadata**:

    This field provides a basic description of an event, including what type of event it is, timestamps, and more.
*   **Network metadata**: \*\*\*\*

    This field provides information about network-related events and protocol details.
*   **Security results**: \*\*\*\*

    This field provides the security-related outcome of events. An example of a security result can be an antivirus software detecting and quarantining a malicious file by reporting "virus detected and quarantined."

</details>

<details>

<summary>Raw Log Search</summary>



* If data cannot be found using normalized search, the option of searching raw logs is available.
* Raw log search examines logs that have not undergone normalization.
* Raw logs are processed during normalization, extracting and formatting relevant information for easier searching.
* Raw log search may be necessary to find data not included in normalized logs, such as specific unnormalized fields.
* It can also be used to troubleshoot data ingestion issues during the SIEM process.

</details>

1. **VT CONTEXT**: This section provides the VirusTotal information available for the domain.
2. **WHOIS**: This section provides a summary of information about the domain using WHOIS, a free and publicly available directory that includes information about registered domain names, such as the name and contact information of the domain owner. In cybersecurity, this information is helpful in assessing a domain's reputation and determining the origin of malicious websites.
3. **Prevalence**: This section provides a graph which outlines the historical prevalence of the domain. This can be helpful when you need to determine whether the domain has been accessed previously. Usually, less prevalent domains may indicate a greater threat.
4. **RESOLVED IPS**: This insight card provides additional context about the domain, such as the IP address that maps to [**signin.office365x24.com**](http://signin.office365x24.com), which is **40.100.174.34**. Clicking on this IP will run a new search for the IP address in Chronicle. Insight cards can be helpful in expanding the domain investigation and further investigating an indicator to determine whether there is a broader compromise.
5. **SIBLING DOMAINS**: This insight card provides additional context about the domain. Sibling domains share a common top or parent domain. For example, here the sibling domain is listed as [**login.office365x24.com**](http://login.office365x24.com), which shares the same top domain [**office365x24.com**](http://office365x24.com) with the domain you're investigating: [**signin.office365x24.com**](http://signin.office365x24.com).
6. **ET INTELLIGENCE REP LIST**: This insight card includes additional context on the domain. It provides threat intelligence information, such as other known threats related to the domains using ProofPoint's Emerging Threats (ET) Intelligence Rep List.
7. Click **TIMELINE**. This tab provides information about the events and interactions made with this domain. Click **EXPAND ALL** to reveal the details about the HTTP requests made including **GET** and **POST** requests. A GET request retrieves data from a server while a POST request submits data to a server.
8. Click **ASSETS**. This tab provides a list of the assets that have accessed the domain.











