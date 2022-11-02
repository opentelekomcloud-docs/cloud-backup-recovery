:original_name: cbr_05_0003.html

.. _cbr_05_0003:

A Server Created Using an Image Enters Maintenance Mode After Login
===================================================================

Symptom
-------

A server is created using the image of a cloud server backup. However, upon login to the server, the server enters maintenance mode and cannot be used.

Possible Cause
--------------

After the server creation, the configuration parameters contained in the **/etc/fstab** file in the system disk of the new server are that of the backup source server, causing the UUID information to be inconsistent with the new data disks. As a result, the ECS encounters an error when uploading **/etc/fstab** during the bootup and enters maintenance mode.

Solution
--------

The following uses CentOS as an example.

#. After creating an ECS using an image, log in to the ECS console, click **Remote Login** in the row of the ECS.

#. On the maintenance mode page that is displayed, access the system as prompted.


   .. figure:: /_static/images/en-us_image_0160524684.jpg
      :alt: **Figure 1** Maintenance mode of the system


      **Figure 1** Maintenance mode of the system

#. Run the **cat /etc/fstab** command to check the disk attachment information.


   .. figure:: /_static/images/en-us_image_0160524685.jpg
      :alt: **Figure 2** Data disk UUIDs


      **Figure 2** Data disk UUIDs

#. Run the **vi /etc/fstab** command to open the file, press **i** to enter the editing mode, and delete the attachment information of all data disks. Then, press **Esc** to exit the editing mode and run **:wq!** to save the change and exit.


   .. figure:: /_static/images/en-us_image_0160524686.jpg
      :alt: **Figure 3** **/etc/fstab** after being updated


      **Figure 3** **/etc/fstab** after being updated

#. Run the **reboot** command to restart the system.


   .. figure:: /_static/images/en-us_image_0160524687.jpg
      :alt: **Figure 4** Normal bootup page


      **Figure 4** Normal bootup page

#. After entering the system, attach the data disks manually.


   .. figure:: /_static/images/en-us_image_0160524688.jpg
      :alt: **Figure 5** Attaching the data disks manually


      **Figure 5** Attaching the data disks manually

#. Run the **blkid** command to obtain the UUID information of the data disks.


   .. figure:: /_static/images/en-us_image_0160524689.jpg
      :alt: **Figure 6** Obtaining UUIDs of data disks


      **Figure 6** Obtaining UUIDs of data disks

#. Run the **vi /etc/fstab** command to open the file, press **i** to enter the editing mode, and add the attachment information of all data disks. Then, press **Esc** to exit the editing mode and run **:wq!** to save the change and exit.


   .. figure:: /_static/images/en-us_image_0160524690.jpg
      :alt: **Figure 7** Adding attachment information of data disks


      **Figure 7** Adding attachment information of data disks

   After the information is added, the system will automatically attach the data disks on restart.
