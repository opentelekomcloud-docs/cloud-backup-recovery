:original_name: cbr_01_0009.html

.. _cbr_01_0009:

Constraints
===========

General
-------

-  A vault can be associated with only one backup policy.
-  A vault can be associated with only one replication policy.
-  A vault can be associated with a maximum of 256 resources.
-  A maximum of 32 backup policies and 32 replication policies can be created.
-  Only backups in the **Available** or **Locked** vaults can be used to restore data.
-  Backups in a **Deleting** vault cannot be deleted.
-  When Storage Disaster Recovery Service (SDRS) is used to set up disaster recovery for cloud servers, restorations can be performed at the disaster recovery site only after protection is disabled.
-  Backups cannot be downloaded to a local PC or uploaded to OBS.
-  A vault and its associated servers or disks must be in the same region.
-  Concurrent data restoration is not supported.
-  Auto capacity expansion does not take effect if it is enabled after the vault is full.

Cloud Disk Backup
-----------------

-  Only disks in the **Available** or **In-use** state can be backed up.
-  Frozen disks in the retention period cannot be backed up.
-  A new disk must be at least as large as the backup's source disk.
-  Cloud disk backups cannot be replicated to other regions.

Cloud Server Backup
-------------------

-  A maximum of 10 shared disks can be backed up with a cloud server.
-  Only backups in the **Available** or **Locked** vaults can be used to create images.
-  Frozen servers in the retention period cannot be backed up.
-  You can back up specific disks on a server, but such a backup must be restored as a whole. File- or directory-level restoration is not supported.
-  When SDRS is used to set up disaster recovery for cloud servers, restorations can be performed at the disaster recovery site only after protection is disabled.
-  You are advised not to back up a server whose disk size exceeds 4 TB.
-  Backups can be replicated only to regions that have replication capabilities.

   -  A backup can be replicated only when it meets all of the following conditions:

      #. It is an ECS backup.
      #. It contains system disk data.
      #. It is in the **Available** state.

   -  Only backups can be replicated. Backup replicas cannot be replicated again but can be used to create images.
   -  A backup can be replicated to multiple regions but can have only one replica in each destination region. The replication rule varies with the replication method:

      -  Manual replication: A backup can be replicated to the destination region as long as it has no replica in that region. A backup can be replicated again if its replica in the destination region has been deleted.
      -  Policy-based replication: A backup can only be automatically replicated to a destination region once. It cannot be automatically replicated to that region again, even if its replica has been deleted.

   -  Only replication-supported regions can be selected as destination regions.

SFS Turbo Backup
----------------

-  Only file systems in the **Available** state can be backed up.
-  An SFS Turbo file system backup cannot be used to restore data to the original file system.
