# LDAP Basics (AD) — Authorized targets only

Discovery (Nmap)
nmap -p 389,636 -sV --script ldap-rootdse,ldap-search -oA ldap_ports_<IP> <IP>

Anonymous bind (rare in AD)
ldapwhoami -x -H ldap://<IP>

RootDSE (naming contexts)
ldapsearch -x -H ldap://<IP> -b "" -s base namingContexts defaultNamingContext rootDomainNamingContext subschemaSubentry

STARTTLS on 389
ldapwhoami -x -H ldap://<IP> -ZZ
ldapsearch -x -H ldap://<IP> -ZZ -b "" -s base defaultNamingContext

LDAPS on 636
openssl s_client -connect <IP>:636 </dev/null
ldapwhoami -x -H ldaps://<IP>

Authenticated bind (Linux)
# Replace DOMAIN, USER; supply password when prompted
ldapwhoami -H ldap://<IP> -D "DOMAIN\\USER" -W
# Get default naming context
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "" -s base defaultNamingContext

Useful Base DN examples
DC=corp,DC=local
DC=contoso,DC=com

Common attributes to request
dn, cn, sAMAccountName, userPrincipalName, memberOf, objectSid, objectGUID, userAccountControl

Safety notes
- Prefer STARTTLS/LDAPS to protect credentials.
- Avoid whole-directory dumps on prod; use targeted filters.
