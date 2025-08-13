# Screenshot Best Practices

1. **Always include context**
   - Show the target IP/URL in the screenshot.
   - Highlight the vulnerability output.

2. **Use descriptive filenames**


10.0.0.5_sql_injection_dump.png
10.0.0.5_priv_esc_root.png


3. **Redact sensitive info**
- Use GIMP or Shutter to blur passwords, hashes.

4. **Maintain chronology**
- Store screenshots in numbered folders per host:
  ```
  01_Enumeration/
  02_Exploitation/
  03_PostExploitation/
  ```

5. **Automate if possible**
- Use `gnome-screenshot -a` or `scrot` from CLI.
