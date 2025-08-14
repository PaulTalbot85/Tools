# LDAP (389) — Deep Dive (Authorized targets only)

## Discovery
nmap -p 389 -sV --script ldap-rootdse,ldap-search -oA ldap_scan_<IP> <IP>

## Anonymous Bind (if permitted)
ldapwhoami -x -H ldap://<IP>
# If anonymous binds are disabled you'll see an auth error.

## RootDSE (discover naming contexts)
ldapsearch -x -H ldap://<IP> -s base -b "" namingContexts defaultNamingContext rootDomainNamingContext

## STARTTLS Capability Check
# Lists supported controls and features
ldapsearch -x -H ldap://<IP> -s base -b "" supportedSASLMechanisms supportedCapabilities supportedLDAPVersion

## STARTTLS (upgrade to TLS on 389)
ldapwhoami -x -H ldap://<IP> -ZZ
ldapsearch -x -H ldap://<IP> -ZZ -b "" -s base defaultNamingContext

## Authenticated Queries (approved creds)
# Replace BASE with the defaultNamingContext (e.g., DC=corp,DC=local)
ldapsearch -H ldap://<IP> -D "CORP\\<USER>" -W -b "DC=corp,DC=local" -s sub "(objectClass=person)" sAMAccountName userPrincipalName

## Common AD Objects (example filters)
# Users:
ldapsearch -H ldap://<IP> -D "CORP\\<USER>" -W -b "DC=corp,DC=local" "(objectCategory=person)" sAMAccountName memberOf
# Computers:
ldapsearch -H ldap://<IP> -D "CORP\\<USER>" -W -b "DC=corp,DC=local" "(objectCategory=computer)" dNSHostName operatingSystem
# Groups:
ldapsearch -H ldap://<IP> -D "CORP\\<USER>" -W -b "DC=corp,DC=local" "(objectCategory=group)" sAMAccountName member

## Notes
- Treat directory data as sensitive; store outputs with clear filenames.
- Avoid large recursive dumps on production unless explicitly approved.
