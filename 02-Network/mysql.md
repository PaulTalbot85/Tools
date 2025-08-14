# MySQL (TCP/3306)

## Nmap

sudo nmap -p3306 -sV -O <TARGET_IP>
nmap -p3306 --script mysql-empty-password,mysql-info <TARGET_IP>
nmap -p3306 --script mysql-users,mysql-databases,mysql-variables --script-args "mysqluser='<USER>',mysqlpass='<PW>'" <TARGET_IP>

mysql -h <TARGET_IP> -u <USER> -p

show databases;
use <DB>;
show tables;
select * from <TABLE> limit 5;
Hash dump / query via NSE

nmap -sV -p3306 --script mysql-dump-hashes --script-args "username='<USER>',password='<PW>'" <TARGET_IP>
nmap -p3306 --script mysql-query --script-args \
"query='select version();',username='<USER>',password='<PW>'" <TARGET_IP>
Brute (scoped)

hydra -l <USER> -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt <TARGET_IP> mysql
