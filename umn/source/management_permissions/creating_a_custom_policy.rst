:original_name: cbr_03_0050.html

.. _cbr_03_0050:

Creating a Custom Policy
========================

You can create custom policies to supplement the system-defined policies of CBR. For the actions supported for custom policies, see section "Permissions Policies and Supported Actions" in *Cloud Backup and Recovery API Reference*.

You can create custom policies in either of the following ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Edit JSON policies from scratch or based on an existing policy.

For details about how to create custom policies, see `Creating a Custom Policy <https://docs.otc.t-systems.com/identity-access-management/umn/user_guide/fine-grained_policy_management/creating_a_custom_policy.html>`__.

This section provides examples of common CBR custom policies.

Example Custom Policies
-----------------------

-  Example 1: Allowing users to create, modify, and delete vaults

   .. code-block::

      {
            "Version": "1.1",
            "Statement": [
                  {
                        "Effect": "Allow",
                        "Action": [
                              "cbr:*:get*",
                              "cbr:*:list*",
                              "cbr:vaults:update",
                              "cbr:vaults:delete",
                              "cbr:vaults:create"
                        ]
                  }
            ]
      }

-  Example 2: Denying users to delete vaults and backups

   A policy with only "Deny" permissions must be used in conjunction with other policies to take effect. If the permissions assigned to a user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   If you need to assign permissions of the **CBR FullAccess** policy to a user but want to prevent the user from deleting vaults and backups, create a custom policy for denying vault and backup deletion, and attach both policies to the group to which the user belongs. In this way, the user can perform all operations on CBR except deleting vaults or backups. The following is an example deny policy:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Deny",
                  "Action": [
                      "cbr:backups:delete",
                      "cbr:vaults:delete"
                  ]
              }
          ]
      }

-  Example 3: Defining permissions for multiple services in a policy

   A custom policy can contain the actions of multiple services that are of the global or project-level type. The following is an example policy containing actions of multiple services:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "cbr:vaults:create",
                      "cbr:vaults:update",
                      "cbr:vaults:delete"
                  ]
              },
              {
                  "Effect": "Allow",
                  "Action": [
                      "sfs:shares:createShare"
                  ]
              }
          ]
      }
