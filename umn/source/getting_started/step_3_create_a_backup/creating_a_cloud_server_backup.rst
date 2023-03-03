:original_name: cbr_02_0006.html

.. _cbr_02_0006:

Creating a Cloud Server Backup
==============================

This section describes how to quickly create a cloud server backup.

If you do not need an ECS for the moment, you can back up the ECS and then delete it. When you want an ECS later, you can create an image from the ECS backup and use the image to create ECSs.

Backing up a server does not impact the server performance. To ensure data integrity, you are advised to back up the server during off-peak hours when no data is written to the disks.

Prerequisites
-------------

-  Only servers in the **Running** or **Stopped** state can be backed up.
-  At least one server backup vault is available.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose a backup tab from the left navigation pane.

#. On the **Cloud Server Backups** page, click the **Vaults** tab and find the vault to which the server is associated.

#. Choose **More** > **Perform Backup** in the **Operation** column. In the server list, select the server you want to back up. After a server is selected, it is added to the list of selected servers. See :ref:`Figure 1 <cbr_02_0006__fig2557455115213>`.

   .. _cbr_02_0006__fig2557455115213:

   **Figure 1** Selecting the server to be backed up

   |image2|

#. Set **Name** and **Description** for the backup. :ref:`Table 1 <cbr_02_0006__table4829135361311>` describes the parameters.

   .. _cbr_02_0006__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                 | Remarks               |
      +=======================+=============================================================================================================================================================+=======================+
      | Name                  | Name of the backup you are creating.                                                                                                                        | manualbk_d819         |
      |                       |                                                                                                                                                             |                       |
      |                       | A name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-).                                                          |                       |
      |                       |                                                                                                                                                             |                       |
      |                       | .. note::                                                                                                                                                   |                       |
      |                       |                                                                                                                                                             |                       |
      |                       |    You can also use the default name **manualbk\_**\ *xxxx*.                                                                                                |                       |
      |                       |                                                                                                                                                             |                       |
      |                       |    If multiple servers are to be backed up, the system automatically adds suffixes to their backup names, for example, **backup-0001** and **backup-0002**. |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Description of the backup.                                                                                                                                  | --                    |
      |                       |                                                                                                                                                             |                       |
      |                       | It cannot exceed 255 characters.                                                                                                                            |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Choose whether to enable full backup. If full backup is enabled, CBR performs a full backup on every associated server, which requires a larger capacity compared to an incremental backup. See :ref:`Figure 2 <cbr_02_0006__fig789511544815>`.

   .. _cbr_02_0006__fig789511544815:

   **Figure 2** Selecting full backup

   |image3|

#. (Optional) Click the vault name to go to the vault details page. On the **Associated Servers** tab page, locate the target server. Click **Perform Backup** in the **Operation** column of the server. See :ref:`Figure 3 <cbr_02_0006__fig7287161212118>`.

   .. _cbr_02_0006__fig7287161212118:

   **Figure 3** Perform Backup

   |image4|

#. Click **Yes**. CBR automatically creates a backup for the server.

   On the **Backups** tab page, if the status of the backup is **Available**, the backup task is successful.

   .. note::

      You can restart a server if necessary after the backup progress exceeds 10%. However, to ensure data integrity, you are advised to restart it after the backup is complete.

   After the backup is complete, you can use the backup to restore server data or create an image. For details, see :ref:`Restoring Data Using a Cloud Server Backup <cbr_03_0032>` and :ref:`Using a Backup to Create an Image <cbr_03_0016>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0251464113.png
.. |image3| image:: /_static/images/en-us_image_0184043658.png
.. |image4| image:: /_static/images/en-us_image_0251458830.png
