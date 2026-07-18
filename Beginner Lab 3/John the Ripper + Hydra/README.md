## Overview
Offline and online password auditing using John the Ripper 
and Hydra. Covers hash extraction, dictionary attacks, and 
brute force credential testing against live services.

## Tools Used
- John the Ripper (offline cracking)
- Hydra (online brute forcing)
- openssl (hash generation)
- unshadow (hash extraction)

## Target
- Practice shadow files (offline)
- Metasploitable 2 FTP service (online)

## Skills Demonstrated
- SHA-512 hash generation and cracking
- Linux shadow file format and extraction
- Dictionary attacks using rockyou.txt
- Custom wordlist creation
- FTP brute force with Hydra
- Legacy SSH algorithm troubleshooting

## Key Commands
```bash
# Offline cracking
openssl passwd -6 password123
unshadow test_passwd.txt test_shadow.txt > crackme.txt
john --wordlist=/usr/share/wordlists/rockyou.txt crackme.txt
john --show crackme.txt

# Online brute forcing
hydra -l msfadmin -P custom.txt ftp://192.168.56.105 -t 1 -V
```

## Key Findings
- Cracked SHA-512 hash using rockyou.txt wordlist
- Successfully brute forced FTP credentials
- Demonstrated weakness of common passwords

## Lab Report
Full lab reports with screenshots available in:
- Lab03A_JohnTheRipper.docx
- Lab03B_Hydra.docx
