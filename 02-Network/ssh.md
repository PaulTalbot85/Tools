# SSH — Quick Enum (Authorized targets only)

## Detect & fingerprint
nmap -p 22 -sV --script ssh2-enum-algos,ssh-hostkey <IP>
ssh -o BatchMode=yes <user>@<IP>  # non-interactive banner check

## Hardening checks (read-only)
- Host key algorithms
- Kex algorithms / MACs
- Protocol version

## Notes
- Brute-force is intentionally omitted here; add your approved workflow if allowed.
