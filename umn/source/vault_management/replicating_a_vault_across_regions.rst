:original_name: cbr_03_0009.html

.. _cbr_03_0009:

Replicating a Vault Across Regions
==================================

Scenarios
---------

Cloud server backup vaults allow you to **replicate all backups in vaults to replication vaults of the same account in another region**. Server backup replicas can be used to create images and provision servers in the destination region. to quickly deploy services across regions.

A vault can be replicated in either of the following ways:

-  Manual replication: Select a backup vault and manually replicate it.
-  Policy-based replication: Configure a replication policy to periodically replicate backups that have not been replicated or failed to be replicated to the destination region.

Constraints
-----------

-  Disk backup vaults cannot be replicated to other regions.
-  Vaults can be replicated to different regions. Replication traffic charges are incurred in the source region. Backup replicas consume storage capacity in replication vaults.
-  A server backup vault can be replicated only if at least one of its backups meets all of the following conditions:

   #. The backup is generated from an ECS.
   #. The backup contains system disk data.
   #. The backup is in the **Available** state.

-  Replication is supported only for backup vaults of the same type created in the source region. Replicated vaults cannot be re-replicated. Backups replicated from other regions can only be used to create images.
-  A backup vault can be replicated to different regions. Replication can be performed manually or through policies, but each target region supports only one replication. Once a backup has been replicated to a region, it cannot be replicated there again, even if the target backup is deleted.
-  Replication is supported only between the following regions:

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. On the **Vaults** tab, find the target backup vault.

#. Choose **More** > **Create Replica** in the **Operation** column of the vault.


   **Figure 1** Creating a replica

   |image3|

#. In the displayed dialog box, configure the parameters as described in :ref:`Table 1 <cbr_03_0009__table4829135361311>`.

   .. _cbr_03_0009__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                            |
      +===================================+========================================================================================================================================================+
      | Destination Region                | Region where the vault will be replicated to.                                                                                                          |
      |                                   |                                                                                                                                                        |
      |                                   | Only the regions that support replication will be displayed.                                                                                           |
      |                                   |                                                                                                                                                        |
      |                                   | -  If the selected region contains only one project, you can directly select the region name.                                                          |
      |                                   | -  If the selected region has multiple projects, the default project of the region is preselected, but you can still select another project if needed. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Vault                 | A replication vault in the destination region.                                                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

#. After the replication is complete, you can switch to the destination region to view generated replicas. For details, see :ref:`Viewing a Vault <cbr_03_0002>`. You can then use replicas to create images.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001754810509.png
