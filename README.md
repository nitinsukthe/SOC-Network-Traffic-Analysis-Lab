# Network Traffic Analysis with Wireshark | Packet Capture & Protocol Investigation

## Overview

This project demonstrates practical **network traffic analysis using Wireshark** within a **Kali Linux virtual machine environment**.

The objective of this lab was to capture live network traffic, inspect DNS communications, analyze protocol distribution, review conversation statistics, and understand communication patterns generated during web browsing activity.

This project simulates the responsibilities of a **Network Analyst / SOC Analyst** performing packet inspection, protocol investigation, and traffic monitoring.

---

## Learning Objectives

By completing this project, I demonstrated the ability to:

* Conduct live packet captures using Wireshark
* Apply and remove display filters
* Analyze DNS network traffic
* Investigate protocol hierarchy statistics
* Review network conversation statistics
* Interpret traffic flows and communication patterns
* Document and present packet analysis findings

---

## Lab Environment

| Component        | Details                |
| ---------------- | ---------------------- |
| Operating System | Kali Linux VM          |
| Tool Used        | Wireshark              |
| Packet Format    | `.pcapng`              |
| Browser Activity | Web Traffic Generation |
| Target Websites  | kali.org, redhat.com   |

---

## Project Tasks

---

## Task 1: Live Packet Capture

### Objective

Capture real-time network traffic using Wireshark.

### Steps Performed

1. Opened Wireshark.
2. Selected the active network interface.
3. Started live packet capture.
4. Generated network traffic by browsing:

* https://www.kali.org/
* https://www.redhat.com/en

5. Observed captured packets in real time.
6. Stopped the capture session.
7. Saved the capture file in `.pcapng` format.

### Saved File

```bash
Packet capture.pcapng
```

### Screenshot

<img src="images/Live Packet Capture.png" width="1000">

---

## Task 2: Save Captured Traffic File

### Objective

Verify successful packet capture storage.

### Steps Performed

1. Saved the capture file to the Kali Linux Desktop.
2. Verified file availability.
3. Confirmed correct `.pcapng` format.

### Screenshot

<img src="images/Desktop.png" width="1000">

---

## Task 3: DNS Traffic Filtering

### Objective

Filter and analyze DNS traffic using Wireshark display filters.

### Display Filter Used

```bash
dns
```

### Steps Performed

1. Applied the DNS display filter.
2. Inspected DNS query and response packets.
3. Identified hostname resolution requests generated during browsing activity.
4. Removed the display filter after analysis.

### Key Observation

The browser generated DNS requests to resolve domain names before establishing HTTPS sessions.

### Screenshot

<img src="images/Filtered DNS Traffic.png" width="1000">

---

## Task 4: Protocol Hierarchy Analysis

### Objective

Analyze protocol distribution inside captured network traffic.

### Steps Performed

1. Opened:

```bash
Statistics → Protocol Hierarchy
```

2. Sorted results by:

```bash
Percent Packets (Highest → Lowest)
```

3. Reviewed protocol usage and packet distribution.

### Protocols Observed

* IPv4
* TCP
* TLS / SSL
* DNS
* HTTP / HTTPS

### Screenshot

<img src="images/Protocol Hierarchy Statistics Results.png" width="1000">

---

## Task 5: Conversation Statistics Analysis

### Objective

Review communication endpoints and traffic volume.

### Steps Performed

1. Opened:

```bash
Statistics → Conversations
```

2. Sorted conversations by:

```bash
Bytes (Highest → Lowest)
```

3. Analyzed communication pairs and high-volume traffic flows.

### Key Observation

Conversation statistics highlighted the systems responsible for the highest amount of data transfer during the browsing session.

### Screenshot

<img src="images/Conversation Statistics Report.png" width="1000">

---

## Traffic Analysis Findings

### Traffic Behavior

The captured traffic primarily consisted of:

* DNS Resolution Requests
* TCP Session Establishment
* TLS/HTTPS Encrypted Communications
* Client-Server Browser Interactions

The browsing activity generated encrypted web traffic supported by DNS lookup operations.

---

## Security Investigation Perspective

If suspicious traffic were identified during analysis, the following response actions could be considered.

### Immediate Containment Actions

* Isolate affected endpoints
* Block suspicious IP addresses
* Restrict malicious outbound traffic
* Monitor active connections

### Investigation Actions

* Inspect packet metadata
* Review DNS queries
* Correlate timestamps
* Identify anomalous traffic behavior
* Investigate communication endpoints

---

## Supporting Security Tools

Additional tools and logs useful for validating findings:

* Wireshark
* Zeek
* NetFlow Analyzer
* Firewall Logs
* IDS / IPS Logs
* SIEM Platforms
* Endpoint Security Logs

---

## Skills Demonstrated

* Network Traffic Analysis
* Packet Inspection
* Wireshark Analysis
* DNS Investigation
* Protocol Analysis
* Traffic Monitoring
* Security Investigation
* Network Communication Analysis
* Cybersecurity Documentation

---

## Repository Structure

```bash
Wireshark-Network-Traffic-Analysis/
│
├── README.md
├── Packet capture.pcapng
│
└── images/
    ├── Live Packet Capture.png
    ├── Desktop.png
    ├── Filtered DNS Traffic.png
    ├── Protocol Hierarchy Statistics Results.png
    └── Conversation Statistics Report.png
```

---

## Author

**Nitin Sukthe**

Cybersecurity | Cloud Security | AI Security Enthusiast
