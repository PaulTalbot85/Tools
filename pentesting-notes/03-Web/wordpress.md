# WordPress Enumeration & Exploitation

## WPScan

wpscan --url <URL> --enumerate u,ap,at --api-token <TOKEN>
wpscan --url <URL> --passwords /usr/share/wordlists/rockyou.txt --usernames admin

Manual Checks

/wp-login.php

/xmlrpc.php

/wp-content/plugins/

/wp-content/themes/

Exploitation

Searchsploit plugins/themes

xmlrpc.php brute force
