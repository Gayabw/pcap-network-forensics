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

## 📰Case Description
Scenario: 
- Lily Tuckrige, a Chemistry teacher at XYZ School, reported receiving
harassing emails on her personal email (lilytuckrige@yahoo.com). 

Initial Evidence:
- Emails suspected to originate from a student in her class.
- A screenshot of the email was provided to IT department, which requested full
headers for more details

Findings from Email Header:
- Emails originated from the IP address 140.247.62.34, a dorm room at XYZ
School

Dorm Room Details:
- Shared by three women: Alice, Barbara, and Candice.
- Wi-Fi router installed without a password by Barbara’s boyfriend
  
IT Investigation:
- Network sniffer set up to capture Ethernet traffic.
- New email sent via "willselfdestruct.com," complicating direct traceability
  
Goal:
- Identify if a Chemistry 109 student sent the emails using conclusive
evidence

---

## 🛠️ Tools & Technologies
- Wireshark v 4.4.3: Network traffic analysis professionals consider this tool as their most reliable observation platform
- platform:  Windows 10 Pro (64-bit), processor:  Intel(R) Core(TM) i3 RAM: 12 GB
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

1. **Initial Traffic Analysis**:
- Loaded PCAP into Wireshark
- Reviewed capture summary (duration, packets, size): erified file integrity using SHA256/SHA1 hashes and established the capture timeframe.
  
![Capture Summary](./assets/01_capture_summary.png)

* Figure 1: Verification of PCAP integrity using SHA hashes and capture property summary.

2. **Identified active devices**:
- Used Statistics → Endpoints
- Identified 192.168.15.4 as highest traffic generator (suspect)
  
![Active Endpoints](./assets/02_endpoint_status.png)

* Figure 2: IPv4 endpoint statistics identifying 192.168.15.4 as the primary traffic generator.

3. **Applied protocol filters**:
- tcp → general traffic
- http → web activity
- dns → domain queries

4. **Focused on suspect device**:
- ip.addr == 192.168.15.4
- Tracked all incoming & outgoing traffic
  
![IP traffic](./assets/04_ip_traffic.png)
  
5. Analyzed web activity:
- http && ip.addr == 192.168.15.4
- Observed normal browsing:
  - Google searches
  - YouTube access
  - Amazon browsing

![Web Activity](./assets/05_web_activity.png)

6. Network Infrastructure Reconstruction
- Visualized the communication flow between the suspect, the router, and external services (Amazon, Google, etc.).

![Network Structure](./assets/06_network_structure.png)

7. Investigated DNS behavior:
- Identified suspicious domain requests to:
  - sendanonymousemail.net
  - willselfdestruct.com

![DNS Behavior](./assets/07_dns_behavior.png)
    
8. Content-Based Filtering:
- Applied keyword filters:
  - frame contains "send+anonymous"
  - frame contains "tuckrige"
  - frame contains "mail"
- Revealed email-related activity linked to the victim

![Content Filter sendanonymous](./assets/08_content_filter.png)


![Content Filter Wilselfdistruct](./assets/08.1_content_filter.png)

9. Tracked communication with external IP:
- ip.addr == 140.247.62.34
- Linked to harassment target (via router)

![External IP](./assets/09_track_external_ip.png)

10. Evidence Correlation:
- Gmail account identified
- Anonymous messaging activity confirmed
- User intent observed via search behavior

![Email Evidence](./assets/10_email_evidence.png)
  
11. Timeline Reconstruction:
- Based on:
  - Packet numbers
  - HTTP referers
  - Timestamps
- Observed flow:
  - Yahoo search → Google search → YouTube → Amazon
  - Then suspicious activity: Transition to anonymous email activity

![Timeline](./assets/11_activity_timeline.png)

---

## 📊 Key Findings

1. File Security & Timeframe:
   
- Verified MD5, SHA1, and SHA256 checksums for forensic integrity.
- Captured data spans July 22, 2008, 01:51 - 06:13 UTC.
  
2. Network Details:
   
- 17 devices identified on the subnet 192.168.15.XX.
- Gateway IP: 192.168.15.1; Suspect IP: 192.168.15.4 (Apple device).

3. Investigation Findings:
   
- Harassing emails sent via sendanonymousemail.net and willselfdestruct.com.
- Email trace linked to jcoachj@gmail.com (Packet #77528).
- Searches by the suspect: “want to harass my teacher.”
  
4. Key Technical Evidence:
   
- Filters applied: ip.addr == 192.168.15.4 and frame contains "tuckrige".
- Virtual Machine detected: Windows XP (via Apple hardware).
  
5. Identification:
   
- Logs confirm suspect is Johnny Coach, Chemistry 109 student.
- Connection to nitroba.org, origin of initial harassing emails.
  
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
  
---

## 👩‍🎓Team Members
- Gayathmee Kiveka
- Minsadhi Vihasna

---

## 🎓 Academic Note
This project was developed as part of the Bachelor of Information Technology (Cybersecurity specialization) and is intended for academic and educational purposes.

[!IMPORTANT]
To maintain academic integrity and protect the privacy of team members and institutional data:
- **Redacted Information:** Sensitive identifiers, team member personal details, and internal institutional data have been omitted.
- **Partial Documentation:** Only specific forensic artifacts and methodology summaries are presented here to showcase technical proficiency.
- **Full Report:** The complete Forensic Report and original PCAP files are available for review upon request during formal interviews.

---

## 📄 License  
This repository is provided for **academic use only**.  


