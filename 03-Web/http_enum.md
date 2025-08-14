# HTTP/HTTPS Enumeration

## Nmap NSE

nmap -p80,443,8080,8443 -sV -sC -O <TARGET_IP>
nmap --script http-enum,http-title,http-headers,http-methods -p80,443 <TARGET_IP>

Technology Fingerprinting

whatweb <URL>
whatweb --aggression 3 <URL>
wappalyzer <URL>   # browser extension

Header Grab

curl -I <URL>
curl -s -D- <URL> | less

Robots & Sitemap

curl -s <URL>/robots.txt
curl -s <URL>/sitemap.xml

SSL/TLS

nmap --script ssl-cert,ssl-enum-ciphers -p443 <TARGET_IP>
openssl s_client -connect <TARGET_IP>:443
