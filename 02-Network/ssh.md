# SSH Enumeration & Access (TCP/22)

## Nmap

sudo nmap -p22 -sV -sC -O <TARGET_IP>
nmap -p22 --script ssh2-enum-algos <TARGET_IP>
nmap -p22 --script ssh-hostkey --script-args ssh_hostkey=full <TARGET_IP>
nmap -p22 --script ssh-auth-methods --script-args="ssh.user=<USER>" <TARGET_IP>
nmap -p22 --script=ssh-brute --script-args userdb=<USERS_LIST> <TARGET_IP>

Connect / Netcat sanity

nc -v <TARGET_IP> 22
ssh <USER>@<TARGET_IP>
Metasploit

use auxiliary/scanner/ssh/ssh_login
set RHOSTS <TARGET_IP>
set USERPASS_FILE /usr/share/wordlists/metasploit/root_userpass.txt
set STOP_ON_SUCCESS true
run

Brute (scoped)

hydra -l <USER> -P /usr/share/wordlists/rockyou.txt <TARGET_IP> ssh
