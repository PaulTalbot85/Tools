# 04 – Port Scanning

*(Imported from your previous Port Scanning notes.)*

---

Nmap

nmap <TARGET_IP>                # Default scan
nmap -Pn <TARGET_IP>            # Skip ping
nmap -p- <TARGET_IP>            # All ports
nmap -F <TARGET_IP>             # Fast scan
nmap -sU <TARGET_IP>            # UDP scan
nmap -sV <TARGET_IP>            # Service scan
sudo nmap -sV -O <TARGET_IP>    # Service + OS detection
nmap -sC <TARGET_IP>            # Default scripts
nmap -A <TARGET_IP>             # Aggressive scan


Output

nmap -oN output.txt <TARGET_IP>
nmap -oA outputfile <TARGET_IP>
