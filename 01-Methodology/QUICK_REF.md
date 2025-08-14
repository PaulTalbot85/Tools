# Quick Reference — Pentesting Methodology

One-page workflow for CTFs, exams (eJPT, eCPPT, OSCP), and fast real-world engagements.

---

## 1️⃣ Scoping
- Define target IPs, domains, and in/out-of-scope services.
- Agree on testing window and rules of engagement.

---

## 2️⃣ Host Discovery
fping -a -g <SUBNET> 2>/dev/null
nmap -sn <SUBNET> -oA ping_sweep

---

## 3️⃣ Port Scanning
nmap -p- --min-rate 1000 -T4 -oA allports <IP>
nmap -sC -sV -p<ports> -oA versions <IP>

---

## 4️⃣ Service Enumeration
- **FTP** — ftp <IP> / nmap --script ftp*
- **SSH** — ssh <user>@<IP>
- **SMB** — smbclient -L //<IP> / crackmapexec smb <IP>
- **HTTP** — whatweb <URL> / gobuster dir -u <URL> -w <WORDLIST>
- **MSSQL** — impacket-mssqlclient <user>@<IP>

---

## 5️⃣ Web Testing
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirb/common.txt
sqlmap -u "http://<IP>/index.php?id=1" --batch

---

## 6️⃣ Vuln Research
- SearchSploit: searchsploit <software> <version>
- CVE search: Google “<product> <version> CVE”

---

## 7️⃣ Initial Access
- Default creds, weak creds, brute force
- Exploit known CVEs (Metasploit or manual)
- Phishing / HTA payloads / malicious docs

---

## 8️⃣ Privilege Escalation
- **Linux** — linpeas.sh, sudo -l, GTFOBins
- **Windows** — winPEAS.exe, whoami /priv, systeminfo

---

## 9️⃣ Post-Exploitation
- Dump creds / hashes
- Lateral movement (psexec, evil-winrm, SSH key reuse)
- Pivot with autoroute + proxychains

---

## 🔟 Reporting
- Note all findings, creds, and flags.
- Include PoC commands & screenshots.
- Save raw output in /loot

---

> **Tip:** Keep this open in a split terminal during exams.
