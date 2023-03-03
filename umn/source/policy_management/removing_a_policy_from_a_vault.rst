:original_name: cbr_03_0030.html

.. _cbr_03_0030:

Removing a Policy from a Vault
==============================

If you no longer need automatic backup for a vault, remove the policy from the vault.

Prerequisites
-------------

A policy has been applied to the vault.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Choose a backup tab from the left navigation pane.

#. On any backup page, find the target vault and click the vault name to view the vault details.

#. In the **Policies** area, click **Remove Policy**. See :ref:`Figure 1 <cbr_03_0030__fig16691161117510>`.

   .. _cbr_03_0030__fig16691161117510:

   **Figure 1** Removing a policy

   |image2|

   .. note::

      -  If a backup task is being executed for a resource in the vault, the policy can be removed normally. However, the backup task will continue and backups will be generated.
      -  After a policy is removed, backups retained by time will expire based on the retention rule, but backups retained by quantity will not be automatically deleted. You can manually delete unwanted backups.

#. Click **Yes**. The vault will no longer execute tasks as specified in this policy.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0184119988.png
