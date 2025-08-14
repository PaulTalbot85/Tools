# SMTP — Deep Dive (Authorized targets only)

## Discovery & Banner
nmap -p 25,465,587 -sV --script smtp-commands,smtp-open-relay -oA smtp_scan_<IP> <IP>
echo | nc -nv <IP> 25
openssl s_client -connect <IP>:465 </dev/null
openssl s_client -starttls smtp -connect <IP>:587 </dev/null

## Safe Capability Check
swaks --server <IP> --helo test.local --quit-after HELO
# swaks --to you@example.com --from me@example.com --server <IP> --quit-after RCPT

## User Enumeration (only if permitted)
# VRFY/EXPN may leak users — check policy first
# nc -nv <IP> 25
#   HELO test.local
#   VRFY administrator
#   EXPN postmaster
# Tooling:
# smtp-user-enum -M VRFY -U users.txt -t <IP>

## Open Relay Test (explicit approval required)
# nmap --script smtp-open-relay -p25 <IP>
# swaks --server <IP> --from a@b.com --to x@y.com --data "Test" --quit-after DATA

## Notes
- Respect rate limits and spam policies.
- Do not send external mail unless specifically in scope.
- Save outputs (nmap -oA, tee) for later reporting.
