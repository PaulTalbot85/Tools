# Professional Penetration Testing Methodology

This section provides a structured, standards-aligned methodology for conducting penetration tests.
It is based on **PTES (Penetration Testing Execution Standard)** and **NIST SP 800-115** principles, refined through practical use in authorised client engagements, labs, and certification environments.

---

## Sections

| File                        | Description                                                                                                                   |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **01-overview\.md**         | High-level testing workflow, engagement phases, and methodology reference.                                                    |
| **02-scoping-checklist.md** | Questions and information to gather before starting the engagement. Defines scope, rules of engagement, and success criteria. |
| **03-host-discovery.md**    | Techniques and tools for identifying live hosts within the target scope.                                                      |
| **04-port-scanning.md**     | Fast and comprehensive port scanning strategies, including TCP, UDP, and service version detection.                           |
| **05-service-enum.md**      | Enumeration approaches for discovered services, including common protocol checks and deeper manual inspection.                |
| **06-passive-recon.md**     | Non-intrusive intelligence gathering from public sources (OSINT) and passive network monitoring.                              |
| **07-dns-enum.md**          | DNS reconnaissance methods, including zone transfers, subdomain discovery, and record analysis.                               |
| **08-vuln-research.md**     | Identifying, validating, and prioritising vulnerabilities based on discovered services and applications.                      |
| **09-initial-access.md**    | Techniques for gaining a foothold in the target environment (exploitation, credential attacks, web entry points).             |
| **10-reporting-notes.md**   | Guidelines for documenting findings, structuring the final report, and maintaining evidence.                                  |
| **QUICK\_REF.md**           | One-page methodology cheat sheet for use during live engagements.                                                             |

---

## Usage

1. **Plan** – Review `01-overview.md` and `02-scoping-checklist.md` before testing to define the scope and objectives.
2. **Enumerate** – Follow `03-host-discovery.md` through `07-dns-enum.md` to map the target environment.
3. **Assess** – Use `08-vuln-research.md` to match findings with known exploits or misconfigurations.
4. **Exploit** – Reference `09-initial-access.md` for initial compromise techniques.
5. **Document** – Use `10-reporting-notes.md` to record all evidence for final deliverables.
6. **Quick Reference** – Keep `QUICK_REF.md` open for rapid access to common commands and workflows.

---

## Alignment with Standards

This methodology aligns with:

* **PTES** – Penetration Testing Execution Standard
* **NIST SP 800-115** – Technical Guide to Information Security Testing and Assessment

It is designed to be flexible enough for certification exams, CTFs, and real-world client engagements.

---

## Disclaimer

This methodology is for use in **authorised penetration testing and educational environments only**.
Do not apply any techniques against systems without explicit written permission.

---
