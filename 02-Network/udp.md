# Port 23 – Telnet

## Overview

* **Port**: 23/tcp
* **Service**: Telnet (Telecommunication Network Protocol)
* **Purpose**: Provides remote, text-based access to a system’s shell.
* **Status**: Legacy and insecure. Telnet has been replaced by SSH in modern systems.

## Security Issues

* **Cleartext transmission**: No encryption. Usernames, passwords, and commands are sent in plaintext.
* **Weak or default configurations**:

  * Some systems allow login without a password.
  * Default or easily guessable credentials are common (e.g., `admin:admin`, `root:root`).
* **Privilege escalation risk**: Misconfigurations may allow root login directly, bypassing normal security restrictions.

## Enumeration and Exploitation

1. **Banner grabbing**

   ```bash
   telnet <target-ip> 23
   ```

   * Check for service banners, prompts, or direct shell access.
   * Banners may reveal hostname or operating system information.

2. **Authentication tests**

   * Test common usernames such as `root`, `admin`, `guest`, or `user`.
   * Attempt blank passwords or common defaults.
   * If credentials are unknown, correlate with information from other services (e.g., SMB shares, web apps, databases).

3. **Post-login activities**

   * Verify privileges:

     ```bash
     whoami
     id
     hostname
     uname -a
     ```
   * Explore the file system for flags, configuration files, or credentials.

## Real-World Implications

* Insecure Telnet configurations can allow unauthorized remote root access.
* Attackers can sniff traffic to capture plaintext credentials.
* Regulatory standards prohibit Telnet in production environments due to the lack of encryption.

## Defensive Best Practices

* Disable Telnet service entirely.
* Replace with SSH for secure remote access.
* Enforce strong authentication policies.
* Restrict network exposure through segmentation and firewalls.

## Lab Example

In a Hack The Box Starting Point exercise, Telnet allowed direct login as `root` without a password. This illustrates why Telnet is considered insecure and should not be used in modern environments.

---
