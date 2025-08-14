# SSH Pivoting — Deep Dive (Authorized targets only)

## Local port forward (use local tool against remote)
ssh -L 127.0.0.1:<LPORT>:<RHOST>:<RPORT> <USER>@<JUMP>
# Example: expose remote 10.10.10.5:1433 locally as 127.0.0.1:1433

## Dynamic SOCKS proxy
ssh -D 127.0.0.1:<SOCKS_PORT> <USER>@<JUMP>
# Then set proxychains to use socks5 127.0.0.1 <SOCKS_PORT>

## ProxyCommand chain (jump host)
# ~/.ssh/config
# Host internal-*
#   ProxyCommand ssh -W %h:%p <USER>@<JUMP>
# ssh <USER>@internal-10.0.0.5

## Notes
- Document each tunnel and keep a simple diagram of routes.
