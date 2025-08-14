# AD Users — Queries (Linux + PowerShell)

Determine Base DN (Linux)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "" -s base defaultNamingContext

List all users (Linux)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(objectCategory=person)" sAMAccountName userPrincipalName memberOf

Filter examples (Linux)
# Domain Admins members
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(memberOf=CN=Domain Admins,CN=Users,DC=corp,DC=local)" sAMAccountName userPrincipalName
# Disabled users (UAC bit 2)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(&(objectCategory=person)(userAccountControl:1.2.840.113556.1.4.803:=2))" sAMAccountName
# Password never expires (UAC bit 65536)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(&(objectCategory=person)(userAccountControl:1.2.840.113556.1.4.803:=65536))" sAMAccountName
# Smartcard required (bit 262144)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(&(objectCategory=person)(userAccountControl:1.2.840.113556.1.4.803:=262144))" sAMAccountName
# Users with SPN set (service accounts likely)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(&(objectCategory=person)(servicePrincipalName=*))" sAMAccountName servicePrincipalName

Windows (PowerShell; RSAT or on-DC)
# Set base
$Base = (Get-ADDomain).DistinguishedName
# All users
Get-ADUser -Filter * -SearchBase $Base -Properties SamAccountName,Enabled,PasswordNeverExpires | Select SamAccountName,Enabled,PasswordNeverExpires
# Domain Admins members
Get-ADGroupMember -Identity "Domain Admins" -Recursive | Get-ADUser -Properties SamAccountName | Select SamAccountName
# Disabled users
Get-ADUser -Filter 'Enabled -eq $false' -SearchBase $Base | Select SamAccountName
# Password never expires
Get-ADUser -Filter * -SearchBase $Base -Properties PasswordNeverExpires | Where-Object {$_.PasswordNeverExpires -eq $true} | Select SamAccountName
# Users with SPNs
Get-ADUser -Filter {ServicePrincipalName -like "*"} -Properties ServicePrincipalName | Select SamAccountName,ServicePrincipalName

Notes
- Always align with account lockout/PII handling policies.
- Prefer least-information queries and targeted filters.
