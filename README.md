# SOC Network Traffic Analysis Lab

## Wireshark-Based Packet Capture, DNS Investigation & Protocol Analysis

---

## Overview

This project demonstrates practical **network traffic capture, monitoring, and investigation** using **Wireshark** inside a **Kali Linux Virtual Machine**.

The objective of this lab was to perform live packet analysis, generate web traffic, inspect DNS communications, analyze protocol hierarchy statistics, review conversation statistics, and document findings using a SOC-style investigation workflow.

The project simulates activities commonly performed by:

* SOC Analysts
* Network Security Analysts
* Incident Response Teams
* Security Monitoring Engineers

---

## Learning Objectives

By completing this project, I demonstrated the ability to:

* Launch and configure a Kali Linux VM environment
* Capture live network traffic using Wireshark
* Apply DNS display filters
* Analyze protocol hierarchy statistics
* Investigate network conversations
* Interpret communication flows
* Perform SOC-style network investigation
* Document packet analysis findings

---

## Lab Environment

| Component         | Configuration          |
| ----------------- | ---------------------- |
| Operating System  | Kali Linux VM          |
| Analysis Tool     | Wireshark              |
| Packet Format     | `.pcapng`              |
| Browser Activity  | Web Traffic Generation |
| Websites Accessed | kali.org, redhat.com   |

---

# Task 1 — Launch Kali Linux Environment

## Step 1 — Power On Kali Linux Virtual Machine

Started the Kali Linux Virtual Machine and authenticated into the environment.

### Screenshot

<img src="screenshots/1.Power on your Kali Linux VM and log in to the environment.png" width="1000">

---

## Step 2 — Open Application Menu

Opened the Kali Linux application launcher.

### Screenshot

<img src="screenshots/2.Click the Kali Linux dragon icon in the top-left.png" width="1000">

---

## Step 3 — Search for Wireshark

Searched for the Wireshark packet analyzer.

### Screenshot

<img src="screenshots/3.Search Wireshark.png" width="1000">

---

## Step 4 — Launch Wireshark

Opened the Wireshark application.

### Screenshot

<img src="screenshots/4.Welcome to wireshark.png" width="1000">

---

# Task 2 — Live Packet Capture

## Objective

Capture real-time network traffic.

### Steps Performed

1. Selected active network interface.
2. Started live capture.
3. Generated browser traffic.
4. Visited:

* https://www.kali.org/
* https://www.redhat.com/en

5. Monitored packet activity.

### Screenshot — Live Traffic Capture

<img src="screenshots/5.Live Network Traffic.png" width="1000">

---

## Step 5 — Save Packet Capture

Saved the captured traffic file.

File format:

```plaintext
Packet capture.pcapng
```

### Screenshot

<img src="screenshots/6.Save capture file on VM desktop.png" width="1000">

---

## Step 6 — Verify Desktop File 

Verified successful packet capture file on Kali Desktop.

### Screenshot

<img src="screenshots/7.Desktop.png" width="1000">

---

# Task 3 — DNS Traffic Investigation

## Objective

Filter and analyze DNS communications.

### Display Filter Used

```plaintext
dns
```

### Steps Performed

1. Applied DNS filter.
2. Investigated DNS queries.
3. Reviewed DNS responses.
4. Identified hostname resolution traffic.

### Screenshot — DNS Filter Applied

<img src="screenshots/8.Filtered DNS traffic.png" width="1000">

---

## Step 7 — Clear Display Filter

Removed DNS display filter after analysis.

### Screenshot

<img src="screenshots/9.Clear the DNS filter from the display.png" width="1000">

---

# Task 4 — Protocol Hierarchy Analysis

## Objective

Review protocol distribution within captured traffic.

### Navigation Path

```plaintext
Statistics → Protocol Hierarchy
```

### Sorting Method

```plaintext
Percent Packets (Highest → Lowest)
```

### Protocols Observed

* IPv4
* TCP
* TLS / SSL
* DNS
* HTTPS

### Screenshot

<img src="screenshots/10.Protocol Hierarchy Statistics results.png" width="1000">

---

# Task 5 — Conversation Statistics Investigation

## Objective

Analyze communication endpoints and traffic volume.

### Navigation Path

```plaintext
Statistics → Conversations
```

### Sorting Method

```plaintext
Bytes (Highest → Lowest)
```

### Analysis Focus

* Source IP Addresses
* Destination IP Addresses
* Communication Sessions
* High-Volume Traffic Flows

### Screenshot

<img src="screenshots/11.Conversation Statistics report.png" width="1000">

---

# Traffic Analysis Findings

The captured traffic primarily consisted of:

* DNS Resolution Requests
* TCP Session Establishment
* TLS Handshakes
* HTTPS Encrypted Traffic
* Browser-Generated Client-Server Communication

Observed communication workflow:

DNS Lookup
↓
TCP Connection
↓
TLS Negotiation
↓
Encrypted HTTPS Session

---

# Security Investigation Perspective

Potential suspicious indicators analysts should investigate:

* Unknown external destinations
* Suspicious DNS domains
* Large outbound transfers
* Excessive DNS queries
* Rare protocol usage
* Persistent encrypted tunnels

---

## Recommended Immediate Containment Actions

If suspicious traffic is identified:

* Isolate affected endpoints
* Block malicious IPs
* Restrict suspicious outbound communications
* Preserve packet captures
* Collect supporting logs

---

## Supporting Tools & Logs

### Security Tools

* Wireshark
* Zeek
* NetFlow Analyzer
* Snort
* Suricata
* Splunk
* Microsoft Sentinel

### Log Sources

* Firewall Logs
* DNS Logs
* Proxy Logs
* Endpoint Logs
* SIEM Events

---

## Skills Demonstrated

* Network Traffic Analysis
* Wireshark Packet Inspection
* DNS Investigation
* Protocol Analysis
* Conversation Statistics Analysis
* Security Monitoring
* Incident Investigation
* SOC Workflow Documentation

---

## Repository Structure

```plaintext
SOC-Network-Traffic-Analysis-Lab/
│
├── README.md
│
├── report/
│   └── Wireshark_Network_Traffic_Analysis_Report.pdf
│
├── packet-capture/
│   └── Packet capture.pcapng
│
├── screenshots/
│   ├── 1.Power on your Kali Linux VM.png
│   ├── 2.Click the Kali Linux dragon icon.png
│   ├── 3.Search Wireshark.png
│   ├── 4.Welcome to wireshark.png
│   ├── 5.Live Network Traffic.png
│   ├── 6.Save capture file on VM desktop.png
│   ├── 7.Desktop.png
│   ├── 8.Filtered DNS traffic.png
│   ├── 9.Clear the DNS filter.png
│   ├── 10.Protocol Hierarchy Statistics results.png
│   └── 11.Conversation Statistics report.png
│
└── docs/
    └── Analysis_Notes.md
```

---

## Author

**Nitin Sukthe**

Cybersecurity | Cloud Security | AI Security Enthusiast
