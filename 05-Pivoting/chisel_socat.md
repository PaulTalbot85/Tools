# Chisel / Socat Patterns

## Chisel SOCKS proxy
# On VPS/server: chisel server -p <PORT> --reverse
# On client:     chisel client <SERVER_IP>:<PORT> R:socks

## Socat TCP relay
socat TCP-LISTEN:<LPORT>,fork TCP:<RHOST>:<RPORT>
