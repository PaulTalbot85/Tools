# FTP — Quick Enum (Authorized targets only)

## Discover & banner
nmap -p 21 -sV --script ftp-anon,ftp-syst,ftp-bounce <IP>
echo | nc -nv <IP> 21

## Anonymous check
# If permitted, test anonymous:
# ftp -inv <IP>
#   user anonymous
#   pass anonymous@

## Notes
- Prefer read-only verification.
- Capture `nmap -oA ftp_<IP>` outputs for reports.
