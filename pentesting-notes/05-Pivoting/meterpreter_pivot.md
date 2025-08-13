# Meterpreter Pivoting

## Autoroute

run autoroute -s <TARGET_SUBNET>

Adds route to internal network through compromised host.

Port Forwarding
portfwd add -l 8888 -p 80 -r 10.0.0.5

Access internal service at 127.0.0.1:8888.

SOCKS Proxy
use auxiliary/server/socks_proxy
set SRVHOST 127.0.0.1
set SRVPORT 9050
set VERSION 4a
run

With Proxychains
proxychains nmap -sT -Pn -p80 10.0.0.5
