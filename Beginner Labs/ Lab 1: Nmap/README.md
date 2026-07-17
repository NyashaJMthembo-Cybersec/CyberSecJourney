# Lab 01 — Network Reconnaissance (Nmap)

## Overview
Network reconnaissance using Nmap to discover open ports, 
running services, and OS information on a target system.

## Tools Used
- Nmap

## Target
- Metasploitable 2 — 192.168.56.105

## Skills Demonstrated
- Port scanning
- Service version detection
- OS fingerprinting
- XML output for Metasploit import

## Key Commands
```bash
sudo nmap -sV 192.168.56.105
sudo nmap -A 192.168.56.105
sudo nmap -p- 192.168.56.105
sudo nmap -oX scan_results.xml 192.168.56.105
```

## Lab Report
Full lab report with screenshots available in 
Lab01_Nmap.docx
