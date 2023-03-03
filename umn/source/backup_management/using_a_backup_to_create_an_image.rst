:original_name: cbr_03_0016.html

.. _cbr_03_0016:

Using a Backup to Create an Image
=================================

CBR allows you to create images using ECS backups. You can use the images to provision ECSs to rapidly restore service running environments.

Prerequisites
-------------

-  Confirm that the following operations have been performed before you use an ECS backup to create an image:

   -  You have optimized the Linux ECS (referring to `Optimizing a Linux Private Image <https://docs.otc.t-systems.com/usermanual/ims/en-us_topic_0047501133.html>`__) and installed Cloud-Init (referring to `Installing Cloud-Init <https://docs.otc.t-systems.com/usermanual/ims/en-us_topic_0030730603.html>`__).
   -  You have optimized the Windows ECS (referring to `Optimizing a Windows Private Image <https://docs.otc.t-systems.com/usermanual/ims/en-us_topic_0047501112.html>`__) and installed Cloudbase-Init (referring to `Installing and Configuring Cloudbase-Init <https://docs.otc.t-systems.com/usermanual/ims/en-us_topic_0030730602.html>`__).

-  A backup can be used to create an image in either of the following scenarios: 1. The backup is in the **Available** state. 2. The backup is in the **Creating** state which is marked with **Image can be created**.

   .. note::

      Once a backup creation starts, the backup enters the **Creating** state. After a period of time, a message stating "Image can be created" is displayed under **Creating**. In this case, the backup can be used for creating an image, even though it is still being created and cannot be used for restoration.

-  The backup you want to use to create an image contains the system disk data.

Function Description
--------------------

-  Images created using a backup are the same, so CBR allows you to use a backup to create only one full-ECS image that contains the whole data of the system disk and data disks of an ECS, in order to save the image quota. After an image is created, you can use the image to provision multiple ECSs in a batch.
-  A backup with an image created cannot be directly deleted. If you want to delete such a backup, delete its image first. If a backup is automatically generated based on a backup policy and the backup has been used to create an image, the backup will not be counted as a retained backup and will not be deleted automatically.
-  A backup is compressed when it is used to create an image. Therefore, the size of the generated image is smaller than that of the backup.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose a backup tab from the left navigation pane.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. In the row of the backup, choose **More** > **Create Image**. See :ref:`Figure 1 <cbr_03_0016__fig31751974142>`.

   .. _cbr_03_0016__fig31751974142:

   .. figure:: /_static/images/en-us_image_0251479636.png
      :alt: **Figure 1** Creating an image

      **Figure 1** Creating an image

#. Create an image by referring to section "Creating a Full-ECS Image from a CBR Backup" in the *Image Management Service User Guide*.

#. If you want to use an image to provision ECSs, see section "Creating an ECS from an Image" in the *Image Management Service User Guide*.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
