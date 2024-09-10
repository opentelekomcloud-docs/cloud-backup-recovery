:original_name: cbr_02_0007.html

.. _cbr_02_0007:

Creating a Cloud Disk Backup
============================

This section describes how to quickly create a cloud disk backup.

Backing up a server does not impact the disk performance.

Peak hours of the backup service are from 22:00 to 08:00, during which there may be delays. So you are advised to evaluate your service types and schedule backups in discrete time periods.

Prerequisites
-------------

A disk can be backed up only when its status is **Available** or **In-use**. If you have performed operations such as expanding, attaching, detaching, or deleting a disk, refresh the page first to ensure that the operation is complete and then determine whether to back up the disk.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. On the **Cloud Disk Backups** page, click the **Vaults** tab and find the vault to which the disk is associated.

#. Perform backup in either of the following ways:

   -  Click **Perform Backup** in the **Operation** column. In the disk list, select the disk you want to back up. After a disk is selected, it is added to the list of selected disks. See :ref:`Figure 1 <cbr_02_0007__fig2557455115213>`.

      .. _cbr_02_0007__fig2557455115213:

      **Figure 1** Selecting the disk to be backed up

      |image3|

   -  Click the vault name to go to the vault details page. On the **Associated Disks** tab page, locate the target disk and click **Perform Backup** in the **Operation** column. See :ref:`Figure 2 <cbr_02_0007__fig19972192464112>`.

      .. _cbr_02_0007__fig19972192464112:

      **Figure 2** Perform Backup

      |image4|

   .. note::

      CBR will identify whether the selected disk is encrypted. If it is encrypted, the backups will be automatically encrypted.

#. Set **Name** and **Description** for the backup. :ref:`Table 1 <cbr_02_0007__table4829135361311>` describes the parameters.

   .. _cbr_02_0007__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                               | Remarks               |
      +=======================+===========================================================================================================================================================+=======================+
      | Name                  | Name of the backup you are creating.                                                                                                                      | manualbk_d819         |
      |                       |                                                                                                                                                           |                       |
      |                       | A name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-).                                                        |                       |
      |                       |                                                                                                                                                           |                       |
      |                       | .. note::                                                                                                                                                 |                       |
      |                       |                                                                                                                                                           |                       |
      |                       |    You can also use the default name **manualbk\_**\ *xxxx*.                                                                                              |                       |
      |                       |                                                                                                                                                           |                       |
      |                       |    If multiple disks are to be backed up, the system automatically adds suffixes to their backup names, for example, **backup-0001** and **backup-0002**. |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Description of the backup.                                                                                                                                | --                    |
      |                       |                                                                                                                                                           |                       |
      |                       | It cannot exceed 255 characters.                                                                                                                          |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Choose whether to enable full backup. If full backup is enabled, CBR performs a full backup on every associated disk, which requires a larger capacity compared to an incremental backup. See :ref:`Figure 3 <cbr_02_0007__fig789511544815>`.

   .. _cbr_02_0007__fig789511544815:

   **Figure 3** Full Backup

   |image5|

#. Click **OK**. CBR automatically creates a backup for the disk.

   On the **Backups** tab page, if the status of the backup is **Available**, the backup task is successful.

   .. note::

      -  If you delete data from the disk during the backup, the deleted data may fail to be backed up. Therefore, to ensure data integrity, delete the target data after the backup is complete, and then perform the backup.

   After the backup is complete, you can use the backup to restore disk data. For details, see :ref:`Restoring from a Cloud Disk Backup <cbr_03_0033>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002028782365.png
.. |image4| image:: /_static/images/en-us_image_0000001533473474.png
.. |image5| image:: /_static/images/en-us_image_0184062862.png
