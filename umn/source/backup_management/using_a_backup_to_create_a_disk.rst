:original_name: cbr_03_0017.html

.. _cbr_03_0017:

Using a Backup to Create a Disk
===============================

You can create new disks from backups. Once created, the new disks will contain the backup data.

The new disks created using system disk backups can only be used as data disks on servers. They cannot be used as system disks.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose your desired type of backup from the left navigation pane.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. If the status of the target backup is **Available**, click **Create Disk** in the **Operation** column of the backup.

#. Configure the disk parameters.

   .. note::

      See the parameter description table in section "Create an EVS Disk" of the *Elastic Volume Service User Guide* for more information.

      Pay attention to the following:

      -  You can choose the AZ to which the backup source disk belongs, or a different AZ.

      -  The new disk must be at least as large as the backup's source disk.

         If the capacity of the new disk is greater than that of the backup's source disk, format the additional space by following the steps provided in section "Extending Disk Partitions and File Systems" of the *Elastic Volume Service User Guide*.

      -  You can create a disk of any type regardless of the backup's disk type.

#. Click **Next**.

#. Go back to the disk list. Check whether the disk is successfully created.

   You will see the disk status change as follows: **Creating**, **Available**, **Restoring**, **Available**. You may not notice the **Restoring** status because Instant Restore is supported and the restoration speed is very fast. After the disk status has changed from **Creating** to **Available**, the disk is successfully created. After the status has changed from **Restoring** to **Available**, backup data has been successfully restored to the created disk.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
