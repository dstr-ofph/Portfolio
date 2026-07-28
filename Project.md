Investigating an Agent Tesla Malware Outbreak: A SOC Tier 2 Analysis
1. Executive Summary/Overview
In this project, I stepped into the role of a Tier 2 Security Operations Center (SOC) Analyst to investigate a simulated Agent Tesla malware outbreak. By analyzing a suspicious email and network packet captures, I successfully traced the attack from the initial phishing hook all the way to its data exfiltration attempts. Ultimately, this project delivered a complete incident report packed with actionable Indicators of Compromise (IOCs), demonstrating how rapid, thorough network analysis can shut down credential theft and secure organizational assets.
2. Core Technologies/Applied Technologies
* Wireshark (Network Protocol Analyzer)
* Email Header & .eml Analysis Tools
* Packet Capture (.pcap) Forensics
* Cryptographic Hash Analysis
* DNS & FTP Traffic Analysis
* Indicators of Compromise (IOC) Extraction Workflows
3. Situation
A staff member raised an alarm after noticing unusual computer behavior shortly after opening an email attachment from an allegedly known supplier. The compromised workstation rapidly began showing signs of sluggish performance and making suspicious outbound network connections, specifically involving unrecognized FTP traffic. The security team suspected an infection by Agent Tesla—a notorious spyware trojan known for stealing credentials—and needed immediate, clear-cut answers regarding the scope of the breach and the methods used by the attacker.
4. Task
Acting as the lead SOC Analyst, my objective was to forensically examine the available evidence, which consisted of the raw email file (.eml) and network traffic logs (.pcap). My core responsibilities were to determine the exact attack chain, extract crucial Indicators of Compromise (IOCs), analyze how the malware behaved on the network, and compile a comprehensive incident timeline to guide the remediation team.
5. Actions
Safe Email and Payload Interrogation
To start the investigation safely, I parsed the .eml file without executing any payloads. I analyzed the email headers to expose sender spoofing techniques and safely extracted the malicious attachment's cryptographic hashes, establishing our first critical indicators.
[Figure 1: Analysis of the suspicious email headers revealing sender spoofing techniques] - [Image link: ./images/email_header_analysis.png]
Mapping Attacker Infrastructure via DNS
Using Wireshark, I cracked open the network packet capture (.pcap) to monitor the malware's post-infection behavior. By filtering for DNS requests, I was able to map out the external domains the malware was attempting to contact for command and control instructions.
[Figure 2: Wireshark capture showing malicious DNS queries to external domains] - [Image link: ./images/wireshark_dns_queries.png]
Uncovering the Exfiltration Pathway
Following the trail of suspicious outbound connections, I isolated unauthorized FTP sessions within the network traffic. This step was crucial, as it revealed exactly how the Agent Tesla malware was actively attempting to smuggle stolen user credentials out of the internal network.
[Figure 3: Captured FTP session exposing the data exfiltration pathway] - [Image link: ./images/ftp_exfiltration_stream.png]
Harvesting Actionable Intelligence
With the network pathways exposed, I gathered the crucial puzzle pieces—malicious IP addresses, domain names, and file hashes. I extracted and cataloged these Indicators of Compromise (IOCs) so they could be immediately used by defensive systems to block the threat.
[Figure 4: A compiled list of actionable IOCs extracted from the investigation] - [Image link: ./images/extracted_iocs_list.png]
Reconstructing the Kill Chain
Finally, I synthesized all the forensic data to build a cohesive narrative. I documented every phase of the attack lifecycle from the initial phishing delivery to the final exfiltration attempt, producing a clear, actionable case study for security stakeholders.
[Figure 5: The final incident response timeline mapping the malware's lifecycle] - [Image link: ./images/incident_timeline_report.png]
6. Result
The project was a resounding success, culminating in the complete reconstruction of the Agent Tesla attack lifecycle. Qualitatively, the investigation transformed raw, complex network data and email files into a clear, actionable narrative that illuminated the attacker's specific tradecraft. Quantitatively, the process yielded a comprehensive set of verified Indicators of Compromise (IOCs)—including specific file hashes, malicious domains, and IP addresses—ready to be ingested by firewalls and endpoint protection platforms to proactively prevent future compromise.
7. Frameworks & Standards
* MITRE ATT&CK Framework: The investigation directly aligned with this framework by mapping the adversary's behaviors, specifically identifying tactics like Initial Access (via Phishing) and Exfiltration (via Alternative Protocol - FTP).
* NIST Computer Security Incident Handling Guide (SP 800-61): The methodology adhered to NIST standards for the 'Detection and Analysis' phase, ensuring digital evidence was handled safely, documented thoroughly, and logically analyzed to determine the incident's true scope.
* Nigeria Data Protection Act (NDPA) 2023: By swiftly identifying the exfiltration of sensitive information via FTP and extracting IOCs to halt it, this analysis supports the NDPA's strict mandate for data controllers to ensure the security, integrity, and confidentiality of personal data against unauthorized access or breaches.
8. Organizational Benefits
* Reduced Breach Impact: Rapid identification of the FTP exfiltration channel minimizes potential data loss and prevents compromised employee credentials from being weaponized against the company.
* Proactive Defense Enhancements: The extracted IOCs can be fed directly into the organization's security appliances, effectively immunizing the network against identical future campaigns.
* Cost and Time Efficiency: Handling the investigation using a structured internal process drastically cuts down incident response times and reduces the need for expensive external forensic consultants.