# MSSQL — Quick Enum (Authorized targets only)

## Discovery
nmap -p 1433 -sV --script ms-sql-info,ms-sql-ntlm-info <IP>

## Client (when creds provided)
impacket-mssqlclient <DOMAIN>/<user>@<IP> -windows-auth

## Notes
- Use query enumeration only with authorization.
