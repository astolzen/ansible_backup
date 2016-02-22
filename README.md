# Ansible Backup
#### Network Backup using ansible, rsync and btrfs

## Simple yet fast Backup of multiple Hosts to a central Server running an BTRFS Filesystem.

### Concept:
 - The Backup-Server runs a btrfs subvolume a backup target for all connected host
 - All Hosts back up their data to this subvolume in an individual directory according to the hostname
 - Prior to the backup, a subvolume snapshot is created to enable diff-backups and synthetic full backups
 - at the end of the backup, the tool "bedup" is used to dedup the BTRFS subvolume

