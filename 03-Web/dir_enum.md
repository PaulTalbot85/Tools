# Directory Discovery — Deep Dive (Authorized targets only)

## Gobuster quick
gobuster dir -u http://<IP>/ -w /usr/share/wordlists/dirb/common.txt -o gobuster_<IP>.txt

## Gobuster with extensions
gobuster dir -u http://<IP>/ -w /usr/share/wordlists/dirb/common.txt -x php,txt,html,js -o gobuster_ext_<IP>.txt

## FFUF (status filter + recursion caution)
ffuf -w /usr/share/wordlists/dirb/common.txt -u http://<IP>/FUZZ -mc 200,204,301,302 -o ffuf_<IP>.json
# For nested paths, do targeted recursion only (avoid blind -recursion on prod).

## Virtual host fuzz (only if domain in scope)
# ffuf -w subdomains.txt -u http://<IP>/ -H "Host: FUZZ.<domain>" -fs <size>

## Notes
- Respect rate limits; throttle with -t, -p as needed.
