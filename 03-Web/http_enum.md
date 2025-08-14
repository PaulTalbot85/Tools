# HTTP — Deep Dive (Authorized targets only)

## First touch (save every step)
curl -i http://<IP>/
curl -Ik https://<IP>/
whatweb http://<IP>/ | tee http_whatweb_<IP>.txt
nmap -p 80,443 -sV --script http-title,http-headers,http-server-header -oA http_scan_<IP> <IP>

## TLS & ciphers (if HTTPS)
openssl s_client -connect <IP>:443 -servername <HOST> </dev/null | tee tls_<IP>.txt
nmap --script ssl-enum-ciphers -p 443 -oA ssl_ciphers_<IP> <IP>

## Low-hanging files
curl -s http://<IP>/robots.txt
curl -s http://<IP>/sitemap.xml

## Virtual hosts (in scope)
# for d in $(cat wordlist.txt); do
#   curl -s -H "Host: $d.<domain>" http://<IP>/ | grep -i -E "(title|error|unique string)";
# done

## Parameter & directory mapping
# see 03-Web/dir_enum.md for deeper wordlists and strategies

## Notes
- Always record full URLs, parameters, cookies, and status codes.
