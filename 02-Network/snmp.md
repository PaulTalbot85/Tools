# SNMP — Deep Dive (Authorized targets only)

## Discovery
nmap -sU -p 161 -sV -oA snmp_scan_<IP> <IP>
# onesixtyone -c communities.txt <IP>   # if allowed

## Read-Only Walk (when community string provided)
# Classic defaults: public/private (only test if permitted)
snmpwalk -v2c -c <community> <IP> 1.3.6.1.2.1.1        # system MIB (hostname, uptime)
snmpwalk -v2c -c <community> <IP> 1.3.6.1.2.1.4        # IP stack
snmpwalk -v2c -c <community> <IP> 1.3.6.1.2.1.25.4     # Running processes
snmpwalk -v2c -c <community> <IP> 1.3.6.1.2.1.25.6     # Installed software
snmpwalk -v2c -c <community> <IP> 1.3.6.1.2.1.17       # Bridges/switch info
snmpwalk -v2c -c <community> <IP> 1.3.6.1.2.1.31       # High-capacity ifTable

## Bulk Walk (faster on v2c)
snmpbulkwalk -v2c -c <community> <IP> 1.3.6.1.2.1

## Convenience Script
# snmp-check <IP> -c <community>

## Notes
- Never brute community strings without written approval.
- Treat data as sensitive (routes, users, software inventory).
- Store outputs with clear filenames for reports.
