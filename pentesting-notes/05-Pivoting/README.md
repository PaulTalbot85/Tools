# 05 – Pivoting & Tunnelling

Techniques for moving from one compromised host to another and accessing internal network resources.  
Includes port forwarding, SOCKS proxies, SSH tunnels, and pivoting via Meterpreter or SSH.

---

## 📌 Contents

| File                | Description |
|---------------------|-------------|
| `meterpreter_pivot.md` | Pivoting using Meterpreter's `autoroute` and port forwarding. |
| `ssh_pivot.md`      | SSH local, remote, and dynamic port forwarding. |
| `chisel_socat.md`   | Using Chisel or Socat for tunnelling. |
| `socks_proxy.md`    | SOCKS4/5 proxy setup and usage. |
| `rdesktop_rdp.md`   | Accessing RDP over tunnels or proxies. |

---

## 🛠 Usage

1. **Compromise Initial Host** – Get shell or Meterpreter session.
2. **Add Routes** – Make the internal network reachable.
3. **Forward Ports** – Expose internal services locally.
4. **Proxy Traffic** – Use SOCKS or SSH dynamic forwarding for full internal access.
5. **Access Services** – RDP, SMB, HTTP, etc., through tunnels.

---

## 🔍 Quick Start Commands

| Task                | Command |
|---------------------|---------|
| Meterpreter route   | `run autoroute -s 10.0.0.0/24` |
| Port forward        | `portfwd add -l 8080 -p 80 -r 10.0.0.5` |
| SOCKS proxy         | `use auxiliary/server/socks_proxy` |
| SSH dynamic         | `ssh -D 1080 user@host` |

---

> **Tip:** Combine `proxychains` with a SOCKS proxy for scanning and enumeration of internal hosts without exposing your tools directly.
