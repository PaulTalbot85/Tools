# WinRM — Deep Dive (Authorized targets only)

## Discovery
nmap -p 5985,5986 -sV -oA winrm_scan_<IP> <IP>

## Client (approved creds)
# evil-winrm -i <IP> -u <user> -p <pass>
#   upload file.txt
#   download C:\path\file.txt
#   powershell or cmd session as needed

## CrackMapExec (approved usage)
# crackmapexec winrm <IP> -u <user> -p <pass> -x "whoami"

## Notes
- All authentication attempts must follow lockout policy and scope.
