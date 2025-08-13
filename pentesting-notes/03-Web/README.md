# 03 – Web

This section contains enumeration, vulnerability testing, and exploitation techniques for web applications and HTTP-based services.  
Each file is focused on one area or attack type so you can quickly jump to the exact technique you need.

---

## 📌 Contents

| File                | Description |
|---------------------|-------------|
| `http_enum.md`      | HTTP/HTTPS enumeration and technology fingerprinting. |
| `auth_brute.md`     | Authentication brute force and password spraying. |
| `dir_enum.md`       | Directory and file brute forcing (Gobuster, FFUF). |
| `sqli.md`           | SQL Injection testing and exploitation (manual + tools). |
| `xss.md`            | Cross-Site Scripting discovery and payloads. |
| `lfi_rfi.md`        | Local/Remote File Inclusion testing. |
| `ssrf.md`           | Server-Side Request Forgery checks. |
| `cmd_injection.md`  | Command injection detection and exploitation. |
| `file_upload.md`    | File upload exploitation and bypasses. |
| `wordpress.md`      | WordPress enumeration and exploitation. |
| `drupal.md`         | Drupal enumeration and common exploits. |
| `rejetto_hfs.md`    | Rejetto HFS RCE exploitation. |
| `spip.md`           | SPIP CMS enumeration and exploitation. |

---

## 🛠 Usage

1. **Start with `http_enum.md`** to fingerprint technologies, gather headers, and map the application.
2. **Run `dir_enum.md`** to discover hidden endpoints and backup files.
3. **Test for vulnerabilities** using the relevant attack files (`sqli.md`, `xss.md`, etc.).
4. **Leverage CMS-specific files** (`wordpress.md`, `drupal.md`, `rejetto_hfs.md`, `spip.md`) for targeted exploitation.
5. **Document everything** for reporting and pivoting.

---

## 🔍 Quick Start Commands

| Task         | Command |
|--------------|---------|
| Tech detect  | `whatweb <URL>` |
| Dir enum     | `gobuster dir -u <URL> -w /usr/share/wordlists/dirb/common.txt` |
| Auth brute   | `hydra -l admin -P rockyou.txt <URL> http-post-form` |
| SQLi         | `sqlmap -u "<URL>?id=1" --batch --dump` |
| XSS test     | `<script>alert(1)</script>` |
| WP enum      | `wpscan --url <URL> --enumerate u,ap,at` |

---

> **Tip:** Always save tool output to files (`-oN`, `-oA`, or `tee`) so you can quickly reference it later in the engagement.
