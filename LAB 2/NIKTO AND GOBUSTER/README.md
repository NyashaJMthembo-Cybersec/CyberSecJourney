# Lab 02 — Web Enumeration (Nikto + Gobuster)

## Overview
Web server enumeration using Nikto and Gobuster to discover 
hidden directories, identify vulnerabilities and 
misconfigurations in web applications.

## Tools Used
- Nikto
- Gobuster

## Target
- Metasploitable 2 — http://192.168.56.105

## Skills Demonstrated
- Web vulnerability scanning
- Directory brute forcing
- HTTP status code analysis
- Attack surface mapping

## Key Commands
```bash
nikto -h http://192.168.56.105
gobuster dir -u http://192.168.56.105 -w /usr/share/wordlists/dirb/common.txt
gobuster dir -u http://192.168.56.105 -w /usr/share/wordlists/dirb/common.txt -x php,html,txt
```

## Key Findings
- Identified hidden directories and admin panels
- Discovered outdated software versions
- Found misconfigurations in web server setup

## Lab Report
Full lab report with screenshots available 
