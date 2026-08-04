:original_name: cbr_03_0036.html

.. _cbr_03_0036:

Recording CBR Operations Using CTS
==================================

You can use Cloud Trace Service (CTS) to trace operations in CBR.

Prerequisites
-------------

CTS has been enabled.

Key Operations Recorded by CTS
------------------------------

.. table:: **Table 1** CBR operations that can be recorded by CTS

   +---------------------------------------+---------------+--------------------------+
   | Operation                             | Resource Type | Trace Name               |
   +=======================================+===============+==========================+
   | Creating a policy                     | policy        | createPolicy             |
   +---------------------------------------+---------------+--------------------------+
   | Updating a policy                     | policy        | updatePolicy             |
   +---------------------------------------+---------------+--------------------------+
   | Deleting a policy                     | policy        | deletePolicy             |
   +---------------------------------------+---------------+--------------------------+
   | Associating a policy with a vault     | vault         | associatePolicy          |
   +---------------------------------------+---------------+--------------------------+
   | Disassociating a policy from a vault  | vault         | dissociatePolicy         |
   +---------------------------------------+---------------+--------------------------+
   | Creating a vault                      | vault         | createVault              |
   +---------------------------------------+---------------+--------------------------+
   | Modifying a vault                     | vault         | updateVault              |
   +---------------------------------------+---------------+--------------------------+
   | Deleting a vault                      | vault         | deleteVault              |
   +---------------------------------------+---------------+--------------------------+
   | Removing resources                    | vault         | removeResources          |
   +---------------------------------------+---------------+--------------------------+
   | Adding resources                      | vault         | addResources             |
   +---------------------------------------+---------------+--------------------------+
   | Performing a replication              | vault         | replicateVaultBackup     |
   +---------------------------------------+---------------+--------------------------+
   | Performing a backup                   | vault         | createVaultBackup        |
   +---------------------------------------+---------------+--------------------------+
   | Creating a backup                     | backup        | createBackup             |
   +---------------------------------------+---------------+--------------------------+
   | Deleting a backup                     | backup        | deleteBackup             |
   +---------------------------------------+---------------+--------------------------+
   | Synchronizing a backup                | backup        | syncBackup               |
   +---------------------------------------+---------------+--------------------------+
   | Restoring a backup                    | backup        | restoreBackup            |
   +---------------------------------------+---------------+--------------------------+
   | Replicating a backup                  | backup        | replicateBackup          |
   +---------------------------------------+---------------+--------------------------+
   | Setting resources                     | vault         | setResources             |
   +---------------------------------------+---------------+--------------------------+
   | Migrating resources                   | vault         | migrateResources         |
   +---------------------------------------+---------------+--------------------------+
   | Disabling protection                  | vault         | disableProtect           |
   +---------------------------------------+---------------+--------------------------+
   | Deleting backups from a vault         | vault         | deleteVaultBackup        |
   +---------------------------------------+---------------+--------------------------+
   | Synchronizing vault backups           | vault         | syncVaultBackup          |
   +---------------------------------------+---------------+--------------------------+
   | Batch creating or deleting vault tags | vault         | bulkCreateDeleteVaultTag |
   +---------------------------------------+---------------+--------------------------+
   | Creating a tag for a vault            | vault         | createVaultTag           |
   +---------------------------------------+---------------+--------------------------+
   | Deleting tags of a vault              | vault         | deleteVaultTag           |
   +---------------------------------------+---------------+--------------------------+
   | Creating a backup recipient           | backup        | createBackupMember       |
   +---------------------------------------+---------------+--------------------------+
   | Updating a backup recipient           | backup        | updateBackupMember       |
   +---------------------------------------+---------------+--------------------------+
   | Deleting a backup recipient           | backup        | deleteBackupMember       |
   +---------------------------------------+---------------+--------------------------+
   | Updating a backup                     | backup        | updateBackup             |
   +---------------------------------------+---------------+--------------------------+

Viewing Audit Logs
------------------

For how to view audit logs, see section "Querying Real-Time Traces" in the *Cloud Trace Service User Guide*.

Disabling or Enabling a Tracker
-------------------------------

The following procedure illustrates how to disable an existing tracker on the CTS console. After the tracker is disabled, CTS will stop recording operations, but you can still view existing operation records.

#. Log in to the CTS console.

#. In the upper left corner, click |image1| and select a region.

#. Click **Service List** and choose **Management & Deployment** > **Cloud Trace Service**.

#. Choose **Tracker List** in the navigation pane.


   .. figure:: /_static/images/en-us_image_0224256701.png
      :alt: **Figure 1** Viewing trackers

      **Figure 1** Viewing trackers

#. In the tracker list, click **Disable** in the **Operation** column.

#. Click **OK**.

#. After the tracker is disabled, the available operation changes from **Disable** to **Enable**. To enable the tracker again, click **Enable** and then click **OK**. CTS will start recording operations again.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
