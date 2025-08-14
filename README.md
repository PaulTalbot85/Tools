
# Penetration Testing Methodology & Field Notes

This repository contains a structured collection of penetration testing methodology notes, tooling references, and workflow guides. It is designed for **fast reference** during live engagements, Capture the Flag (CTF) challenges, and certification exams such as **eJPT, eCPPT, OSCP, and CPTS**.

The layout follows the logical progression of a penetration test — from scoping and enumeration to exploitation, post-exploitation, pivoting, and reporting.

---

## Repository Structure

| Folder                  | Description                                                                                                                                       |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **01-Methodology**      | End-to-end penetration testing workflow, scoping, engagement rules, and planning.                                                                 |
| **02-Network**          | Network enumeration and exploitation (SMB, SNMP, SSH, NFS, RPC, Kerberos, MSSQL, etc.). Includes quick checks and deep-dive playbooks.            |
| **03-Web**              | Web application testing techniques (HTTP enumeration, authentication bypass, SQL injection, XSS, LFI/RFI, CMS exploits, directory brute forcing). |
| **04-PostExploitation** | Privilege escalation (Windows/Linux), credential harvesting, persistence, and data exfiltration techniques.                                       |
| **05-Pivoting**         | Internal network access, tunnelling, SOCKS proxying, port forwarding, and lateral movement.                                                       |
| **06-Reporting**        | Report templates, note-taking formats, evidence collection checklists, and final deliverable preparation.                                         |
| **07-ActiveDirectory**  | Active Directory enumeration and attack playbooks (BloodHound, SharpHound, PowerView, Kerberos attacks).                                          |

---

## How to Use

1. **Prepare** – Review relevant sections before an engagement to ensure tools and payloads are ready.
2. **Execute** – Use commands and playbooks as a reference during live testing. Adapt parameters to the target environment.
3. **Document** – Record findings in real time using the templates in `06-Reporting`.
4. **Deliver** – Compile evidence and submit a professional penetration testing report.

---

## Key Features

* **Service-specific playbooks** – SMB, MSSQL, WinRM, Kerberos, HTTP, and more.
* **Workflow-driven structure** – Mirrors the real-world testing process.
* **Lab-tested commands** – Extracted from real pentests, CTFs, and certification practice.
* **Reporting-ready** – Includes evidence checklists and structured report templates.
* **Cross-references** – Links between related techniques (e.g., SMB enumeration → Pivoting).

---

## Recommended Workflow

1. **01-Methodology** – Define scope, rules of engagement, and overall plan.
2. **02-Network** – Map the attack surface and enumerate exposed services.
3. **03-Web** – Test web applications for vulnerabilities.
4. **04-PostExploitation** – Escalate privileges and harvest credentials.
5. **05-Pivoting** – Access internal networks and expand the foothold.
6. **07-ActiveDirectory** – Execute AD-specific attacks where applicable.
7. **06-Reporting** – Compile findings into the final report.

---

## Disclaimer

This repository is intended for **authorised security testing and educational purposes only**.
Do not use any techniques or tools described here against systems without explicit written permission.

---

If you want, I can also **cross-link all sections via QUICK\_REF.md files** so you can jump between related playbooks instantly. That would make it even faster to navigate during an engagement.

Do you want me to draft that cross-link system next?

