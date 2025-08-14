# XSS (Authorized targets only)

## Benign reflection test
- <script>alert(1)</script>
- <img src=x onerror=alert(1)>

## Notes
- Use non-destructive payloads for validation.
- Follow client redaction policy for evidence.
