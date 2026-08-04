:original_name: cbr_05_0003.html

.. _cbr_05_0003:

A Server Created from an Image Enters Maintenance Mode After Login
==================================================================

Symptom
-------

A server is created using the image of a cloud server backup. However, upon login to the server, the server enters the maintenance mode and cannot be used.

Possible Cause
--------------

After the server is created, the **/etc/fstab** file on the system disk of the new server retains configuration parameters from the source server. As a result, the UUIDs referenced in the file do not match the new data disks, causing the ECS instance to encounter an error when loading **/etc/fstab** and enter maintenance mode.

Solution
--------

The following uses CentOS as an example.

#. After creating an ECS using an image, log in to the ECS console, click **Remote Login** in the row of the ECS.

#. On the maintenance mode page that is displayed, access the system as prompted.


   .. figure:: /_static/images/en-us_image_0000002043775410.png
      :alt: **Figure 1** Maintenance mode of the system

      **Figure 1** Maintenance mode of the system

#. Run the **cat /etc/fstab** command to check the disk attachment information.


   .. figure:: /_static/images/en-us_image_0000001513434281.png
      :alt: **Figure 2** Data disk UUIDs

      **Figure 2** Data disk UUIDs

#. Run the **vi /etc/fstab** command to open the file, press **i** to enter the editing mode, and delete the attachment information of all data disks. Then, press **Esc** to exit the editing mode and run **:wq!** to save the changes and exit.


   .. figure:: /_static/images/en-us_image_0000001462955128.png
      :alt: **Figure 3** **/etc/fstab** after being updated

      **Figure 3** **/etc/fstab** after being updated

#. Run the **reboot** command to restart the system.


   .. figure:: /_static/images/en-us_image_0000001513556381.png
      :alt: **Figure 4** Normal bootup page

      **Figure 4** Normal bootup page

#. After entering the system, attach the data disks manually.


   .. figure:: /_static/images/en-us_image_0000001513555957.png
      :alt: **Figure 5** Attaching the data disks manually

      **Figure 5** Attaching the data disks manually

#. Run the **blkid** command to obtain the UUID information of the data disks.


   .. figure:: /_static/images/en-us_image_0000001513691041.png
      :alt: **Figure 6** Obtaining UUIDs of data disks

      **Figure 6** Obtaining UUIDs of data disks

#. Run the **vi /etc/fstab** command to open the file, press **i** to enter the editing mode, and add the attachment information of all data disks. Then, press **Esc** to exit the editing mode and run **:wq!** to save the changes and exit.


   .. figure:: /_static/images/en-us_image_0000001513435141.png
      :alt: **Figure 7** Adding attachment information of data disks

      **Figure 7** Adding attachment information of data disks

   After the information is added, the system will automatically attach the data disks on restart.
