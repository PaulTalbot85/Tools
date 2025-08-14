# Initial Access

Use this after enumeration to gain your first foothold.

## Common Techniques
1. **Exploiting Known Vulnerabilities**
   - RCE in web apps, unpatched services
   - Public exploits from Exploit-DB, GitHub

2. **Brute Force / Credential Stuffing**
   - SSH, RDP, SMB, WinRM
   - Use small targeted wordlists first

3. **Phishing / User Interaction**
   - HTA payloads, malicious docs, links
   - Combine with OSINT on targets

4. **Misconfigurations**
   - Anonymous SMB shares
   - Default credentials
   - World-writable web directories

## Post-Access Actions
- Establish persistence
- Enumerate system & network
- Prepare for privilege escalation
