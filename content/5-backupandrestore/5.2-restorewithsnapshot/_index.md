---
title : "Restore with DB snapshot"
date : "2025-10-02"
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---


1. In the RDS . interface
- Select Snapshots
- Select the snapshot you just created
- Select Actions
- Select Restore snapshot


![info](/images/restoreandbackup/restore-snapshot-setup-01.png?featherlight=false&width=90pc)

2. In Settings
- DB instance identifier, enter wordpress-db-restore
- Choose create a standby instance because we use multi AZ initially


![info](/images/restoreandbackup/restore-snapshot-setup-02.png?featherlight=false&width=90pc)

3. Set up network for restore Database instance

![info](/images/restoreandbackup/restore-snapshot-setup-03.png?featherlight=false&width=90pc)

4. Select Restore DB instance

![info](/images/restoreandbackup/restore-snapshot-setup-04.png?featherlight=false&width=90pc)

5. Wait for about 10 minutes, the status of the database changes to Available and is successfully initialized.

![info](/images/restoreandbackup/restore-snapshot-setup-05.png?featherlight=false&width=90pc)