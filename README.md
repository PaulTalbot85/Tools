# 🛠️ Penetration Testing Notes & Resources

A curated, structured collection of my penetration testing methodology, tooling references, and workflow notes — built from lab work, CTFs, and certification prep (eJPT, eCPPT, OSCP).

This repo is designed for **quick reference during engagements** and to be **easily navigable** by section.

---

## 📂 Structure

| Folder | Description |
| ------ | ----------- |
| **01-Methodology** | Overall pentest workflow, scoping, engagement rules, reporting structure. |
| **02-Network** | Network-level enumeration & exploitation notes (SMB, SNMP, SSH, etc). |
| **03-Web** | Web application testing (auth bypass, injection, directory enumeration, etc). |
| **04-PostExploitation** | Privilege escalation, credential extraction, persistence techniques. |
| **05-Pivoting** | Tunnelling, SOCKS proxying, port forwarding, lateral movement. |
| **06-Reporting** | Report templates, note-taking strategies, evidence checklists. |

---

## 🎯 Usage

- Keep **small, focused** `.md` files per topic (one vulnerability/service per file).
- Include **commands, payloads, and output examples** where useful.
- Link between sections where techniques overlap (e.g., SMB enumeration → Pivoting).
- Use `.gitkeep` for empty directories so GitHub displays them.

---

## 🔖 Recommended Workflow

1. Start with **01-Methodology** to scope and plan.
2. Use **02-Network** and **03-Web** for enumeration and exploitation.
3. Move to **04-PostExploitation** once a foothold is established.
4. Use **05-Pivoting** when accessing internal networks.
5. Finish with **06-Reporting** for professional documentation.

---

## 📌 Status

- [x] Structure flattened for easy navigation  
- [x] Numbered folders for logical workflow  
- [ ] Populate all sections with lab-tested examples  
- [ ] Add cross-references between sections  

---

**Author:** Paul Talbot  
**License:** MIT  
# Pentest Methodology & Field Notes

A structured, ready-to-use repository for penetration testing workflows, commands, and templates.  
Built for speed during live engagements and certification exams (eCPPT, OSCP, CPTS, etc.).

---

## 📂 Structure

| Folder                | Description |
|-----------------------|-------------|
| `01-Scoping/`         | Target scoping, recon setup, and rules of engagement. |
| `02-Network/`         | Network service enumeration and exploitation (SMB, FTP, SSH, MSSQL, etc.). |
| `03-Web/`             | Web application testing techniques (HTTP enum, SQLi, XSS, LFI/RFI, CMS exploits). |
| `04-PostExploitation/`| Privilege escalation, persistence, credential harvesting, and looting. |
| `05-Pivoting/`        | Internal pivoting, tunnelling, and proxying to reach additional targets. |
| `06-Reporting/`       | Templates, note-taking formats, and evidence management for final deliverables. |

---

## 🛠 How to Use

1. **Prepare** – Before the engagement, review the relevant section(s) for your target scope.
2. **Execute** – Copy/paste commands into your terminal during testing, modifying as needed.
3. **Document** – Use the `note_taking.md` templates to record findings as you go.
4. **Deliver** – Build your final report using the `report_template.md` in `06-Reporting/`.

---

## 📌 Key Features

- **One-file-per-topic** – Find what you need fast (e.g., `smb.md`, `sqli.md`, `windows_priv_esc.md`).
- **Exam-friendly** – Optimised for certifications like eCPPT, OSCP, CPTS.
- **Live engagement ready** – Minimal scrolling, quick command copy/paste.
- **Report-ready** – Built-in evidence checklists and templates.

---

## 🧩 Recommended Workflow

1. **01-Scoping/** – Define targets and rules.  
2. **02-Network/** – Map out network services.  
3. **03-Web/** – Assess HTTP applications.  
4. **04-PostExploitation/** – Escalate, persist, loot.  
5. **05-Pivoting/** – Move laterally.  
6. **06-Reporting/** – Compile and submit findings.

---

## ⚠️ Disclaimer

This repository is for **educational and authorised testing purposes only**.  
Do not use any techniques herein against systems without explicit written permission.

---

> Keep your notes in sync with your latest tools and favourite payloads — the fastest pentesters are the most prepared.

