:original_name: cbr_01_0011.html

.. _cbr_01_0011:

Permissions
===========

If you need to assign different permissions to personnel in your enterprise to access your CBR resources, Identity and Access Management (IAM) is a good choice for fine-grained permissions management. IAM provides identity authentication, permissions management, and access control, helping you to securely access your cloud resources.

With IAM, you can create IAM users and assign permissions to control their access to specific resources. For example, if you want some software developers in your enterprise to use CBR resources but do not want them to delete CBR resource or perform any other high-risk operations, you can create IAM users and grant permission to use CBR resources but not permission to delete them.

If your cloud account does not require individual IAM users for permissions management, you can skip this section.

IAM is a free service. You only pay for the resources in your account. For more information about IAM, see `IAM Service Overview <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0026.html>`__.

CBR Permissions
---------------

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and attach policies or roles to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

CBR is a project-level service deployed for specific regions. When you set **Scope** to **Region-specific projects** and select the specified projects in the specified regions, the users only have permissions for CBR resources in the selected projects. If you set **Scope** to **All resources**, the users have permissions for CBR resources in all region-specific projects. When accessing CBR resources, the users need to switch to the authorized region.

You can grant permissions by using roles and policies.

-  Roles: A coarse-grained authorization strategy provided by IAM to assign permissions based on users' job responsibilities. Only a limited number of service-level roles are available for authorization. Cloud services depend on each other. When you grant permissions using roles, you also need to attach any existing role dependencies. Roles are not ideal for fine-grained authorization and least privilege access.
-  Policies: A fine-grained authorization strategy that defines permissions required to perform operations on specific cloud resources under certain conditions. This type of authorization is more flexible and is ideal for least privilege access. For example, you can grant users only permission to manage ECSs of a certain type. A majority of fine-grained policies contain permissions for specific APIs, and permissions are defined using API actions. For the API actions supported by CBR, see `Permissions Policies and Supported Actions <https://docs.otc.t-systems.com/cloud-backup-recovery/api-ref/permissions_policies_and_supported_actions/introduction.html>`__.

:ref:`Table 1 <cbr_01_0011__table19991717191614>` lists all the system-defined permissions for CBR.

.. _cbr_01_0011__table19991717191614:

.. table:: **Table 1** System-defined permissions for CBR

   +--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Policy Name                    | Description                                                                                                                                                   | Type                  |
   +================================+===============================================================================================================================================================+=======================+
   | CBR FullAccess                 | Administrator permissions for CBR. Users with these permissions can operate and use all vaults, backups, and policies.                                        | System-defined policy |
   +--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | CBR BackupsAndVaultsFullAccess | Common user permissions for CBR. Users with these permissions can create, view, and delete vaults and backups, but cannot create, update, or delete policies. | System-defined policy |
   +--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | CBR ReadOnlyAccess             | Read-only permissions for CBR. Users with these permissions can only view CBR data.                                                                           | System-defined policy |
   +--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

:ref:`Table 2 <cbr_01_0011__table4282145810314>` lists the common operations supported by system-defined permissions of CBR.

.. _cbr_01_0011__table4282145810314:

.. table:: **Table 2** Common operations supported by system-defined permissions of CBR

   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Operation                           | CBR FullAccess | CBR BackupsAndVaultsFullAccess | CBR ReadOnlyAccess |
   +=====================================+================+================================+====================+
   | Querying vaults                     | Supported      | Supported                      | Supported          |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Creating vaults                     | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Listing vaults                      | Supported      | Supported                      | Supported          |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Updating vaults                     | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Deleting vaults                     | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Associating resources               | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Dissociating resources              | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Creating policies                   | Supported      | Not supported                  | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Updating policies                   | Supported      | Not supported                  | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Applying policies to vaults         | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Removing policies from vaults       | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Deleting policies                   | Supported      | Not supported                  | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Performing backups                  | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Updating subscriptions              | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Querying the Agent status           | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Deleting backups                    | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Restoring data from backups         | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Associating vaults                  | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Batch adding or deleting vault tags | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Adding vault tags                   | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
   | Editing tags                        | Supported      | Supported                      | Not supported      |
   +-------------------------------------+----------------+--------------------------------+--------------------+
