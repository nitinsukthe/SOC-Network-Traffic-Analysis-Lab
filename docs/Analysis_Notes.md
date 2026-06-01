# Analysis Notes

## Project: SOC Network Traffic Analysis Lab

### Analyst

**Nitin Sukthe**

### Environment

* Kali Linux Virtual Machine
* Wireshark Packet Analyzer
* Live Network Interface Capture
* Browser Traffic Generation

### Websites Used

* https://www.kali.org/
* https://www.redhat.com/en

---

# 1. Traffic Capture Notes

Live network traffic capture was performed using Wireshark.

The capture session monitored real-time network activity generated through browser interactions.

Traffic collection included:

* DNS Requests
* DNS Responses
* TCP Connections
* TLS Handshakes
* HTTPS Communications
* Client–Server Traffic

Packet capture was saved successfully in:

```plaintext id="rk5hmu"
Packet capture.pcapng
```

---

# 2. DNS Traffic Analysis Notes

## Display Filter Used

```plaintext id="c5rk2r"
dns
```

### Purpose

The DNS display filter was used to isolate domain name resolution traffic from the full packet capture.

### Observations

Observed DNS behavior included:

* Hostname lookup requests
* DNS resolver responses
* Domain-to-IP address mapping

The browser performed DNS resolution before establishing secure HTTPS sessions.

Typical communication sequence:

Client → DNS Query
DNS Resolver → DNS Response

### Security Relevance

DNS traffic analysis is useful for detecting:

* Suspicious domains
* Malware beaconing
* Command and Control activity
* DNS tunneling
* Data exfiltration behavior

No immediately suspicious DNS activity was identified during this analysis.

---

# 3. Protocol Hierarchy Analysis Notes

## Navigation Path

```plaintext id="ywj6hy"
Statistics → Protocol Hierarchy
```

### Sorting Method

```plaintext id="xjlwmw"
Percent Packets (Highest → Lowest)
```

### Protocols Observed

The packet capture contained several common protocols associated with encrypted web browsing.

Observed protocols included:

* IPv4
* TCP
* TLS / SSL
* DNS
* HTTPS

### Key Findings

The majority of captured packets corresponded to standard browser communication behavior.

Encrypted protocols represented a significant portion of network activity.

Protocol hierarchy analysis confirmed expected multi-layer communication between client systems and remote web services.

---

# 4. Conversation Statistics Notes

## Navigation Path

```plaintext id="mk8y8m"
Statistics → Conversations
```

### Sorting Method

```plaintext id="e6rlnh"
Bytes (Highest → Lowest)
```

### Observations

Conversation statistics analysis identified:

* Source endpoints
* Destination endpoints
* Active communication sessions
* Traffic volume rankings

High-volume traffic flows primarily corresponded to browser communications with external servers.

Traffic behavior aligned with normal client-server browsing activity.

---

# 5. Communication Flow Analysis

The packet capture demonstrated a typical web communication lifecycle.

Observed sequence:

DNS Resolution
↓
TCP Session Establishment
↓
TLS Handshake
↓
HTTPS Data Exchange
↓
Connection Termination

### Interpretation

This communication pattern reflects expected encrypted web browsing behavior.

No immediately anomalous communication sequence was identified.

---

# 6. Security Findings

The traffic analysis identified characteristics commonly associated with legitimate web activity.

Observed indicators included:

✔ DNS Resolution Requests

✔ TCP Session Creation

✔ TLS Encrypted Communication

✔ HTTPS Traffic

✔ Browser-Based Client–Server Interaction

---

## Potential Threat Indicators to Investigate

In enterprise environments, analysts should monitor for:

* Unknown external destinations
* Suspicious DNS domains
* Large outbound transfers
* Excessive failed connections
* Abnormal protocol usage
* Rare geographic connections
* Persistent encrypted tunnels

---

# 7. Recommended Immediate Containment Actions

If suspicious indicators are identified, recommended response actions include:

### Endpoint Isolation

Disconnect affected systems from the network.

### Block Malicious Infrastructure

Restrict:

* Malicious IP addresses
* Suspicious domains
* Unauthorized ports

### Restrict Outbound Traffic

Monitor and control:

* DNS communications
* HTTPS outbound sessions
* Remote external connections

### Preserve Evidence

Secure investigative artifacts including:

* Packet captures
* Firewall logs
* DNS logs
* Endpoint telemetry
* Security alerts

---

# 8. Recommended Investigation Workflow

Structured investigation process:

### Step 1 — Packet Metadata Review

Review:

* Source IPs
* Destination IPs
* Ports
* Protocols
* Timestamps

### Step 2 — DNS Validation

Analyze:

* Query frequency
* Domain reputation
* Newly observed domains

### Step 3 — External Connection Validation

Validate:

* Destination ownership
* ASN information
* Threat intelligence reputation

### Step 4 — Security Event Correlation

Correlate findings with:

* Firewall logs
* Authentication events
* Endpoint logs
* SIEM alerts

### Step 5 — Endpoint Investigation

Review systems for:

* Suspicious processes
* Malware indicators
* Persistence mechanisms
* Unauthorized scheduled tasks

---

# 9. Supporting Tools & Logs

## Security Tools

* Wireshark
* Zeek
* NetFlow Analyzer
* Snort
* Suricata
* Splunk
* ELK Stack
* Microsoft Sentinel

---

## Log Sources

### Firewall Logs

Useful for:

* Connection monitoring
* Policy validation
* Blocked traffic analysis

### DNS Logs

Useful for:

* Domain resolution history
* Query frequency analysis

### Proxy Logs

Useful for:

* Web activity review
* Download monitoring

### Endpoint Logs

Useful for:

* Process investigation
* User activity analysis
* Security event review

### SIEM Logs

Useful for:

* Alert correlation
* Timeline reconstruction
* Incident validation

---

# 10. Skills Demonstrated

This project demonstrates practical cybersecurity and SOC analysis skills including:

* Network Traffic Analysis
* Packet Capture
* Wireshark Operations
* DNS Investigation
* Protocol Analysis
* Conversation Statistics Review
* Security Monitoring
* Incident Investigation
* Security Reporting
* Network Communication Analysis

---

# 11. Analyst Summary

This assessment successfully demonstrated live network traffic monitoring and investigation using Wireshark in a Kali Linux environment.

Traffic generated through browser interactions was captured, filtered, analyzed, and interpreted using multiple analytical techniques.

The exercise reinforces practical skills relevant to:

* SOC Analyst
* Network Security Analyst
* Incident Response Analyst
* Cybersecurity Analyst
