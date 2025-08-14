# SSH Pivoting

## Local forward (access remote service from localhost)
ssh -L 127.0.0.1:<LPORT>:<RHOST>:<RPORT> <USER>@<JUMP>

## Dynamic SOCKS (proxy a whole subnet via SOCKS5)
ssh -D 127.0.0.1:<SOCKS_PORT> <USER>@<JUMP>

## Remote forward (expose local service to remote)
ssh -R <RPORT>:127.0.0.1:<LPORT> <USER>@<JUMP>
