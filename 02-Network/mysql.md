# MySQL — Deep Dive (Authorized targets only)

## Discovery
nmap -p 3306 -sV --script mysql-info,mysql-variables -oA mysql_scan_<IP> <IP>

## Client (with approved creds)
mysql -h <IP> -u <user> -p
SHOW DATABASES;
USE <db>;
SHOW TABLES;
SELECT COUNT(*) FROM <table>;

## NSE helpers (only when allowed)
# nmap -p 3306 --script mysql-users --script-args "mysqluser='<user>',mysqlpass='<pass>'" <IP>
# nmap -p 3306 --script mysql-databases --script-args "mysqluser='<user>',mysqlpass='<pass>'" <IP>

## Notes
- Do not brute credentials without explicit written approval.
- Export only necessary evidence and redact sensitive data.
