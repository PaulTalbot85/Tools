# 03 – Host Discovery

## Purpose
Identify active systems within the agreed scope.

---

## Passive Discovery
- DNS records
- WHOIS information
- Certificate Transparency logs
- OSINT from public sources

## Active Discovery
### ICMP Sweep
```bash
fping -a -g <CIDR> 2>/dev/null
nmap -sn <CIDR>
