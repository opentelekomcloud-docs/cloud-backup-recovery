:original_name: cbr_03_0107.html

.. _cbr_03_0107:

Using a Backup to Create a File System
======================================

In case of a virus attack, accidental deletion, or software or hardware fault, you can use an SFS Turbo file system backup to create a new file system. After it is created, data on the new file system is the same as that in the backup.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose a backup tab from the left navigation pane.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. If the status of the target backup is **Available**, click **Create File System** in the **Operation** column of the backup.

#. Set the file system parameters. See :ref:`Figure 1 <cbr_03_0107__fig126043518315>`.

   .. _cbr_03_0107__fig126043518315:

   .. figure:: /_static/images/en-us_image_0000001222800105.png
      :alt: **Figure 1** Creating a file system

      **Figure 1** Creating a file system

   .. note::

      -  For detailed parameter descriptions, see table "Parameter description" under "Creating an SFS Turbo File System" in the *Scalable File Service User Guide*.

#. Click **Next**.

#. Go back to the file system list and check whether the file system is successfully created.

   You will see the file system status change as follows: **Creating**, **Available**, **Restoring**, **Available**. You may not notice the **Restoring** status because Instant Restore is supported and the restoration speed is very fast. After the file system status has changed from **Creating** to **Available**, the file system is successfully created. After the status has changed from **Restoring** to **Available**, backup data has been successfully restored to the created file system.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
