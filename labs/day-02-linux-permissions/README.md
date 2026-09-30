```
# Day 2 — Linux Users, Groups, and File Permissions

**Date:** September 29, 2026  
**Status:** Complete  
**Platform:** VMware Fusion on macOS  
**Virtual Machine:** Ubuntu-IT-Lab  
**Operating System:** Ubuntu 22.04.5 LTS  

## Objective
Configure role-based access control (RBAC), enforce the principle of least privilege on a shared directory, and resolve a simulated user access ticket.

## Work Completed
- Verified administrative identity (`jonathan`) and `sudo` group membership.
- Created employee accounts `alice` and `bob`.
- Established departmental group `finance` and assigned `alice`.
- Created shared directory `/srv/finance` with group ownership set to `finance`.
- Enforced `chmod 770` permissions so only `finance` group members can access the folder.
- Tested permissions: `alice` succeeded in file creation; `bob` was blocked (`Permission denied`).
- Resolved Ticket #1042: Added `bob` to the `finance` group after HR confirmation and verified access restoration.

## Key Commands Executed
```bash
whoami &amp;&amp; id &amp;&amp; groups
sudo adduser alice
sudo adduser bob
sudo groupadd finance
sudo usermod -aG finance alice
sudo mkdir -p /srv/finance
sudo chgrp finance /srv/finance
sudo chmod 770 /srv/finance
sudo -u alice touch /srv/finance/alice_test.txt
sudo -u bob touch /srv/finance/bob_test.txt
sudo usermod -aG finance bob

```

## Result

Role-based access control and least-privilege directory restrictions are fully operational and verified.

```

---
```
