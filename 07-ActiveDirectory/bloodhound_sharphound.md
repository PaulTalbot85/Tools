# BloodHound / SharpHound — Quick Collection (Authorized targets only)

Purpose
- Safely enumerate AD relationships for path analysis without changing state.
- Use least-privileged domain creds where possible.

Collector Options (choose one)

1) PowerShell (built-in SharpHound collector)
  Import-Module .\SharpHound.ps1
  Invoke-BloodHound -CollectionMethod Default -Domain <domain.local> -ZipFileName bh_<HOST>_default.zip

  Common collection methods (mix as needed):
  - CollectionMethod Default         balanced set
  - CollectionMethod ACL,GPOLocalGroup,Session,Trusts,LoggedOn
  - Stealth options: -ExcludeDCs, -Throttle 1000, -Jitter 20

2) SharpHound.exe (binary collector)
  .\SharpHound.exe --CollectionMethods Default --Domain <domain.local> --ZipFileName bh_<HOST>_default.zip
  Throttling example:
  .\SharpHound.exe --Jitter 20 --Throttle 1000 --RandomFilenames

3) Linux collection helpers (when Windows access is limited)
  - secretsdump.py, GetADUsers.py, impacket-GetUserSPNs etc. produce partial data only.
  - Prefer native SharpHound from a domain-joined context for full fidelity.

Operational Tips
- Run from a low-noise host (workstation or jump box).
- Respect lockout and monitoring. Use throttling and jitters on production.
- Never change GPOs, ACLs, or memberships during enumeration.

Ingesting into BloodHound
1) Start Neo4j (or BloodHound CE) locally.
2) Launch BloodHound UI and log in.
3) Drag and drop the generated ZIP(s) into the UI to ingest.
4) Run built-in queries:
   - Find Shortest Paths to Domain Admins
   - Find Principals with DCSync Rights
   - Find Kerberoastable Accounts
   - Find AS-REP Roastable Users
   - Find Local Admin Rights

Exporting Evidence
- Export query results as PNG or JSON.
- Keep original ZIPs and a notes file listing:
  host used, date/time, collector version, command line, throttling settings.

Cleanup
- Remove collectors and ZIPs from client systems per data handling policy.

Notes
- This guide is enumeration-only. Exploitation of identified paths must be in scope and explicitly approved.
