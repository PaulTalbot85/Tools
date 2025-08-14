# 04 – Port Scanning

## Purpose
Identify exposed services and understand the attack surface.

---

## TCP
### Quick Scan

nmap -Pn -T4 --top-ports 1000 -sC -sV <IP> -oN quick_tcp.txt

Full Scan
nmap -p- -T4 <IP> -oN allports_tcp.txt

UDP
nmap -sU --top-ports 100 <IP> -oN top_udp.txt

Professional Practices
Save scan results in multiple formats (normal, XML, grepable).

Run scans during agreed testing windows to reduce impact.

