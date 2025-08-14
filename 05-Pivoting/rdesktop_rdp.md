# Accessing RDP Over Tunnels

## With Port Forward

ssh -L 3389:10.0.0.5:3389 user@pivot_host
rdesktop 127.0.0.1
With Proxychains

proxychains rdesktop 10.0.0.5
