# 03 – Host Discovery

*(Imported from your previous Host Discovery notes.)*

---

Ping Scan

sudo nmap -sn <TARGET_IP/NETWORK>

ARP Scan

netdiscover -i eth1 -r <TARGET_IP/NETWORK>

fping

fping -I eth1 -g <TARGET_IP/NETWORK> -a 2>/dev/null
