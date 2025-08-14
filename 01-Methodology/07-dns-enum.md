# 07 – DNS Enumeration

## Purpose
Map domain relationships, subdomains, and internal records.

---

## Steps
1. Identify nameservers:
dig ns target.com

Test for zone transfer:
dig axfr @<nameserver> target.com

Subdomain brute force:
gobuster dns -d target.com -w subdomains.txt

OpSec Note
Excessive DNS queries may alert monitoring systems — use caching resolvers where appropriate.
