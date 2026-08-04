:original_name: cbr_02_0010.html

.. _cbr_02_0010:

Creating an SFS Turbo Backup Vault
==================================

This section describes how to create an SFS Turbo backup vault.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. In the upper left corner, click |image1| and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery** > **SFS Turbo Backups**.

#. In the upper right corner of the page, click **Create SFS Turbo Backup Vault**.

#. Select a protection type.

   -  **Backup**: An SFS Turbo backup vault stores SFS Turbo backups.

#. Determine whether to enable backup locking.

   If backup locking is enabled, backups in the vault will not be deleted maliciously or by mistake. This improves data reliability.

   |image3|

   .. important::

      Backup locking cannot be disabled after it is enabled.

#. (Optional) In the file system list, select the file systems to be backed up. After file systems are selected, they are added to the list of selected file systems.


   **Figure 1** Selecting file systems

   |image4|

   .. note::

      -  The selected file systems must not have been associated with any vault and must be in the **Available** state.
      -  If you skip this step, you can also associate file systems with the vault later.

#. Specify the vault capacity. This capacity is the total size of the file systems that you want to associate with this vault. Plan the vault capacity and ensure that it is at least as large as the file systems you want to back up. If a backup policy is applied to the vault, plan more capacity as required. The capacity ranges from 10 GB to 10,485,760 GB. If automatic capacity expansion is not enabled, the vault capacity will not be automatically expanded, even if the capacity of file systems is expanded during use.

   You can expand the vault capacity if it becomes insufficient. See :ref:`Figure 2 <cbr_02_0004__fig179361847142520>`.


   .. figure:: /_static/images/en-us_image_0000002302754542.png
      :alt: **Figure 2** Setting the vault capacity

      **Figure 2** Setting the vault capacity

#. Configure auto backup.

   -  If you select **Configure**, you must then select an existing backup policy or create a policy. After the vault is created, CBR will apply the policy to this vault, and all file systems associated with this vault will be automatically backed up based on this policy.
   -  If you select **Skip**, file systems associated with this vault will not be automatically backed up until you apply a backup policy to the vault.

#. (Optional) Add tags to the vault.

   Tags are key-value pairs, which are used to identify, classify, and search for vaults. You can add a maximum of 20 tags for a vault, and vault tags are only used to filter and manage vaults. See :ref:`Figure 3 <cbr_02_0010__cbr_02_0003_fig138791734631>`.

   .. _cbr_02_0010__cbr_02_0003_fig138791734631:

   **Figure 3** Adding a tag

   |image5|

   :ref:`Table 1 <cbr_02_0010__cbr_02_0003_table191162312815>` describes the parameters of a tag.

   .. _cbr_02_0010__cbr_02_0003_table191162312815:

   .. table:: **Table 1** Tag parameters

      +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                           | Example Value         |
      +=======================+=======================================================================================================+=======================+
      | Key                   | Each tag has a unique key. You can specify a key or select the key of an existing tag created in TMS. | Key_0001              |
      |                       |                                                                                                       |                       |
      |                       | A tag key:                                                                                            |                       |
      |                       |                                                                                                       |                       |
      |                       | -  Can contain 1 to 36 Unicode characters.                                                            |                       |
      |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_).                                |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+
      | Value                 | A tag value can be duplicated and can also be left empty.                                             | Value_0001            |
      |                       |                                                                                                       |                       |
      |                       | A tag value:                                                                                          |                       |
      |                       |                                                                                                       |                       |
      |                       | -  Can contain 0 to 43 Unicode characters.                                                            |                       |
      |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_).                                |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+

#. Specify a name for the vault.

   The name can contain 1 to 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed. Example: **vault-612c**

   .. note::

      You can also use the default name **vault\_**\ *xxxx*.

#. Complete the creation as prompted.

#. Go back to the **SFS Turbo Backups** page. You can see the created vault in the vault list.

   You can associate file systems with the new vault and back up the file systems. For details, see :ref:`Vault Management <cbr_03_0002>`.

.. |image1| image:: /_static/images/en-us_image_0000001587692708.png
.. |image2| image:: /_static/images/en-us_image_0000001599596653.jpg
.. |image3| image:: /_static/images/en-us_image_0000002159985785.png
.. |image4| image:: /_static/images/en-us_image_0000001992180742.png
.. |image5| image:: /_static/images/en-us_image_0251430145.png
