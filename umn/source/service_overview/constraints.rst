:original_name: cbr_01_0009.html

.. _cbr_01_0009:

Constraints
===========

General
-------

-  A vault can be associated with only one backup policy.
-  A vault can be associated with a maximum of 256 resources.
-  A maximum of 32 backup policies can be created.
-  Only the backups in a vault whose status is **Available** or **Locked** can be used for data restoration.
-  Backups in a vault whose status is **Deleting** cannot be deleted.
-  When Storage Disaster Recovery Service (SDRS) is used to set up disaster recovery for cloud servers, restorations can be performed at the disaster recovery site only after protection is disabled.
-  Backups cannot be downloaded to a local PC or uploaded to OBS.
-  A vault and its associated servers or disks must be in the same region.

Cloud Disk Backup
-----------------

-  Only disks in the **Available** or **In-use** state can be backed up.
-  A new disk must be at least as large as the backup's source disk.

Cloud Server Backup
-------------------

-  Shared disks on a server can be backed up, but there can be no more than 10 shared disks.
-  Only backups in a vault whose status is **Available** or **Locked** can be used to create images.
-  You can choose to back up only specified disks on a server, but such a backup of disks must be restored as a whole. File- or directory-level restoration is not supported.
-  When SDRS is used to set up disaster recovery for cloud servers, restorations can be performed at the disaster recovery site only after protection is disabled.
-  You are advised not to back up a server whose disk size exceeds 4 TB.

SFS Turbo Backup
----------------

-  Only file systems in the **Available** state can be backed up.
-  An SFS Turbo file system backup cannot be used to restore data to the original file system.
