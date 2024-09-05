:original_name: cbr_03_0018.html

.. _cbr_03_0018:

Replicating a Backup Across Regions
===================================

CBR enables you to replicate backups of server backup vaults from one region to another.

Replicas of server backups can be used to create images and provision servers.

With cross-region replication, you can quickly deploy services in a different region. Data on the new resource in the destination region is the same as that on the original resource when you took the backup.

You can replicate backups in either of the following methods on the CBR console:

-  Select a backup from the backup list and manually perform a replication.
-  Select a backup vault and manually replicate it. Alternatively, you can configure a replication policy to periodically replicate backups that have not been replicated or failed to be replicated to the destination region.

This section uses the first method to describe how to replicate a backup. For details about the second method, see :ref:`Replicating a Vault <cbr_03_0009>`.

.. note::

   The replication constraints apply to both replication methods.

Constraints
-----------

-  A server backup can be replicated only when it meets all the following conditions:

   #. It is an ECS backup.
   #. It contains system disk data.
   #. It is in the **Available** state.

-  Only backups or backup vaults can be replicated. Replicated backups and vaults cannot be replicated again but their replicas can be used to create images.
-  A backup can be replicated to multiple regions but can have only one replica in each destination region. The replication rule varies with the replication method:

   -  Manual replication: A backup can be manually replicated to the destination region as long as it has no replica in that region. A backup can be manually replicated again if its replica in the destination region has been deleted.
   -  Policy-based replication: A backup can only be automatically replicated to a destination region once. It cannot be automatically replicated to that region again, even if its replica has been deleted.

-  Only replication-supported regions can be selected as destination regions.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click the **Backups** tab and locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Choose **More** > **Create Replica** in the **Operation** column of the backup. See :ref:`Figure 1 <cbr_03_0018__fig274723941115>`.

   .. _cbr_03_0018__fig274723941115:

   **Figure 1** Creating a replica

   |image3|

#. In the displayed dialog box, configure the parameters as described in :ref:`Table 1 <cbr_03_0018__table4829135361311>`.

   .. _cbr_03_0018__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                    |
      +===================================+================================================================================================================================================================+
      | Name                              | Replica name                                                                                                                                                   |
      |                                   |                                                                                                                                                                |
      |                                   | A name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-).                                                             |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Replica description                                                                                                                                            |
      |                                   |                                                                                                                                                                |
      |                                   | It cannot exceed 255 characters.                                                                                                                               |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Region                | Region to which the backup is replicated                                                                                                                       |
      |                                   |                                                                                                                                                                |
      |                                   | Only the regions that support replication will be displayed.                                                                                                   |
      |                                   |                                                                                                                                                                |
      |                                   | -  If the selected region contains only one project, you can directly select the region name.                                                                  |
      |                                   | -  If the selected region has multiple projects, the default project of the region is selected. You can select another project if needed.                      |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Vault                 | A replication vault in the destination region                                                                                                                  |
      |                                   |                                                                                                                                                                |
      |                                   | You can replicate backups to vaults in multiple destination regions. Creating replica will replicate all backups in the source vault to the destination vault. |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. note::

      The traffic for cross-region replication is the size of the replicated backup.

#. Click **OK**.

#. After the replication is complete, you can switch to the destination region to view generated replicas. For details, see :ref:`Viewing a Backup <cbr_03_0013>`. You can then use replicas to create images.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001706852702.png
