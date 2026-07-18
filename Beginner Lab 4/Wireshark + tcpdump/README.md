## Overview
Live network traffic capture using tcpdump and analysis 
using Wireshark. Demonstrates how unencrypted protocols 
expose sensitive data including plaintext credentials.

## Tools Used
- tcpdump (CLI capture)
- Wireshark (GUI analysis)

## Target
- Metasploitable 2 — 192.168.56.105
- Interface: vboxnet0

## Skills Demonstrated
- Network interface identification
- Live packet capture and PCAP file creation
- Wireshark display filters and TCP stream reconstruction
- Plaintext credential extraction from FTP traffic
- HTTP traffic analysis
- Protocol hierarchy and traffic statistics
- Anomaly detection using IO graphs

## Key Commands
```bash
# Capture traffic
sudo tcpdump -i vboxnet0 -w capture.pcap

# Search for credentials
sudo tcpdump -r capture.pcap -A | grep -i 'password\|user'

# Launch Wireshark
sudo wireshark &
```

## Key Findings
- Extracted FTP credentials in plaintext from packet capture
- Reconstructed full FTP session using Wireshark TCP Stream
- Demonstrated why FTP should be replaced with SFTP
- Identified traffic spikes using IO graphs

## Lab Report
Full lab report with screenshots available in 
Lab04_NetworkPacketCapture.docx
