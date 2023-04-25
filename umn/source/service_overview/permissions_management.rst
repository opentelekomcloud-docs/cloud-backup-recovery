:original_name: cbr_01_0011.html

.. _cbr_01_0011:

Permissions Management
======================

If you need to assign different permissions to employees in your enterprise to control their access to your CBR resources on the cloud, Identity and Access Management (IAM) is a good choice for fine-grained permissions management. IAM provides identity authentication, permissions management, and access control, helping you secure access to your cloud resources.

With IAM, you can use your cloud account to create IAM users for your employees, and assign permissions to them to control their access to specific types of resources. For example, you can create IAM users for software developers and grant them only the permissions required for using CBR resources to allow them to use CBR resources but prevent them from performing any other operations.

If your cloud account does not require individual IAM users for permissions management, skip this section.

IAM is free of charge. For more information about IAM, see `IAM Service Overview <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0026.html>`__.

CBR Permissions
---------------

By default, new IAM users do not have permissions assigned. You need to add an IAM user to one or more groups, and attach permissions policies or roles to these groups. Users inherit permissions from the groups to which they are added and can perform specified operations on cloud services based on the permissions.

CBR is a project-level service deployed and accessed in specific physical regions. To assign CBR permissions to a user group, specify the scope as region-specific projects and select projects for the permissions to take effect. If **All projects** is selected, the permissions will take effect for the user group in all region-specific projects. When accessing CBR, the users need to switch to a region where they have been authorized to use this service.

You can grant users permissions by using roles and policies.

-  Roles: A type of coarse-grained authorization mechanism that defines permissions related to users responsibilities. Only a limited number of service-level roles for authorization are available. When using roles to grant permissions, you need to also assign other roles on which the permissions depend to take effect. However, roles are not an ideal choice for fine-grained authorization and secure access control.
-  Policies: A type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization, meeting requirements for secure access control. For example, you can grant ECS users only the permissions for managing a certain type of ECSs. Most policies define permissions based on APIs. For the API actions supported by CBR, see `Permissions Policies and Supported Actions <https://docs.otc.t-systems.com/en-us/api/cbr/cbr_04_0017.html>`__.

:ref:`Table 1 <cbr_01_0011__table19991717191614>` lists all the system-defined roles and policies supported by CBR.

.. _cbr_01_0011__table19991717191614:

.. table:: **Table 1** System-defined policies supported by CBR

   +--------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Policy Name                    | Description                                                                                                                                                      | Type                  |
   +================================+==================================================================================================================================================================+=======================+
   | CBR FullAccess                 | Administrator permissions for CBR. Users granted these permissions can operate and use all vaults, backups, and policies.                                        | System-defined policy |
   +--------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | CBR BackupsAndVaultsFullAccess | Common user permissions for CBR. Users granted these permissions can create, view, and delete vaults and backups, but cannot create, update, or delete policies. | System-defined policy |
   +--------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | CBR ReadOnlyAccess             | Read-only permissions for CBR. Users granted these permissions can only view CBR data.                                                                           | System-defined policy |
   +--------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

:ref:`Table 2 <cbr_01_0011__table4282145810314>` lists the common operations supported by each system-defined policy or role of CBR. Select the policies or roles as required.

.. _cbr_01_0011__table4282145810314:

.. table:: **Table 2** Common operations supported by each system-defined policy or role of CBR

   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Operation                           | CBR FullAccess | CBR BackupsAndVaultsFullAccess | CBR ReadOnlyAccess |
   +=====================================+================+================================+====================+
   | Querying vaults                     | Y              | Y                              | Y                  |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Creating vaults                     | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Listing vaults                      | Y              | Y                              | Y                  |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Updating vaults                     | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Deleting vaults                     | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Associating resources               | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Dissociating resources              | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Creating policies                   | Y              |                                |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Updating policies                   | Y              |                                |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Applying policies to a vault        | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Removing policies from a vault      | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Deleting policies                   | Y              |                                |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Performing backups                  | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Updating subscriptions              | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Querying the Agent status           | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Deleting backups                    | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Restoring data using backups        | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Associating vaults                  | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Batch adding or deleting vault tags | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Adding vault tags                   | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Editing tags                        | Y              | Y                              |                    |
   +-------------------------------------+----------------+--------------------------------+--------------------+
