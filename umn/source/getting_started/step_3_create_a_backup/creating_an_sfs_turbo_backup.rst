:original_name: cbr_02_0012.html

.. _cbr_02_0012:

Creating an SFS Turbo Backup
============================

This section describes how to quickly create an SFS Turbo file system backup.

Backing up an SFS Turbo file system does not impact the file system performance. To ensure data integrity, you are advised to back up the file system during off-peak hours when no data is written to the file system.

Prerequisites
-------------

A file system can be backed up only when its status is **Available** or **In-use**. If you have performed operations such as expanding, mounting, unmounting, or deleting a file system, refresh the page first to ensure that the operation is complete and then determine whether to back up the file system.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery** > **SFS Turbo Backups**.

#. On the **SFS Turbo Backups** page, click the **Vaults** tab and find the vault to which the file system is associated.

#. Choose **More** > **Perform Backup** in the **Operation** column. In the file system list, select the file system to be backed up. After a file system is selected, it is added to the list of selected file systems. See :ref:`Figure 1 <cbr_02_0012__fig2557455115213>`.

   .. _cbr_02_0012__fig2557455115213:

   **Figure 1** Selecting the file system to be backed up

   |image2|

#. Set **Name** and **Description** for the backup. :ref:`Table 1 <cbr_02_0012__table4829135361311>` describes the parameters.

   .. _cbr_02_0012__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                      | Remarks               |
      +=======================+==================================================================================================================================================================+=======================+
      | Name                  | Name of the backup you are creating.                                                                                                                             | manualbk_d819         |
      |                       |                                                                                                                                                                  |                       |
      |                       | A name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-).                                                               |                       |
      |                       |                                                                                                                                                                  |                       |
      |                       | .. note::                                                                                                                                                        |                       |
      |                       |                                                                                                                                                                  |                       |
      |                       |    You can also use the default name **manualbk\_**\ *xxxx*.                                                                                                     |                       |
      |                       |                                                                                                                                                                  |                       |
      |                       |    If multiple file systems are to be backed up, the system automatically adds suffixes to their backup names, for example, **backup-0001** and **backup-0002**. |                       |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Description of the backup.                                                                                                                                       | --                    |
      |                       |                                                                                                                                                                  |                       |
      |                       | It cannot exceed 255 characters.                                                                                                                                 |                       |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. (Optional) Click the vault name to go to the vault details page. On the **Associated File Systems** tab page, locate the target file system. Click **Perform Backup** in the **Operation** column of the file system. See :ref:`Figure 2 <cbr_02_0012__fig7287161212118>`.

   .. _cbr_02_0012__fig7287161212118:

   **Figure 2** Perform Backup

   |image3|

#. Click **Yes**. CBR automatically creates a backup for the file system.

   On the **Backups** tab page, if the status of the backup is **Available**, the backup task is successful.

   .. note::

      If you delete data from the file system during the backup, the deleted data may fail to be backed up. To ensure data integrity, you are advised to wait until the backup task is complete and then make the change and perform a backup again.

   After the backup is complete, you can create a new SFS Turbo file system using the backup. For details, see :ref:`Using a Backup to Create a File System <cbr_03_0107>`.

.. |image1| image:: /_static/images/en-us_image_0219685945.png
.. |image2| image:: /_static/images/en-us_image_0000001091176765.png
.. |image3| image:: /_static/images/en-us_image_0000001091021893.png
