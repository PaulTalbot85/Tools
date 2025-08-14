# SNMP — Quick Enum (Authorized targets only)

## Discovery
nmap -sU -p 161 -sV <IP>

## Safe read test (if community strings provided)
snmpwalk -v2c -c <community> <IP> 1.3.6.1.2.1.1  # system MIB

## Notes
- Never brute community strings without explicit permission.
