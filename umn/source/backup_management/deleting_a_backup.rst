:original_name: cbr_03_0015.html

.. _cbr_03_0015:

Deleting a Backup
=================

You can delete unwanted backups to reduce space usage and costs.

Context
-------

CBR supports manual deletion of backups and automatic deletion of expired backups. The latter is executed based on the backup retention rule in the backup policy. For details, see :ref:`Creating a Backup Policy <cbr_03_0025>`.

Prerequisites
-------------

-  There is at least one backup.
-  The backup to be deleted is in the **Available** or **Error** state.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose your desired type of backup from the left navigation pane.

#. Click the **Backups** tab and locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. In the row of the backup, choose **More** > **Delete** from the **Operation** column. See :ref:`Figure 1 <cbr_03_0015__fig1233612574363>`. Alternatively, select the backups you want to delete in a batch and click **Delete** in the upper left corner to delete them.

   .. _cbr_03_0015__fig1233612574363:

   **Figure 1** Deleting a backup

   |image2|

#. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0251478661.png
