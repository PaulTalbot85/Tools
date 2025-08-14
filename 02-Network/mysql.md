# MySQL — Quick Enum (Authorized targets only)

## Discovery
nmap -p 3306 -sV --script mysql-info <IP>

## Client (when creds provided)
mysql -h <IP> -u <user> -p

## Notes
- Only enumerate databases/tables with approved credentials.
