# AD Computers & Groups — Queries

Linux (ldapsearch)
# Domain Controllers
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(userAccountControl:1.2.840.113556.1.4.803:=8192)" dNSHostName operatingSystem operatingSystemVersion
# All computers
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(objectCategory=computer)" dNSHostName operatingSystem
# Groups (list)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "DC=corp,DC=local" "(objectCategory=group)" cn
# Members of a group (by DN)
ldapsearch -H ldap://<IP> -D "DOMAIN\\USER" -W -b "CN=Domain Admins,CN=Users,DC=corp,DC=local" "(objectClass=*)" member

Windows (PowerShell)
$Base = (Get-ADDomain).DistinguishedName
# Domain Controllers
Get-ADDomainController -Filter * | Select HostName,Site,Enabled
# Computers inventory
Get-ADComputer -Filter * -SearchBase $Base -Properties DNSHostName,OperatingSystem,OperatingSystemVersion | Select DNSHostName,OperatingSystem,OperatingSystemVersion
# All groups
Get-ADGroup -Filter * -SearchBase $Base | Select Name,GroupScope,GroupCategory
# Group members
Get-ADGroupMember "Domain Admins" -Recursive | Select Name, objectClass

Notes
- Large orgs: restrict -SearchBase to specific OUs to avoid huge results.
- Store outputs with host- and date-stamped filenames.
