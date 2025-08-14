# NFS — Deep Dive (Authorized targets only)

## Discovery
nmap -p 111,2049 -sV --script nfs-ls,nfs-statfs,nfs-showmount -oA nfs_scan_<IP> <IP>

## Show exports (read-only)
showmount -e <IP>

## Mount an export (read-only where possible)
sudo mkdir -p /mnt/nfs_<IP>
sudo mount -o ro <IP>:/<export> /mnt/nfs_<IP>
ls -lah /mnt/nfs_<IP>
sudo umount /mnt/nfs_<IP>

## UID/GID mapping notes
- NFS relies on UID/GID; misconfigurations may allow unintended access.
- Prefer RO mounting for evidence; do not write unless explicitly permitted.

## Evidence
- Save `showmount -e` output and export listings.
