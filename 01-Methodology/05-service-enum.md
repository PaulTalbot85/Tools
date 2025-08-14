# 05 – Service Enumeration

## Purpose
Gather detailed information about identified services to find entry points.

---

## Common Services & Techniques

### HTTP/S
- Banner grabbing: `whatweb`, `curl -I`
- Directory bruteforce: `gobuster`, `feroxbuster`
- SSL/TLS inspection: `sslyze`

### SMB
- Share enumeration: `smbclient`, `smbmap`
- User enumeration: `enum4linux-ng`

### FTP
- Anonymous login check
- File listings and download attempts

---

## Evidence Collection
- Save all discovered data with timestamps.
- Keep hashes of downloaded files for integrity.
