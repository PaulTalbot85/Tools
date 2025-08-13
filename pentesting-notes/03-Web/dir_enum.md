# Directory and File Enumeration

## Gobuster

gobuster dir -u <URL> -w /usr/share/wordlists/dirb/common.txt
gobuster dir -u <URL> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt,html
FFUF

ffuf -u <URL>/FUZZ -w /usr/share/wordlists/dirb/common.txt
ffuf -u <URL>/FUZZ -w /usr/share/wordlists/seclists/Discovery/Web-Content/big.txt -e .php,.html,.txt
Dirsearch

dirsearch -u <URL> -e php,html,txt
