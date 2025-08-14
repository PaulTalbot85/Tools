# SOCKS Proxy & Proxychains

## proxychains.conf snippet
# dynamic_chain
# proxy_dns
# [ProxyList]
# socks5  127.0.0.1 1080

## Usage
proxychains -q nmap -sT -Pn -p <PORTS> <HOST>
proxychains -q curl http://<TARGET>/
