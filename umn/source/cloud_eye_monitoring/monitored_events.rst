:original_name: cbr_03_0184.html

.. _cbr_03_0184:

Monitored Events
================

Scenarios
---------

On Cloud Eye, you can query CBR events and alarms. You can create alarm rules to be notified when specific events happen.

Namespace
---------

SYS.CBR


Monitored Events
----------------

.. table:: **Table 1** CBR events monitored by Cloud Eye

   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Event Name                       | Event ID                | Severity | Description                                           | Solution                                                                   | Impact                   |
   +==================================+=========================+==========+=======================================================+============================================================================+==========================+
   | Backup creation failed           | backupFailed            | Critical | The backup creation failed.                           | Manually create the backup or contact technical support.                   | Data may be lost.        |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Restoration from a backup failed | restorationFailed       | Critical | The restoration from a backup failed.                 | Restore the resource from another backup or contact technical support.     | Data may be lost.        |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Backup deletion failed           | backupDeleteFailed      | Critical | The backup deletion failed.                           | Try again later or contact technical support.                              | Billing may be abnormal. |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Vault deletion failed            | vaultDeleteFailed       | Critical | The vault deletion failed.                            | Try again later or contact technical support.                              | Billing may be abnormal. |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Replication failure              | replicationFailed       | Critical | The backup replication failed.                        | Try again later or contact technical support.                              | Data may be lost.        |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Backup created                   | backupSucceeded         | Major    | The backup was created.                               | None                                                                       | None                     |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Resource restored from a backup  | restorationSucceeded    | Major    | The resource was restored successfully from a backup. | Check that data is successfully restored.                                  | None                     |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Backup deleted                   | backupDeletionSucceeded | Major    | The backup was deleted successfully.                  | None                                                                       | None                     |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Vault deleted                    | vaultDeletionSucceeded  | Major    | The vault was deleted successfully.                   | None                                                                       | None                     |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Replication succeeded            | replicationSucceeded    | Major    | The backup was replicated successfully.               | None                                                                       | None                     |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Agent offline                    | agentOffline            | Critical | The Agent is offline.                                 | Ensure that the Agent is working properly and can connect to Huawei Cloud. | Backup tasks may fail.   |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
   | Agent online                     | agentOnline             | Major    | The Agent is online.                                  | None                                                                       | None                     |
   +----------------------------------+-------------------------+----------+-------------------------------------------------------+----------------------------------------------------------------------------+--------------------------+
