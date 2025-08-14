# 02 – Network

This section covers enumeration, exploitation, and pivoting techniques for common network services.  
Each file focuses on **one specific protocol or post-exploitation technique** so you can quickly open only what you need.

---

## 📌 Contents

| File             | Description |
|------------------|-------------|
| `snmp.md`        | SNMP enumeration and OID cheats. |
| `smb.md`         | SMB enumeration, null sessions, smbmap, enum4linux, and MS17-010 exploitation. |
| `ftp.md`         | FTP anonymous access, brute force, and client commands. |
| `ssh.md`         | SSH enumeration, brute forcing, key extraction, and Metasploit login. |
| `mssql.md`       | Microsoft SQL Server enumeration, `xp_cmdshell`, and hash dumping. |
| `mysql.md`       | MySQL enumeration, database queries, and hash dumping. |
| `smtp.md`        | SMTP banner grabbing and user enumeration. |
| `winrm.md`       | WinRM discovery, authentication, and remote shell access. |
| `pivoting.md`    | Internal network discovery, port forwarding, and Metasploit autoroute. |
| `tunnelling.md`  | SSH tunnels, SOCKS proxies, and reverse port forwarding. |

---

## 🛠 Usage

1. **Initial Enumeration** – Use `snmp.md`, `smb.md`, `ftp.md`, `ssh.md`, `mssql.md`, `mysql.md`, and `smtp.md` for direct service checks.
2. **Internal Movement** – Once inside, use `winrm.md`, `pivoting.md`, and `tunnelling.md` to access deeper network segments.
3. **Targeted Access** – Open the file for the exact service you’re facing and copy/paste commands into your terminal.
4. **Maintain Scope Awareness** – Brute force only when allowed by scope and after exhausting enumeration.

---

## 🔍 Quick Start Commands

| Protocol  | Fast Check Example |
|-----------|--------------------|
| SNMP      | `snmpwalk -v2c -c public <TARGET>` |
| SMB       | `smbclient -L //<TARGET> -N` |
| FTP       | `ftp <TARGET>` (try `anonymous`) |
| SSH       | `ssh <USER>@<TARGET>` |
| MSSQL     | `mssqlclient.py 'sa:<PW>@<TARGET>'` |
| MySQL     | `mysql -h <TARGET> -u root -p` |
| SMTP      | `nc <TARGET> 25` |
| WinRM     | `evil-winrm -i <TARGET> -u <USER> -p <PW>` |

---

> **Tip:** For speed during live testing, keep your most-used `.md` files open in a second terminal or split-pane editor so you can copy/paste instantly.
