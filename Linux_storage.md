# Linux storage cheatsheet

## LVM RAID

**Restoring failed RAID:**

```bash
sfdisk -d /dev/sda | sfdisk /dev/sdb
mdadm /dev/md0 -a /dev/sdb1
cat /proc/mdstat
```