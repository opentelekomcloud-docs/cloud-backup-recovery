:original_name: cbr_02_0009.html

.. _cbr_02_0009:

Step 2: Associate a Resource with the Vault
===========================================

If you have already associated servers, file systems, or disks when creating a vault, skip this step.

After a server backup vault or disk backup vault is created, you can associate servers, file systems, or disks with the vault to back up these resources.

Prerequisites
-------------

-  The servers you plan to associate with a vault must be in the **Running** or **Stopped** state.
-  The disks you plan to associate with a vault must be in the **Available** or **In-use** state.
-  The SFS Turbo file systems you plan to associate with a vault must be in the **Available** state.
-  The servers you plan to associate with a vault must have at least one disk attached.
-  The vault and the resources you plan to associate with it must be in the same region.
-  The total size of the resources to be associated cannot be greater than the vault capacity.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose your desired type of backup from the left navigation pane.

#. On a backup page, locate the target vault and click **Associate Server**, **Associate File System**, or **Associate Disk**.

#. In the resource list, select the resources you want to associate with the vault. After resources are selected, they are added to the list of selected resources. See :ref:`Figure 1 <cbr_02_0009__fig20466879539>`.

   .. _cbr_02_0009__fig20466879539:

   **Figure 1** Associate Server

   |image2|

#. Click **OK**. Then in the **Associated Servers** column in the vault list, you can view the number of resources that have been successfully associated.

   .. note::

      If a new disk is attached to an associated server, CBR automatically identifies the new disk and includes the new disk in subsequent backup tasks.

Automatic Association
---------------------

If you enable automatic association for a backup vault, the vault will automatically associate the unprotected resources and back them up according to the backup policy applied to the vault.

-  You can enable automatic association only when the vault's remaining capacity (Vault's total capacity - Vault's associated capacity) is greater than 40 GB. You can obtain the vault's total capacity and associated capacity in the **Basic Information** area on the details page of the vault. For example, if you have an 800-GB server backup vault and it has been associated with two 100 GB servers, its remaining capacity is 600 GB (800 GB - 200 GB). In this case, you can enable automatic association.
-  If multiple vaults are enabled with automatic association, CBR scans their backup policies and associates resources with the vault whose next scheduled backup time is the earliest.
-  If the capacity of the first selected vault is used up, resources will be associated with the vault whose next scheduled backup time is the second earliest.
-  If a backup policy with the earliest scheduled backup time is applied to more than one vault, CBR randomly associates the resources with one of these vaults.
-  If a vault has automatic association enabled but has no backup policy applied, no resources will be automatically associated with this vault. You can manually associate unprotected resources.
-  After automatic association is disabled for a vault, the vault stops automatically scanning for unprotected resources. Associated resources are not affected.

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image3| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**.

#. On any backup page, locate the target vault.

#. Choose **More** > **Enable Automatic Association** in the **Operation** column of the vault. See :ref:`Figure 2 <cbr_02_0009__fig197911334183117>`.

   You can filter unprotected resources by tag. If a tag is selected, only unprotected resources with the specified tag will be associated with the vault. Or, all unprotected resources will be associated.

   If no tag is available, you can create tags on the corresponding resource page. You can search for vaults by specifying a maximum of 5 tags at a time. If you select more than one tag, the vaults with any of the specified tags will be returned.

   .. _cbr_02_0009__fig197911334183117:

   **Figure 2** Enabling automatic association

   |image4|

#. Check that **Automatic association** is displayed in the **Associated Servers** column of the vault list.

#. (Optional) If automatic association is not required, choose **More** > **Disable Automatic Association** in the **Operation** column of the vault. See :ref:`Figure 3 <cbr_02_0009__fig10546636185>`.

   .. _cbr_02_0009__fig10546636185:

   **Figure 3** Disabling automatic association

   |image5|

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0252972053.png
.. |image3| image:: /_static/images/en-us_image_0160754270.png
.. |image4| image:: /_static/images/en-us_image_0000001116431701.png
.. |image5| image:: /_static/images/en-us_image_0000001116214783.png
