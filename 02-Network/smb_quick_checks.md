# SMB — Quick Checks (Authorized targets only)

## Signing & Security Mode
nmap -p 445 -sV --script smb2-security-mode,smb2-time -oA smb_quick_<IP> <IP>

## Null session probes (unauth where allowed)
smbclient -L //<IP> -N
# rpcclient -U "" -N <IP>   # if permitted

## CrackMapExec quick glance (with creds; read-only)
# crackmapexec smb <IP> -u <USER> -p <PASS> --shares
# crackmapexec smb <IP> -u <USER> -p <PASS> --users

## Notes
- If signing is disabled or not required, note as a finding.
- Avoid write operations unless explicitly approved by scope.
