#  Log Analysis & Incident Response

## Overview
Analysing Linux auth logs and Apache web server logs using 
bash command-line tools to detect attacks, identify threat 
actors, and build an automated incident response summary 
script.

## Tools Used
- bash
- grep
- awk
- cut
- sort / uniq / wc

## Scenario
SOC alert received — web server acting suspiciously between 
02:00 and 04:00 AM. Tasked with analysing logs to determine 
if an attack occurred and document findings.

## Skills Demonstrated
- SSH brute force detection
- Attacker IP identification and ranking
- Successful login detection after brute force
- SQL injection pattern detection
- Directory traversal detection
- Web traffic volume analysis by hour
- Automated incident response script development
- Timestamped report generation

## Key Commands
```bash
# SSH brute force detection
grep 'Failed password' /var/log/auth.log | wc -l
grep 'Failed password' /var/log/auth.log | awk '{print $(NF-3)}' | sort | uniq -c | sort -rn

# Web attack detection
grep -i 'union\|select\|insert\|drop' /var/log/apache2/access.log
grep '\.\.' /var/log/apache2/access.log

# Run incident summary
./incident_summary.sh | tee incident_report_$(date +%Y%m%d).txt
```

## Key Findings
- Detected coordinated multi-vector attack between 02:00-04:00 AM
- Primary attacker 45.33.32.156 conducted SSH brute force
  and successfully authenticated as root at 03:21 AM
- Secondary attacker 198.54.117.197 performed SQL injection
  and directory traversal attacks
- Built automated bash script for instant incident triage

## Incident Summary
| Severity | Finding |
|----------|---------|
| CRITICAL | SSH brute force + successful root login |
| CRITICAL | SQL injection attempt returned HTTP 200 |
| HIGH | Directory traversal targeting /etc/passwd |
| HIGH | Attack window confirmed 02:00-04:00 AM |
| MEDIUM | Admin panel scanning detected |

## Lab Report
Full lab report with screenshots available in 
Lab06_LogAnalysis.docx
