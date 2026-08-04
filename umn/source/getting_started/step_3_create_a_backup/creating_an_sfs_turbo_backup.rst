:original_name: cbr_02_0012.html

.. _cbr_02_0012:

Creating an SFS Turbo Backup
============================

This section describes how to quickly create an SFS Turbo file system backup.

To ensure data integrity, you are advised to back up the file system during off-peak hours when no data is written to the file system.

The backup service experiences peak usage from 22:00 to 08:00, during which delays may occur. To ensure optimal performance, it is recommended that you evaluate your service types and stagger backups across discrete time periods.

Prerequisites
-------------

A file system can be backed up only when its status is **Available** or **In-use**. If you have performed operations such as expanding, mounting, unmounting, or deleting a file system, refresh the page first to ensure that the operation is complete and then determine whether to back up the file system.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. In the upper left corner, click |image1| and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery** > **SFS Turbo Backups**.

#. On the **SFS Turbo Backups** page, click the **Vaults** tab and find the vault with which the file system is associated.

#. Perform backup in either of the following ways:

   -  Click **Perform Backup** in the **Operation** column. In the file system list, select the file system you want to back up. After a file system is selected, it is added to the list of selected file systems.


      **Figure 1** Selecting the file system to be backed up

      |image3|

   -  Click the vault name to go to the vault details page. On the **Associated File Systems** tab, locate the target file system and click **Perform Backup** in the **Operation** column.


      **Figure 2** Perform Backup

      |image4|

#. Set **Name** and **Description** for the backup.

   .. table:: **Table 1** Parameter description

      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                      | Remarks               |
      +=======================+==================================================================================================================================================================+=======================+
      | Name                  | Name of the backup you are creating.                                                                                                                             | manualbk_d819         |
      |                       |                                                                                                                                                                  |                       |
      |                       | The name can contain 1 to 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                     |                       |
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

#. Click **OK**. CBR automatically creates a backup for the file system.

   On the **Backups** tab, if the status of the backup is **Available**, the backup task is successful.

   .. note::

      -  If you delete data from the file system during the backup, the deleted data may not be backed up. To ensure data integrity, delete the target data after the backup is complete, and then perform the backup.

   After the backup is complete, you can create a new SFS Turbo file system using the backup. For details, see :ref:`Creating a File System from an SFS Turbo Backup <cbr_03_0107>`.

.. |image1| image:: /_static/images/en-us_image_0219685945.png
.. |image2| image:: /_static/images/en-us_image_0000001599563993.jpg
.. |image3| image:: /_static/images/en-us_image_0000002028900293.png
.. |image4| image:: /_static/images/en-us_image_0000001584073409.png
