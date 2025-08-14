# SMTP — Quick Enum (Authorized targets only)

## Discovery
nmap -p 25,465,587 -sV --script smtp-commands,smtp-open-relay <IP>

## Safe checks
swaks --server <IP> --helo test.local --quit-after HELO

## Notes
- Do not spam or relay test beyond scope.
