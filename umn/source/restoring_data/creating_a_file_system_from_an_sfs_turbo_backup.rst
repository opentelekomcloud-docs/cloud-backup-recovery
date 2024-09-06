:original_name: cbr_03_0107.html

.. _cbr_03_0107:

Creating a File System from an SFS Turbo Backup
===============================================

In case of a virus attack, accidental deletion, or software or hardware fault, you can use an SFS Turbo file system backup to create a new file system. Once created, data on the new file system is the same as that in the backup.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click the **Backups** tab and locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Click **Create File System** in the **Operation** column of the backup. The button is available only when the backup status is **Available**.

#. Configure the file system parameters. See :ref:`Figure 1 <cbr_03_0107__fig126043518315>`.

   .. _cbr_03_0107__fig126043518315:

   .. figure:: /_static/images/en-us_image_0000001222800105.png
      :alt: **Figure 1** Creating a file system

      **Figure 1** Creating a file system

   .. note::

      -  You can learn about the parameter descriptions in table "Parameter description" under "Creating an SFS Turbo File System" in "Create a File System" of the *Scalable File Service User Guide*.

#. Click **Create Now**.

#. Go back to the file system list and check whether the file system is successfully created.

   You will see the file system status change as follows: **Creating**, **Available**, **Restoring**, **Available**. You may not notice the **Restoring** status because Instant Restore is supported and the restoration speed is very fast. After the file system status has changed from **Creating** to **Available**, the file system is successfully created. After the status has changed from **Restoring** to **Available**, backup data has been successfully restored to the created file system.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
