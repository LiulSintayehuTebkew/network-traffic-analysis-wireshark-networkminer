# Network Traffic Analysis — PCAP Investigations

Hands-on analysis of real malware infection packet captures 
from malware-traffic-analysis.net. Each investigation follows 
a structured SOC analyst methodology — protocol analysis, 
IOC extraction, threat intelligence enrichment.

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Wireshark | Packet capture analysis and protocol dissection |
| NetworkMiner | Automated host and file extraction from PCAPs |
| VirusTotal | IOC reputation checking |

---

## Methodology

1. Protocol hierarchy analysis — understand traffic composition
2. Conversation analysis — identify top talkers and data flows
3. DNS analysis — extract queried domains and detect anomalies
4. HTTP analysis — examine requests, user agents, and transfers
5. File extraction — export and hash transferred files
6. IOC enrichment — check all indicators on VirusTotal and AbuseIPDB

---


## Disclaimer

All PCAPs were obtained from malware-traffic-analysis.net, 
a public educational resource. Analysis was performed in 
an isolated virtual machine.
