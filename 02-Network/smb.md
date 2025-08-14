# SMB — Deep Dive (Authorized targets only)

## Fast discovery (save output)
nmap -p 445 -sV --script smb-protocols,smb2-time,smb2-security-mode,smb-os-discovery -oA smb_scan_<IP> <IP>

## Null / guest tests (if allowed)
smbclient -L //<IP> -N
rpcclient -U "" -N <IP>   # try enumdomusers / enumdomgroups carefully

## Shares and listings
# Anonymous:
# smbclient //<IP>/<share> -N
# Authenticated:
# smbclient //<IP>/<share> -U <user>
#   ls
#   recurse ON
#   prompt OFF
#   mget *

## SMBMap quick wins
# smbmap -H <IP> -u <user> -p '<pass>'
# smbmap -L -H <IP>                # list drives
# smbmap -r <share> -H <IP>        # list dir
# smbmap -x "ipconfig" -H <IP>     # run command (only if explicitly permitted)

## CrackMapExec basics
# crackmapexec smb <IP> -u <user> -p <pass> --shares
# crackmapexec smb <IP> -u <user> -p <pass> --users
# crackmapexec smb <IP> -u <user> -p <pass> -x "whoami"   # only with authorization

## Notes
- Prefer read-only enumeration first; log everything to files.
- Avoid writable operations unless in scope and necessary.
