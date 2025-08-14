# LDAPS (636) — Deep Dive (Authorized targets only)

## Discovery
nmap -p 636 -sV -oA ldaps_scan_<IP> <IP>

## Test TLS Handshake
openssl s_client -connect <IP>:636 </dev/null

## Simple Bind over LDAPS (anonymous rarely allowed)
ldapwhoami -x -H ldaps://<IP>
# If server requires auth, use domain creds:
ldapwhoami -H ldaps://<IP> -D "CORP\\<USER>" -W

## Authenticated Search (approved creds)
# First, get defaultNamingContext via RootDSE (may require ldap:// with -ZZ):
#   ldapsearch -x -H ldap://<IP> -ZZ -b "" -s base defaultNamingContext
# Then query over ldaps://:
ldapsearch -H ldaps://<IP> -D "CORP\\<USER>" -W -b "DC=corp,DC=local" "(objectClass=person)" sAMAccountName mail memberOf

## Certificate Validation
# In production, validate certs with -d nss or system trust; in labs you may need to ignore validation errors.

## Notes
- Prefer LDAPS or STARTTLS for credential privacy.
- Log exact commands and truncate large outputs in reports.
