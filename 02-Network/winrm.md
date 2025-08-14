# WinRM — Quick Enum (Authorized targets only)

## Discovery
nmap -p 5985,5986 -sV <IP>

## Client (when creds provided)
# evil-winrm -i <IP> -u <user> -p <pass>

## Notes
- Restrict to approval; log evidence paths.
