# RPC — Deep Dive (Authorized targets only)

## Unix Portmapper (rpcbind)
nmap -p 111 -sV --script rpcinfo -oA rpc_scan_<IP> <IP>
rpcinfo -p <IP>

## NFS via RPC (if present)
# See 02-Network/nfs.md for mounting/export checks

## Windows RPC quick checks (unauth where allowed)
# rpcclient -U "" -N <IP>
#   enumdomusers
#   enumdomgroups
#   queryuser <RID>

## Notes
- Portmapper lists RPC programs and ports; use it to drive targeted checks.
- Avoid authenticated RPC actions unless in scope.
