# HTTP — Quick Enumeration (Authorized targets only)

## First touch
curl -I http://<IP>/
whatweb http://<IP>/
nmap -p 80,443 -sV --script http-title,http-headers,http-server-header <IP>

## Robots / sitemap
curl -s http://<IP>/robots.txt
curl -s http://<IP>/sitemap.xml

## Tech & headers to note
- Server, X-Powered-By, Cookies, CSP
- Redirects / VHosts (try Host: headers if in scope)
