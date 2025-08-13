# Tunnelling (SOCKS / SSH / Misc)

## SSH Dynamic SOCKS (Attacker → Jump)

ssh -D 9050 -N <USER>@<JUMP_HOST>
# use with proxychains (socks5 127.0.0.1 9050)
SSH Local Port Forward

# Map local 127.0.0.1:<LPORT> → <INTERNAL_HOST>:<RPORT> through <JUMP_HOST>
ssh -L 127.0.0.1:<LPORT>:<INTERNAL_HOST>:<RPORT> <USER>@<JUMP_HOST>
SSH Remote Port Forward (reverse)

# Remote <JUMP_HOST>:<RPORT> → local <LHOST>:<LPORT>
ssh -R <RPORT>:127.0.0.1:<LPORT> <USER>@<JUMP_HOST>
Metasploit SOCKS (quick ref)

use auxiliary/server/socks_proxy
set SRVHOST 127.0.0.1
set SRVPORT 9050
run
Meterpreter Portfwd (quick ref)

portfwd add -l <LOCAL_PORT> -p <TARGET_PORT> -r <TARGET_IP>
