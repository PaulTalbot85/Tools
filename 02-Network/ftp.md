# FTP — Deep Dive (Authorized targets only)

## Discovery & Banner
nmap -p 21 -sV --script ftp-anon,ftp-bounce,ftp-syst -oA ftp_scan_<IP> <IP>
echo | nc -nv <IP> 21

## Anonymous Access (if permitted)
# ftp -inv <IP>
#   user anonymous
#   pass anonymous@
#   ls -la
#   passive      # toggle passive mode if needed
#   recurse
#   mget *       # only if allowed to download

## Recursive Mirror (read-only evidence)
# lftp -e "set ssl:verify-certificate no; mirror --only-newer --verbose / ./loot_<IP>; bye" -u anonymous,anonymous <IP>

## FTPS / TLS Check
openssl s_client -starttls ftp -connect <IP>:21 </dev/null

## Safer Download (single files)
# wget ftp://anonymous:anonymous@<IP>/path/file.txt -O file.txt

## Notes
- Do not upload or modify content unless explicitly in scope.
- Prefer passive mode through firewalls/NAT.
- Save directory listings and transfer logs for evidence.
