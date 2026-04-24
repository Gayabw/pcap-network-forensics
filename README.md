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

## Scenario
A user (Lily Turkige) received anonymous, self-destructing harassment emails
Investigation conducted using a provided PCAP dataset (academic lab)
Goal:
- Identify the source of the communication
- Trace user activity behind the emails
- Reconstruct the sequence of events using network evidence
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
## ⚙️ Investigation Steps (With evidence)

- The provided PCAP dataset simulates a network forensic investigation scenario involving suspected harassment activity: 
- Objective was to identify:
  - The originating device
  - The communication behavior
  - Evidence of anonymous messaging activity
- Analysis was conducted using packet-level inspection in Wireshark
1. Loaded PCAP into Wireshark
- Reviewed capture summary (duration, packets, size)
2. Identified active devices
- Used Statistics → Endpoints
- Found 192.168.15.4 as highest traffic generator (suspect)
3. Confirmed key network roles
- 192.168.15.1 → Router
- 192.168.15.4 → Suspicious user device
4. Applied protocol filters
- tcp → general communication analysis
- http → web activity
- dns → domain lookups
5. Focused on suspect device
- ip.addr == 192.168.15.4
- Tracked all incoming & outgoing traffic
6. Analyzed web activity
- http && ip.addr == 192.168.15.4
- Found:
  - Google searches
  - YouTube access
  - Amazon browsing
7. Investigated DNS behavior
- Identified requests to:
  - sendanonymousemail.net
  - willselfdestruct.com
8. Searched for suspicious content
- frame contains "send+anonymous"
- frame contains "tuckrige"
- frame contains "mail"
9. Tracked communication with external IP
- ip.addr == 140.247.62.34
- Linked to harassment target (via router)
10. Correlated evidence
- Gmail account identified
- Anonymous messaging activity confirmed
- User intent observed via search behavior
11. Reconstructed activity timeline
- Based on:
  - Packet numbers
  - HTTP referers
  - Timestamps
- Example:
  - Yahoo search → Google search → YouTube → Amazon
  - Then suspicious activity
---


## 📊 Key Findings
- 192.168.15.4 identified as the primary suspect device
- Evidence of anonymous email service usage
- DNS queries linked to:
  - Self-destructing email platforms
- Packet data confirmed:
  - Harassment-related communication activity
- User behavior showed:
  - Transition from normal browsing → suspicious actions

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
