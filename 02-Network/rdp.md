# RDP — Deep Dive (Authorized targets only)

## Discovery & Version Hints
nmap -p 3389 -sV --script rdp-enum-encryption,rdp-ntlm-info,rdp-vuln-ms12-020 -oA rdp_scan_<IP> <IP>

## Basic Connectivity Tests
# Use TLS ignore only on lab targets
xfreerdp /u:<USER> /p:<PASS> /v:<IP>:3389 /cert:ignore /dynamic-resolution
# If using a domain account:
xfreerdp /u:<DOMAIN>\\<USER> /p:<PASS> /v:<IP> /cert:ignore

## Clipboard / Drive Redirection (only if policy allows)
# Map a local folder into the session:
xfreerdp /u:<USER> /p:<PASS> /v:<IP> /drive:loot,./loot

## Network Level Authentication (NLA)
# If NLA fails, note it in evidence; some servers allow fallback
# Use nmap rdp-enum-encryption results for evidence

## Notes
- Respect account lockout policy; avoid repeated failed logins.
- Record screenshots of banner, wallpaper, and hostname if accessed.
