# 01 – Methodology

This section contains high-level penetration testing workflows, checklists, and reference material to guide you through engagements and labs.  
It’s designed to be the **first place you look** when starting an assessment.

---

## 📌 Contents

| File            | Description |
|-----------------|-------------|
| `workflow.md`   | Step-by-step methodology for network & web penetration testing. Includes host discovery, scanning, enumeration, and reporting. |
| `checklists.md` | Quick reference checklists for each phase of an engagement. |
| `reporting.md`  | Report structure and note-taking best practices. |

---

## 🛠 Usage

1. **Start Here:** Follow the `workflow.md` from top to bottom for each target.
2. **Reference Commands:** Use inline commands for quick copy-paste during testing.
3. **Record Findings:** Save all results in the reporting template or your own format.
4. **Repeat:** This is a loop — once you’ve exploited and escalated, come back for post-exploitation enumeration.

---

## 🔍 Key Features

- **Cross-Platform Commands:** Linux, Windows, and macOS equivalents where possible.
- **Multiple Techniques:** Fast and full scans, passive recon, and detailed service enumeration.
- **Tool Integration:** Commands ready to feed into Metasploit, CrackMapExec, and other frameworks.
- **Output Options:** Examples for saving results in all major formats.

---

## 📂 Recommended Workflow

1. **Information Gathering** – Identify live hosts, map the network, collect OSINT.
2. **Enumeration** – Discover services, versions, configurations, and potential vulnerabilities.
3. **Exploitation** – Use findings to gain initial access.
4. **Privilege Escalation** – Elevate to higher privileges.
5. **Post-Exploitation** – Maintain access, pivot, and loot data.
6. **Reporting** – Document everything clearly for later review.

---

> **Tip:** Keep a copy of `workflow.md` open in a split terminal or second screen during live testing.
