# Service Enumeration (Generic)

When you find an open port with an unknown service, follow this general process.

---

## Step 1 – Version & Banner Grab
\`\`\`bash
nc -nv <IP> <PORT>
telnet <IP> <PORT>
openssl s_client -connect <IP>:<PORT> -servername <HOST>
\`\`\`

---

## Step 2 – Protocol-Specific Probing
- Use \`nmap -sV -p<port> --script <relevant NSE>\`  
- Try relevant CLI clients (\`ftp\`, \`mysql\`, \`redis-cli\`, etc.)
- For web services:  
  \`\`\`bash
  curl -i http://<IP>:<PORT>/
  whatweb http://<IP>:<PORT>/
  \`\`\`

---

## Step 3 – Authentication Testing
- Anonymous login attempts (FTP, SMB, etc.)
- Default credentials (CIRT, SecLists)

---

## Step 4 – Deeper Enumeration
- Use matching tools (see \`../02-Network\` and \`../03-Web\` folders)
- Search for known exploits:
  \`\`\`bash
  searchsploit "<service> <version>"
  \`\`\`
  or  
  \`\`\`bash
  cve-search <service> <version>
  \`\`\`

---

> 📌 Tip: Always save output with \`-oN\` (nmap) or \`tee\` so you can grep later.
