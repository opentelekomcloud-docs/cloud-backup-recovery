:original_name: cbr_03_0048.html

.. _cbr_03_0048:

Creating a User and Granting CBR Permissions
============================================

This section describes how to use IAM to implement fine-grained permissions control for your CBR resources. With IAM, you can:

-  Create IAM users for personnel based on your enterprise's organizational structure. Each IAM user has their own identity credentials for accessing CBR resources.
-  Grant users only the permissions required to perform a given task based on their job responsibilities.
-  Entrust a cloud account or cloud service to perform efficient O&M on your CBR resources.

If your cloud account does not require individual IAM users, skip this section. If your account cannot meet your requirements, create IAM users by referring to `Identity and Access Management User Guide <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0026.html>`__.

Figure :ref:`Figure 1 <cbr_03_0048__fig194521431175317>` illustrates the procedure for granting permissions.

Prerequisites
-------------

Learn about the permissions (see :ref:`Permissions <cbr_01_0011>`) supported by CBR and choose policies or roles according to your requirements. For the system policies of other services, see section "Permissions".

Process Flow
------------

.. _cbr_03_0048__fig194521431175317:

.. figure:: /_static/images/en-us_image_0000001562229993.png
   :alt: **Figure 1** Process for granting CBR permissions

   **Figure 1** Process for granting CBR permissions

#. .. _cbr_03_0048__li3656183032711:

   Create a user group and assign permissions.

   Create a user group on the IAM console, and assign the **CBR ReadOnlyAccess** policy to the group.

#. Create an IAM user and add it to the user group.

   Create a user on the IAM console and add the user to the group created in :ref:`1 <cbr_03_0048__li3656183032711>`.

#. Log in and verify permissions.

   Log in to the CBR console as the created user and verify that the user has read-only permissions for CBR.

   -  Choose **Service List** > **Cloud Backup and Recovery**. Then click **Create Server Backup Vault** on the CBR console. If a message appears indicating that you do not have the permissions to perform the operation, the **CBR ReadOnlyAccess** policy has already taken effect.
   -  Choose any other service in **Service List**. If a message appears indicating that you do not have the permissions to access the service, the **CBR ReadOnlyAccess** policy has already taken effect.
