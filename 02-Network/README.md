# 02 – Network

Quick references for common network services. Use this alongside 01-Methodology.

## Contents
- ftp.md – anonymous login, brute, file ops
- ssh.md – auth methods, keys, brute hints
- smb.md – enum shares/users, null sessions, SMBMap, nmap NSE
- smtp.md – banner, user enum, mail testing
- snmp.md – snmpwalk/snmp-check basics
- mysql.md – client access, basic queries, nmap NSE
- mssql.md – impacket-mssqlclient basics
- winrm.md – evil-winrm and CrackMapExec tips
- pivoting.md, tunnelling.md – quick notes (full guide in 05-Pivoting)
- udp.md - classic weak Telnet service

## General tips
- Save outputs (nmap -oA, tee) for later grep.
- Try unauthenticated or default creds first.
