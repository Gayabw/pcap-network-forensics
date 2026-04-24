# PCAP Network Packet Capture Analysis using Wireshark
---
## 📌 Overview
This project focuses on network forensics and incident response by analyzing packet capture (PCAP) files to identify malicious activity and reconstruct attack timelines.

- Performed deep packet inspection using Wireshark
- Identified Indicators of Compromise (IOCs)
- Reconstructed attack timeline using packet level evidence
- Delivered a forensic report with evidence-backed findings
---
## 🎯 Objectives
- Identify malicious or suspicious traffic
- Apply forensic investigation workflow
- Analyze packet-level behavior
- Reconstruct the sequence of an attack
- Identify attacker techniques and artifacts
- Produce evidence-based reporting
- Recommend mitigation strategies
---
## 🛠️ Tools & Technologies
- Wireshark
- TCP/IP, DNS, HTTP, HTTPS
- PCAP Analysis Techniques
- Network Forensics Methodologies
---
## 🔍 Methodology
1. Imported PCAP files into Wireshark
2. Applied filters to isolate suspicious traffic: http, dns, tcp.stream
3. Followed packet streams to reconstruct sessions
4. Identified anomalies in DNS queries and HTTP requests/responses
5. Extracted artifacts such as malicious domains, suspicious IP addresses and payload indicators
6. Documented findings for reporting
   
---
## ⚙️ Investigation Steps
1. Initial Traffic Inspection
- Loaded PCAP file into Wireshark
- Reviewed overall traffic patterns
- Identified unusual spikes and suspicious protocols

2. Protocol-Based Filtering
- Applied filters to narrow down traffic:
- HTTP traffic inspection
- DNS request analysis
- Focused on suspicious external communications

3. Stream Analysis
- Used Follow TCP Stream to inspect full conversations
- Reconstructed communication between victim and attacker
- Identified potential payload delivery

4. DNS Analysis
- Investigated domain resolution patterns
- Detected suspicious or abnormal domain queries
- Linked domains to potential malicious activity

5. IOC Identification
- Extracted Indicators of Compromise:
-- Suspicious IP addresses
-- Malicious domains
-- Unusual request patterns



---


## 📊 Key Outcomes
- Successfully identified: Malicious traffic patterns and Suspicious external communications
- Reconstructed attack flow from initial access to exploitation
- Extracted relevant IOCs for detection and prevention
- Produced a structured forensic report with evidence-backed conclusions

---
## 🧠 Skills Demonstrated
- Network Traffic Analysis
- Packet Inspection (Wireshark)
- Incident Investigation & Timeline Reconstruction
- Threat Detection & IOC Identification
- Analytical Thinking & Problem Solving
- Technical Reporting & Documentation
---
## 🛡️ Mitigation Recommendations
- Implement network monitoring and alerting systems
- Block malicious IPs and domains
- Apply DNS filtering and logging mechanisms
- Enforce firewall rules and segmentation
- Use IDS/IPS for real-time detection
- Regularly update and patch systems
- Regular security monitoring and log analysis
