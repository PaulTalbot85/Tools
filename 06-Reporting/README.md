# 06 – Reporting & Documentation

Templates, formats, and guidelines for documenting penetration test findings during and after engagements.  
Keep these in sync with your client’s reporting requirements or your certification exam rubric.

---

## 📌 Contents

| File                  | Description |
|-----------------------|-------------|
| `report_template.md`  | Full penetration testing report template (executive + technical). |
| `note_taking.md`      | Live note-taking structure for each host/service. |
| `screenshot_tips.md`  | How to capture and organise screenshots as evidence. |
| `evidence_checklist.md` | Quick checklist to ensure you capture all evidence for findings. |

---

## 🛠 Usage

1. **While Testing:** Use `note_taking.md` to record steps, commands, and results.
2. **Capture Evidence:** Use `screenshot_tips.md` and `evidence_checklist.md` to ensure everything is documented.
3. **Final Report:** Fill in `report_template.md` with findings, proof of exploitation, and remediation.

---

## 🔍 Quick Start

| Task                  | Command/Tip |
|-----------------------|-------------|
| Timestamp logs        | Prefix commands with `date &&` |
| Save console output   | `tee -a notes.txt` |
| Screenshot tool       | `gnome-screenshot -a` or `Shift+PrtSc` |
| Redact sensitive data | Use `GIMP` or `Shutter` before submission |

---

> **Tip:** Write the report as you go — this prevents forgetting important details later.
