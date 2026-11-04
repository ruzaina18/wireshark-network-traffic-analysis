# Practical Network Traffic Analysis Using Wireshark

![Wireshark](https://img.shields.io/badge/Tool-Wireshark-blue)
![Category](https://img.shields.io/badge/Category-Cybersecurity-red)
![Level](https://img.shields.io/badge/Level-Beginner-green)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey)

## 1. Project Overview

Network Traffic Analysis is an important part of cybersecurity that involves monitoring, capturing, and analysing data packets travelling across a network.

This project demonstrates practical network traffic analysis using **Wireshark**, an open-source network protocol analyser. The objective is to understand network communication, investigate TCP and DNS activities, examine network ports, and identify patterns that may indicate suspicious behaviour.

Five practical investigations were conducted using Wireshark display filters to analyse captured network packets and document security observations.

## 2. Project Objectives

- Capture and inspect live network traffic.
- Understand TCP and UDP communication.
- Analyse TCP retransmissions and connection resets.
- Investigate DNS queries and responses.
- Identify commonly used network ports.
- Examine repeated TCP connection attempts.
- Recognise potential indicators of suspicious network activity.
- Document findings with packet-level evidence.

## 3. Tools and Technologies

| Tool | Purpose |
|---|---|
| Wireshark | Network packet capture and analysis |
| Npcap | Capturing network packets on Windows |
| Windows Command Prompt | Generating network traffic |
| TCP/IP | Network communication analysis |
| DNS | Domain name resolution |
| HTTP/HTTPS | Web communication analysis |

## 4. Project Environment

- Operating System: Windows
- Network Interface: Wi-Fi
- Packet Analysis Tool: Wireshark
- Capture Format: PCAPNG

## 5. Practical Investigations

### Lab 1: TCP Retransmission Analysis

**Objective:** Identify retransmitted TCP packets and investigate possible network communication issues.

**Wireshark Display Filter:**

```wireshark
tcp.analysis.retransmission
```

**Activities Performed:**
- Filtered TCP retransmission packets.
- Examined source and destination IP addresses.
- Inspected TCP sequence and acknowledgement numbers.
- Investigated repeated retransmission patterns.

**Learning Outcome:** Understood how TCP retransmissions can indicate packet loss, network congestion, or connectivity issues.

### Lab 2: TCP Reset Analysis

**Objective:** Investigate TCP connections that are abruptly terminated.

**Wireshark Display Filter:**

```wireshark
tcp.flags.reset == 1
```

**Activities Performed:**
- Identified TCP RST packets.
- Examined source and destination IP addresses.
- Identified destination ports.
- Investigated possible causes of connection termination.

**Learning Outcome:** Developed an understanding of TCP reset flags and unexpected connection termination.

### Lab 3: DNS Traffic Investigation

**Objective:** Analyse DNS queries and responses to understand domain resolution and identify unusual DNS activity.

**Wireshark Display Filters:**

```wireshark
dns
```

```wireshark
dns.flags.rcode != 0
```

**Activities Performed:**
- Captured DNS requests and responses.
- Identified queried domain names.
- Examined DNS server addresses.
- Investigated unsuccessful DNS responses.
- Looked for repeated or unusual domain requests.

**Learning Outcome:** Gained practical experience in DNS packet analysis and identifying potentially unusual domain-resolution patterns.

### Lab 4: Destination Port Analysis

**Objective:** Examine TCP and UDP communication to identify network services and destination ports.

**Wireshark Display Filter:**

```wireshark
tcp || udp
```

**Common Network Ports Examined:**

| Port | Protocol / Service |
|---|---|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |
| 3389 | Remote Desktop |

**Activities Performed:**
- Filtered TCP and UDP packets.
- Examined source and destination ports.
- Identified common network services.
- Investigated unfamiliar ports and destinations.

**Learning Outcome:** Improved understanding of network services, port identification, and communication patterns.

### Lab 5: TCP Connection Attempt Analysis

**Objective:** Investigate TCP connection initiation and identify repeated connection attempts.

**Wireshark Display Filters:**

```wireshark
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

```wireshark
tcp.analysis.flags
```

**Activities Performed:**
- Identified initial TCP SYN packets.
- Examined source and destination IP addresses.
- Investigated repeated connection attempts.
- Examined connections involving multiple destination ports.
- Looked for potential indicators of port scanning.

**Learning Outcome:** Understood TCP connection initiation and how repeated connection attempts can be investigated for possible port-scanning activity.

## 6. Security Observations

The investigations focused on the following potential indicators:

- Repeated TCP retransmissions that may indicate connectivity issues.
- Unexpected TCP resets that may indicate connection termination.
- Unusual DNS requests that may require further investigation.
- Unexpected destination ports that may indicate unfamiliar services.
- Repeated TCP connection attempts that may be consistent with port scanning.

**Note:** These indicators do not independently confirm malicious activity. Network context and additional evidence are required before classifying traffic as suspicious.

## 7. Project Screenshots and Evidence

The `screenshots` directory contains evidence collected during the five practical investigations.

| File | Description |
|---|---|
| 01_tcp_retransmission.png | TCP retransmission analysis |
| 02_tcp_reset.png | TCP reset investigation |
| 03_dns_investigation.png | DNS query and response analysis |
| 04_port_analysis.png | TCP and UDP destination port analysis |
| 05_tcp_syn_analysis.png | TCP connection attempt investigation |

## 8. Skills Demonstrated

- Wireshark
- Network Traffic Analysis
- Packet Capture and Inspection
- TCP/IP Protocol Analysis
- DNS Investigation
- TCP Connection Analysis
- Network Port Identification
- Network Troubleshooting
- Security Monitoring Fundamentals
- Technical Documentation

## 9. Conclusion

This project provided practical experience in network traffic monitoring and packet-level investigation using Wireshark.

Through five hands-on investigations, I developed an understanding of TCP communication, DNS resolution, network ports, and connection behaviour.

The exercises strengthened my ability to apply Wireshark display filters, interpret packet information, investigate unusual communication patterns, and document technical findings.

## 10. Disclaimer

This project was conducted for educational and cybersecurity learning purposes using network traffic captured from my own system. No unauthorised network access or testing was performed.

All security observations should be validated against actual packet captures before being classified as suspicious or malicious.
