---
title : "Backup and restore database"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

Amazon RDS automatically initiates and stores backups for your Databse (DB instance) within the backup timeframe you set (If not set, RDS will automatically set to 30 minutes in the timeframe corresponding to each Region specified by AWS).
RDS automatically stores backups with a default retention period of 7 days that you set when you initialize or modify the DB Instance.

![info](/images/restoreandbackup/info-aws-01.png)

RDS will take a snapshot of the DB instance's storage volume and back up the entire DB instance (not just the database).
When necessary, you can restore your database at any point within that timeframe.

![info](/images/restoreandbackup/info-aws-02.png)


In order for automatic backups to take place, you must ensure that:
Your DB instance must be active (AVAILABLE) for the backup to take place. If the DB Instance is in a different state (e.g. STORAGE_FULL) then the backup will not be executed.
Automatic backup will not be performed if you are copying that DB instance in the same Region.


### Content

 - [Initialize Snapshot for Database Instance](5.1-createdbsnapshot/)
 - [Perform DB backup from Snapshot](5.2-restorewithsnapshot//)