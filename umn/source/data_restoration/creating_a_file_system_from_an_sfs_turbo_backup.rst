:original_name: cbr_03_0107.html

.. _cbr_03_0107:

Creating a File System from an SFS Turbo Backup
===============================================

In case of a virus attack, accidental deletion, or software or hardware fault, you can use an SFS Turbo file system backup to create a new file system. Once created, data on the new file system is the same as that in the backup.

Constraints
-----------

You can change the storage class of a file system within a certain range. For example, you can change a file system from Standard to Performance, but not from Standard to Standard - Enhanced. From SFS Turbo HPC backups, you can only create HPC file systems with different performance, such as 20 MB/s/TiB, 40 MB/s/TiB, 125 MB/s/TiB, 250 MB/s/TiB, 500 MB/s/TiB, and 1,000 MB/s/TiB.


Constraints
-----------

In CloudPond scenarios, SFS Turbo backups cannot be used to create new SFS Turbo file systems.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab and locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Click **Create New File System** in the **Operation** column of the backup. The button is available only when the backup status is **Available**. The **Create File System** page is displayed.

#. Configure the file system parameters.


   .. figure:: /_static/images/en-us_image_0000001222800105.png
      :alt: **Figure 1** Creating a file system

      **Figure 1** Creating a file system

   You can learn about the parameter descriptions in table "Parameter description" under "Creating an SFS Turbo File System" in "Create a File System" of the *Scalable File Service Turbo User Guide*.

#. Click **Create Now**.

#. Go back to the file system list and check whether the file system is successfully created.

   You will see the file system status change as follows: **Creating**, **Available**, **Restoring**, **Available**. You may not notice the **Restoring** status because Instant Restore is very fast. After the file system status changes from **Creating** to **Available**, the file system is successfully created. After the status has changed from **Restoring** to **Available**, backup data has been successfully restored to the created file system.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
