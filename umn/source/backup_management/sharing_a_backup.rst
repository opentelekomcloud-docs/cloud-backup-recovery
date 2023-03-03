:original_name: cbr_03_0014.html

.. _cbr_03_0014:

Sharing a Backup
================

You can share a server or disk backup with other domains. Shared backups can be used to create servers or disks.

Context
-------

**Sharer**

-  Backups can only be shared among domains in the same region. They cannot be shared across regions.
-  Encrypted backups cannot be shared.
-  When a sharer deletes a shared backup, the backup will also be deleted from the recipient's account, but the disks or servers previously created using the backup will be retained.

**Recipient**

-  A recipient must have at least one backup vault to store the accepted shared backup, and the vault remaining space must be greater than the size of the backup to be accepted.
-  A recipient can choose to accept ore reject a backup. After accepting a backup, the recipient can use the backup to create new servers or disks.
-  When a sharer deletes a shared backup, the backup will also be deleted from the recipient's account, but the disks or servers previously created using the backup will be retained.

Procedure for the Sharer
------------------------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose a backup tab from the left navigation pane.

#. Click the **Backups** tab and set filter criteria to view the backups.

#. Locate the target backup and choose **More** > **Share Backup** in the **Operation** column.

   The backup name, server name, backup ID, and backup type are displayed.

   -  Sharing a backup


      **Figure 1** Sharing a backup

      |image2|

   a. Click the **Share Backup** tab.
   b. Enter the project ID of the recipient.
   c. Click **Add**. The project ID to be added will be displayed in the list. You can add multiple project IDs. A backup can be shared to a maximum of ten projects.
   d. Click **OK**.

   -  Canceling sharing

   a. Locate the target backup and choose **More** > **Share Backup** in the **Operation** column.
   b. On the displayed page, click the **Cancel Sharing** tab and select the backup that no longer needs to be shared. Then, click **OK**.

Procedure for the Recipient
---------------------------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image3| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose a backup tab from the left navigation pane.

#. On the selected backup page, click the **Backups** tab and then click **Backups Shared with Me**.

#. Ensure that the recipient has at least one backup vault before accepting the shared backup. For how to purchase a backup vault, see :ref:`Step 1: Create a Vault <en-us_topic_0170938140>`.

#. Click **Accept**. On the displayed page, select the vault used to store the shared backup. Ensure that the vault remaining capacity is greater than the backup size.

   **Automatic Association:** Determine whether to enable automatic association for the vault. If you select **Configure**, the vault automatically scans and associates in the next backup period servers that have not been backed up and performs backup.

#. View the shared backup you accepted in the backup list.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001478036586.png
.. |image3| image:: /_static/images/en-us_image_0159365094.png
