# Vulnerability Research

Once you’ve identified services, versions, and potential weaknesses:

## Step 1 – Version Matching
- \`searchsploit <service> <version>\`
- Google: \`"service version exploit"\`
- Exploit-DB, Rapid7 DB, CVE Details

## Step 2 – CVE Lookup
- \`cve-search <service> <version>\`
- NVD (https://nvd.nist.gov)
- SecurityFocus, Vulners

## Step 3 – Proof of Concept (PoC)
- Validate PoC in lab before using on client systems.
- Prioritize RCE, privilege escalation, and auth bypass.

## Step 4 – Exploit Prioritization
- High-impact + low-complexity first
- Map vulnerabilities to potential attack paths
