# Directory Discovery (Authorized targets only)

## Gobuster
gobuster dir -u http://<IP>/ -w /usr/share/wordlists/dirb/common.txt -o gobuster_<IP>.txt

## FFUF (status filter)
ffuf -w /usr/share/wordlists/dirb/common.txt -u http://<IP>/FUZZ -mc 200,204,301,302 -o ffuf_<IP>.json

## Notes
- Respect rate limits; avoid noisy scans on prod.
