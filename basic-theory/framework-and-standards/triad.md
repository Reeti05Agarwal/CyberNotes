# Triad

* Triage is a process used to prioritize incidents based on their urgency and importance.
* In security, triage helps analysts manage the large number of alerts they receive daily.
* The triage process involves:
  * Identifying and assessing alerts
  * Prioritizing alerts based on urgency
  * Investigating and collecting evidence
* Triage ensures that security teams can respond quickly to the most critical incidents.

### **Assign priority**

Once the alert has been properly assessed and verified as a genuine security issue, it needs to be prioritized accordingly. Incidents differ in their impact, size, and scope, which affects the response efforts. To manage time and resources, security teams must prioritize how they respond to various incidents because not all incidents are equal. Here are some factors to consider when determining the priority of an incident:

* **Functional impact:** Security incidents that target information technology systems impact the service that these systems provide to its users. For example, a ransomware incident can severely impact the confidentiality, availability, and integrity of systems. Data can be encrypted or deleted, making it completely inaccessible to users. Consider how an incident impacts the existing business functionality of the affected system.
* **Information impact:** Incidents can affect the confidentiality, integrity, and availability of an organization’s data and information. In a data exfiltration attack, malicious actors can steal sensitive data. This data can belong to third party users or organizations. Consider the effects that information compromise can have beyond the organization.
* **Recoverability:** How an organization recovers from an incident depends on the size and scope of the incident and the amount of resources available. In some cases, recovery might not be possible, like when a malicious actor successfully steals proprietary data and shares it publicly. Spending time, effort, and resources on an incident with no recoverability can be wasteful. It’s important to consider whether recovery is possible and consider whether it’s worth the time and cost.

**High Priority:**

* Alerts indicating a potential data breach or ransomware attack
* Alerts indicating a system outage or denial of service attack
* Alerts indicating unauthorized access to critical systems or data

**Medium Priority:**

* Alerts indicating suspicious activity, such as failed login attempts or unusual network traffic
* Alerts indicating a potential phishing or malware attack
* Alerts indicating a configuration issue or vulnerability that could be exploited

**Low Priority:**

* Alerts indicating non-critical events, such as system updates or software patches
* Alerts indicating false positives or benign activity
* Alerts indicating events that are already being handled by other teams

**Incident Response Lifecycle: Phase 3 - Containment, Eradication, and Recovery**

**Containment**

* Limit and prevent additional damage caused by an incident.
* Isolate affected systems to prevent the spread of threats.

**Eradication**

* Remove all traces of the incident from affected systems.
* Perform vulnerability tests and apply patches to vulnerabilities.

**Recovery**

* Return affected systems to normal operations.
* Reimage affected systems, reset passwords, and adjust network configurations.

**Additional Notes**

* The incident response lifecycle is cyclical, and multiple incidents can happen over time.
* Security teams may need to revisit other phases of the lifecycle for additional investigations.

The core functions of the NIST Cybersecurity Framework that integrate with the incident response lifecycle are:

* **Respond:** This function includes the activities necessary to detect, analyze, and respond to security incidents.
* **Recover:** This function includes the activities necessary to restore systems and data to normal operations after a security incident.

The incident response lifecycle and the NIST Cybersecurity Framework are closely aligned, as both frameworks emphasize the importance of preparing for, responding to, and recovering from security incidents.

Here is a table that shows how the phases of the incident response lifecycle map to the core functions of the NIST Cybersecurity Framework:

| Incident Response Lifecycle Phase | NIST Cybersecurity Framework Core Function |
| --------------------------------- | ------------------------------------------ |
| Detection                         | Respond                                    |
| Containment                       | Respond                                    |
| Eradication                       | Respond                                    |
| Recovery                          | Recover                                    |

By following the incident response lifecycle and implementing the core functions of the NIST Cybersecurity Framework, organizations can improve their ability to prevent, detect, and respond to security incidents.

### **Site resilience**

**Resilience** is the ability to prepare for, respond to, and recover from disruptions. Organizations can design their systems to be resilient so that they can continue delivering services despite facing disruptions. An example is site resilience, which is used to ensure the availability of networks, data centers, or other infrastructure when a disruption happens. There are three types of recovery sites used for site resilience:

* **Hot sites**: A fully operational facility that is a duplicate of an organization's primary environment. Hot sites can be activated immediately when an organization's primary site experiences failure or disruption.
* **Warm sites**: \*\*\*\*A facility that contains a fully updated and configured version of the hot site. Unlike hot sites, warm sites are not fully operational and available for immediate use but can quickly be made operational when a failure or disruption occurs.
* **Cold sites**: \*\*\*\*A backup facility equipped with some of the necessary infrastructure required to operate an organization's site. When a disruption or failure occurs, cold sites might not be ready for immediate use and might need additional work to be operational.

**Post-Incident Activity**

The post-incident activity phase of the incident response lifecycle involves reviewing an incident to identify areas for improvement during incident handling. During this phase, different types of documentation get updated or created, including the final report, which provides a comprehensive review of an incident, including a timeline and details of all events related to the incident, as well as recommendations for future prevention.

**Lessons Learned Meeting**

A lessons learned meeting is held within two weeks after an incident to review the incident and determine what happened, what actions were taken, and how well the actions worked. The final report is used as the main reference document during this meeting. The goal of the discussions in a lessons learned meeting is to share ideas and information about the incident and how to improve future response efforts.

**Incident Reviews**

Incident reviews can reveal human errors before detection and during response. Blaming someone for an action they did or didn't do should be avoided. Instead, security teams can view this as an opportunity to learn from what happened and improve.

The main types of documentation that get updated or created during the post-incident activity phase are:

* **Final report:** This document provides a comprehensive review of an incident, including a timeline and details of all events related to the incident, as well as recommendations for future prevention.
* **Lessons learned:** This document captures the key takeaways from an incident and identifies areas for improvement in future incident response efforts.
* **Technical documentation:** This document may include updates to security policies, procedures, and playbooks based on the lessons learned from the incident.

Other types of documentation that may be updated or created during the post-incident activity phase include:

* **Incident response plan:** This document may be updated to reflect the lessons learned from the incident.
* **Security awareness training materials:** These materials may be updated to include information about the incident and how to prevent similar incidents in the future.
* **Knowledge base articles:** These articles may be created to document the lessons learned from the incident and provide guidance on how to prevent similar incidents in the future.

**ncident Investigation and Response**

* **Detection and Analysis**
  * Purpose of detection
  * Indicators of compromise
* **Incident Response**
  * Plans and processes
  * Documentation and triage
  * Containment, eradication, and recovery
* **Post-Incident Actions**
  * Final reports
  * Timelines
  * Post-incident reviews
