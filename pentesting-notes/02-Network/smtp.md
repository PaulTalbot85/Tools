# SMTP (TCP/25)

## Nmap / Banner

sudo nmap -p25 -sV -sC -O <TARGET_IP>
nmap -sV --script banner <TARGET_IP>
Manual

nc <TARGET_IP> 25
telnet <TARGET_IP> 25
HELO attacker.xyz
EHLO attacker.xyz
User Enumeration

smtp-user-enum -U /usr/share/commix/src/txt/usernames.txt -t <TARGET_IP>
Metasploit

use auxiliary/scanner/smtp/smtp_enum
set RHOSTS <TARGET_IP>
run
