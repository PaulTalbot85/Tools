# MSSQL — Deep Dive (Authorized targets only)

## Discovery
nmap -p 1433 -sV --script ms-sql-info,ms-sql-ntlm-info -oA mssql_scan_<IP> <IP>

## Client (approved creds)
impacket-mssqlclient <DOMAIN>/<user>@<IP> -windows-auth
# Once connected:
#   SELECT @@version;
#   SELECT name FROM sys.databases;
#   USE <db>; SELECT TOP 5 * FROM <table>;

## Dangerous features (enable/use ONLY if scope allows)
# xp_cmdshell usage is sensitive:
#   EXEC sp_configure 'show advanced options', 1; RECONFIGURE;
#   EXEC sp_configure 'xp_cmdshell', 1; RECONFIGURE;
#   EXEC xp_cmdshell 'whoami';

## Notes
- Prefer T-SQL enumeration; avoid OS-level execution unless formally permitted.
