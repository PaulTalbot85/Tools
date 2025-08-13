# SOCKS Proxy Setup

## Metasploit

use auxiliary/server/socks_proxy
set SRVPORT 9050
run
SSH Dynamic Forwarding

ssh -D 1080 user@pivot_host
Proxychains Config

nano /etc/proxychains4.conf
# Add at bottom:
socks5 127.0.0.1 1080

proxychains nmap -sT -Pn -p80 10.0.0.5
