# SMB — Quick Enum (Authorized targets only)

## Discovery
nmap -p 445 -sV --script smb-protocols,smb2-time,smb2-security-mode <IP>

## Shares & users (where permitted)
smbclient -L //<IP> -N                  # null session test
# smbclient //<IP>/<share> -U <user>
# rpcclient -U "" -N <IP>               # anonymous rpc (enumdomusers/groups if allowed)

## Notes
- Save: nmap `--script smb-os-discovery,smb-enum-shares` only with authorization.
- Avoid write actions unless in scope.
