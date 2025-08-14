# PowerView — Quick Enumeration (Authorized targets only)

Load PowerView
  Import-Module .\PowerView.ps1
  Set-ExecutionPolicy Bypass -Scope Process

Domain Basics
  Get-Domain                     # domain info
  Get-DomainPolicy               # password and lockout policy
  Get-Forest, Get-ForestTrust    # forest and trusts
  Get-DomainTrust                # domain trusts

Users and Groups
  Get-DomainUser -Identity <user> -Properties samaccountname,memberOf,lastlogon
  Get-DomainUser -SPN            # users with SPNs (service accounts likely)
  Get-DomainGroup                # list groups
  Get-DomainGroupMember "Domain Admins" -Recursive

Computers and Sessions
  Get-DomainComputer -Properties dnshostname,operatingsystem,serviceprincipalname
  Get-NetSession -ComputerName <HOST>            # requires rights; can be noisy
  Get-NetLoggedon -ComputerName <HOST>           # requires rights; can be noisy

ACLs and Rights (read-only views)
  Get-ObjectACL -SamAccountName "Domain Admins" -ResolveGUIDs
  Find-InterestingDomainAcl -ResolveGUIDs
  Get-DomainObjectOwner -Identity "CN=AdminSDHolder,CN=System,<DN>"

Local Admin Rights (mapping)
  Find-LocalAdminAccess -Verbose                  # enumerate where current user is local admin

Shares and Files (evidence-only)
  Find-DomainShare
  Find-InterestingDomainShareFile -Include "password","creds","backup","vnc","keepass"

Delegation and Protections
  Get-DomainUser -TrustedToAuth                   # unconstrained delegation (rare)
  Get-DomainComputer -TrustedToAuth
  Get-DomainObjectAcl -SearchBase "CN=AdminSDHolder,CN=System,<DN>" -ResolveGUIDs
  Get-DomainGPO, Get-DomainOU, Get-DomainGPOUserLocalGroupMapping

Common DN Examples
  DC=corp,DC=local
  CN=Users,DC=corp,DC=local

Safety Notes
- Enumeration only: do not alter memberships, GPOs, or ACLs.
- Throttle noisy functions on production; coordinate with blue team.
- Record command lines, timestamps, and output paths for reporting.
