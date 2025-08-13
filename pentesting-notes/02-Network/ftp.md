# FTP Enumeration & Access (TCP/21)

## Nmap

sudo nmap -p21 -sV -sC -O <TARGET_IP>
nmap -p21 --script ftp-anon <TARGET_IP>
nmap -p21 --script ftp-brute --script-args userdb=<USERS_LIST> <TARGET_IP>

ftp <TARGET_IP>

# try anonymous:anonymous

ls
cd /../..
get <filename>
put <filename>
Brute (scoped)

hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt \
      -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt \
      <TARGET_IP> ftp -t 4
      
