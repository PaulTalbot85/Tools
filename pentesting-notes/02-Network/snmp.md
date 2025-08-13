# SNMP Enumeration

## Quick Scan

sudo nmap -sU -p 161 --open <TARGET_IP>

Walk Known OIDs (v2c)

snmpwalk -v2c -c <COMMUNITY> <TARGET_IP>
snmpwalk -v2c -c <COMMUNITY> <TARGET_IP> 1.3.6.1.2.1.1        # system
snmpwalk -v2c -c <COMMUNITY> <TARGET_IP> 1.3.6.1.2.1.25.1.6.0  # processes
snmpwalk -v2c -c <COMMUNITY> <TARGET_IP> 1.3.6.1.4.1.77.1.2.25 # Windows users

Bruteforce Community (one-liner idea)

for s in public private manager public123 blue; do snmpwalk -v2c -c $s <TARGET_IP> 1.3.6.1.2.1.1 && echo "[+] $s" && break; done
