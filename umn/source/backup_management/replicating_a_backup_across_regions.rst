:original_name: cbr_03_0018.html

.. _cbr_03_0018:

Replicating a Backup Across Regions
===================================

Scenarios
---------

Cross-region replication of server backup vaults allows you to **replicate backups from one region to another in the same account**.

Replicas of server backups can be used to create images and provision servers in another region.

With cross-region replication, you can quickly deploy services in a different region. The resources created from replicated backups retain the same state as the original resources at the time the backup was taken.

You can replicate backups in either of the following methods on the CBR console:

-  Select a backup from the backup list and manually replicate it.
-  Select a backup vault and manually replicate it. Alternatively, you can configure a replication policy to periodically replicate backups that have not been replicated or failed to be replicated to the destination region.

This section uses the first method to describe how to replicate a backup. For details about the second method, see :ref:`Replicating a Vault Across Regions <cbr_03_0009>`.

Constraints
-----------

-  A server backup can be replicated only when it meets all the following conditions:

   #. It is an ECS backup.
   #. It contains system disk data.
   #. It is in the **Available** state.

-  Replication is supported only for backups or vaults created in the source region. Replicated backups and vaults cannot be re-replicated. Backups replicated from other regions can only be used to create images.

-  A backup can be replicated to multiple regions, but only one replica is allowed in each destination region. The number of times you can replicate to a destination region varies depending on the replication method.

   Manual replication of a single backup: A backup can be manually replicated again if its replica in the destination region has been deleted.

   Manual vault replication or policy‑based backup replication: The replication can be performed only once. It cannot be performed again, even if the backups in the destination region have been deleted.

-  Only replication-supported regions can be selected as destination regions.

-  Received shared backups do not support cross-region replication.

Create a Cross-region Backup Replication Task
---------------------------------------------

#. Click |image1| in the upper left corner of the management console and select the region where the backups to be replicated are located.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Choose **More** > **Create Replica** in the **Operation** column of the backup.


   **Figure 1** Creating a replica

   |image2|

#. In the displayed dialog box, configure the parameters as described in :ref:`Table 1 <cbr_03_0018__table4829135361311>`.

   .. _cbr_03_0018__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                |
      +===================================+============================================================================================================================================================+
      | Name                              | Replica name. You can enter a custom name or use the default name **resource name_xxxx**.                                                                  |
      |                                   |                                                                                                                                                            |
      |                                   | The name can contain 1 to 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                               |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Replica description. This parameter is optional.                                                                                                           |
      |                                   |                                                                                                                                                            |
      |                                   | It cannot exceed 255 characters.                                                                                                                           |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Region                | Region where the backup will be replicated to.                                                                                                             |
      |                                   |                                                                                                                                                            |
      |                                   | Only the regions that support replication will be displayed.                                                                                               |
      |                                   |                                                                                                                                                            |
      |                                   | -  If the selected region contains only one project, you can directly select the region name.                                                              |
      |                                   | -  If the selected region has multiple projects, the default project of the region is preselected, but you can still select another project if needed.     |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Vault                 | A replication vault in the destination region.                                                                                                             |
      |                                   |                                                                                                                                                            |
      |                                   | You can replicate backups to vaults in multiple regions. Once replication is successful, the replicated backups will occupy the required storage capacity. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. note::

      The traffic for cross-region replication is determined by the size of the replicated backup.

#. Click **OK**.

#. After the replication is complete, you can switch to the destination region to view generated replicas. For details, see :ref:`Viewing a Backup <cbr_03_0013>`. You can then use the replicas to create images.

.. |image1| image:: /_static/images/en-us_image_0000002449862949.png
.. |image2| image:: /_static/images/en-us_image_0000001706852702.png
