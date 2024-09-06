:original_name: cbr_03_0009.html

.. _cbr_03_0009:

Replicating a Vault Across Regions
==================================

Scenarios
---------

CBR allows you to **replicate server backup vaults entirely to replication vaults in other regions of the same account**. Replicas of server backups in the destination region can be used to create images and provision servers. to quickly deploy services across regions.

There are two methods available for replicating a vault.

-  Manual replication: Select a backup vault and manually replicate it.
-  Policy-based replication: Configure a replication policy to periodically replicate backups that have not been replicated or failed to be replicated to the destination region.

Constraints
-----------

-  Disk backup vaults cannot be replicated to other regions.
-  Backup data can be replicated to vaults in different regions, and backup replicas occupy the replication vault space.
-  A server backup vault can be replicated only when it contains at least one backup that meets all the following conditions:

   #. The backup is an ECS backup.
   #. The backup contains system disk data.
   #. The backup is in the **Available** state.

-  Only backup vaults of the same type can be replicated. Replicated vaults cannot be replicated again but their replicas can be used to create images.
-  A backup vault can be replicated to different destination regions. For manual and policy-based vault replication, a vault can only be replicated to a destination region once. It cannot be replicated to that region again, even if its backups have been deleted.
-  Only replication-supported regions can be selected as destination regions.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. On the **Vaults** tab, find the target backup vault.

#. Choose **More** > **Create Replica** in the **Operation** column of the vault. See :ref:`Figure 1 <cbr_03_0009__fig6867058144918>`.

   .. _cbr_03_0009__fig6867058144918:

   **Figure 1** Creating a replica

   |image3|

#. In the displayed dialog box, configure the parameters as described in :ref:`Table 1 <cbr_03_0009__table4829135361311>`.

   .. _cbr_03_0009__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                               |
      +===================================+===========================================================================================================================================+
      | Destination Region                | Region to which the vault is replicated                                                                                                   |
      |                                   |                                                                                                                                           |
      |                                   | Only the regions that support replication will be displayed.                                                                              |
      |                                   |                                                                                                                                           |
      |                                   | -  If the selected region contains only one project, you can directly select the region name.                                             |
      |                                   | -  If the selected region has multiple projects, the default project of the region is selected. You can select another project if needed. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Vault                 | A replication vault in the destination region                                                                                             |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

#. After the replication is complete, you can switch to the destination region to view generated replicas. For details, see :ref:`Querying a Vault <cbr_03_0002>`. You can then use replicas to create images.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001754810509.png
