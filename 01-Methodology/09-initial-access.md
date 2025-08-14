# 09 – Initial Access

## Purpose
Obtain first access to the target using authorised and approved methods.

---

## Common Vectors
- Exploiting known CVEs
- Default or weak credentials
- Misconfigurations
- File upload vulnerabilities

---

## Tool Examples

hydra -L users.txt -P passwords.txt ssh://<IP>
searchsploit <service> <version>
Professional Guidelines
Avoid DoS conditions.

Only run exploits approved in ROE.
