:original_name: cbr_03_0104.html

.. _cbr_03_0104:

(Optional) Migrating Resources from CSBS/VBS
============================================

Context
-------

The cloud platform has launched the next-generation backup service, CBR. If you have backups in CSBS or VBS but want to switch to CBR to manage these historical backups, you can migrate them to CBR in a few clicks.

If you have never used CSBS or VBS, or do not need the historical backups anymore, skip this section.

Migration Rules
---------------

During migration, CBR will automatically create vaults based on the types of your historical resources.

.. table:: **Table 1** Migration rules

   +----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Before Migration                                                     | After Migration                                                                                                                                                                                                                 |
   +======================================================================+=================================================================================================================================================================================================================================+
   | Servers or disks are associated with a backup policy.                | If backups have been generated, CBR will create a vault with the same name (up to 64 characters) as the policy name (regardless of whether the policy is enabled) and apply the policy to the vault after the vault is created. |
   |                                                                      |                                                                                                                                                                                                                                 |
   |                                                                      | If no backup is generated, CBR will create a vault only when the policy is enabled. The policy applying rule and vault naming rule are the same as above.                                                                       |
   +----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Servers or disks are associated with a backup or replication policy. | If no backup is generated and the policy is disabled, only the policy will be migrated.                                                                                                                                         |
   +----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Backup or replication policies are not associated with any resource. | The policies will be migrated.                                                                                                                                                                                                  |
   +----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Backup replicas are generated.                                       | CBR will create a replication vault named **default** to store generated backup replicas.                                                                                                                                       |
   +----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | An image is created using a backup and a tag is added to the image.  | The backup will fail to be migrated. Go to the IMS console, delete the tag and then migrate the backup again. After the backup is migrated, add the tag if needed.                                                              |
   +----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Other backups, including manual backups, will be stored in a server backup vault named **default**. Different vaults will be created based on different types of resources. For example, CBR will create a disk backup vault to store the migrated disk backups.

After the migration, backups created using CBR will also be displayed on the VBS console, but you will be billed only once.

.. note::

   To delete backups from the VBS console, find these backups in CBR and delete them. Then, the backups will also be deleted from the VBS console.

Base on the preceding rules, the capacity of each vault created by the system is predefined as 1.2 times of the total backup size.

For example, a user has a 100 GB ECS and a 50 GB ECS. The used storage capacity of the two ECSs is 20 GB and 10 GB, respectively. The user manually has backed up the two entire ECSs using cloud server backup. During migration, the capacity of the vault automatically created will be 1.2 times of the total backup size. In this example, the total backup size multiplied by 1.2 is 36 GB. So the system will automatically create a 36 GB vault.

Constraints
-----------

-  The vaults you have cannot be used for migration. Resources will automatically migrated to system-created vaults.
-  Backup resources of one account only need to be migrated once.
-  After resources are migrated, disk backups and server backups will be automatically stored in CBR vaults. No further operations are required.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click **Migrate to CBR** in the upper right corner. Read the content in the displayed dialog box and click **OK**. See :ref:`Figure 1 <cbr_03_0104__fig1730015415381>`.

   .. _cbr_03_0104__fig1730015415381:

   **Figure 1** Migrating resources to CBR

   |image3|

#. The system will automatically migrate resources. After the migration, a vault named **default** will be created and a message will be displayed in the upper part of the page indicating that the migration is successful.

FAQ
---

#. Why Are CBR Backups Displayed on VBS Console?

   If you have migrated data from CSBS and VBS to CBR, and created a backup on CBR Console, the same backup record will be generated on VBS Console. This is due to an underlying mechanism. VBS Console displays all backups generated by CBR, CSBS, and VBS.

#. How Do I Delete Backups from VBS Console?

   After you have migrated data from CSBS and VBS to CBR, backups displayed in the VBS console cannot be deleted alone. Find these backups in CBR and delete them. Then, the backups will also be deleted from the VBS console.

#. What Are the Differences Between CBR, CSBS, and VBS?

   CBR integrates CSBS and VBS. In addition, CBR supports SFS Turbo backup.

#. What Can I Do If a Message Is Displayed Indicating that a Resource Has Been Bound with CSBS or VBS?

   Choose **Cloud Server Backup Service** or **Volume Backup Service** from the service list. On the corresponding service console, check whether there are resources bound with policies on the **Policies** tab. If so, unbind the resources from the policy and go to CBR Console to associate the resources with a vault.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001293014297.png
