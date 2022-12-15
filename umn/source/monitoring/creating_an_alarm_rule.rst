:original_name: cbr_03_0115.html

.. _cbr_03_0115:

Creating an Alarm Rule
======================

Cloud Eye allows you to use alarm templates to create alarm rules, making it easy and convenient to add or modify alarm rules for resources or cloud services, especially for a large number of resources and cloud services.

This section describes how to create an alarm rule for CBR.

Procedure
---------

#. Log in to the management console.
#. In the upper left corner of the page, click |image1| and select your desired region and project.
#. Under **Management & Deployment**, select **Cloud Eye**. In the navigation pane on the left, choose **Alarm Management** > **Alarm Rules**.
#. On the displayed page, click **Create Alarm Rule** in the upper right corner.
#. In the **Create Alarm Rule** dialog box, set the parameters.

   a. Set **Name** and **Description**.

      .. table:: **Table 1** Parameters for configuring the rule name and description

         +-------------+-----------------------------------------------------------------------------------+---------------+
         | Parameter   | Description                                                                       | Example Value |
         +=============+===================================================================================+===============+
         | Name        | Name of the alarm rule. The system generates a random name, which you can modify. | alarm-cgnw    |
         +-------------+-----------------------------------------------------------------------------------+---------------+
         | Description | Alarm rule description. This parameter is optional.                               | ``-``         |
         +-------------+-----------------------------------------------------------------------------------+---------------+

   b. Set alarm content parameters.

      -  If you select **Cloud Backup and Recovery** for **Resource Type**, vaults are monitored with two metrics. :ref:`Table 2 <cbr_03_0115__table15644526289>` describes the parameters.

         .. _cbr_03_0115__table15644526289:

         .. table:: **Table 2** Parameters

            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
            | Parameter             | Description                                                                                                                                                                                                                                                                                                                           | Example Value             |
            +=======================+=======================================================================================================================================================================================================================================================================================================================================+===========================+
            | Resource Type         | **Cloud Backup and Recovery** is selected in this example.                                                                                                                                                                                                                                                                            | Cloud Backup and Recovery |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
            | Dimension             | Monitoring dimension. By default, monitoring is performed by vault.                                                                                                                                                                                                                                                                   | Vault                     |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
            | Monitoring Scope      | **Specific resources** is preset by default. Choose the vaults you want to monitor from the list.                                                                                                                                                                                                                                     | vault-56f8                |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
            | Method                | You can create an alarm rule by using the template or manually creating it.                                                                                                                                                                                                                                                           | Use template              |
            |                       |                                                                                                                                                                                                                                                                                                                                       |                           |
            |                       | .. note::                                                                                                                                                                                                                                                                                                                             |                           |
            |                       |                                                                                                                                                                                                                                                                                                                                       |                           |
            |                       |    If you set **Monitoring Scope** to **Specific resources**, you can set **Method** to **Use template**.                                                                                                                                                                                                                             |                           |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
            | Template              | Template to be used.                                                                                                                                                                                                                                                                                                                  | ``-``                     |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
            | Alarm Policy          | Policy for triggering an alarm.                                                                                                                                                                                                                                                                                                       | ``-``                     |
            |                       |                                                                                                                                                                                                                                                                                                                                       |                           |
            |                       | If you set **Resource Type** to a specific cloud service, the alarm policy takes effect periodically. If you set **Resource Type** to **Event Monitoring**, the alarm policy takes effect based on specific events. Alarm policy can be set for different data usage and consecutive periods generated event 5 minutes up to one day. |                           |
            |                       |                                                                                                                                                                                                                                                                                                                                       |                           |
            |                       | Currently, the following CBR monitoring metrics are supported:                                                                                                                                                                                                                                                                        |                           |
            |                       |                                                                                                                                                                                                                                                                                                                                       |                           |
            |                       | -  Vault Usage                                                                                                                                                                                                                                                                                                                        |                           |
            |                       | -  Used Vault Size                                                                                                                                                                                                                                                                                                                    |                           |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
            | Alarm Severity        | Alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.                                                                                                                                                                                                                                                | Major                     |
            +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+

      -  If you set **Resource Type** to **Event Monitoring**, CBR resources are monitored based on specific events. :ref:`Table 2 <cbr_03_0115__table15644526289>` describes the parameters.

         .. table:: **Table 3** Parameters

            +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+
            | Parameter             | Description                                                                                           | Example Value         |
            +=======================+=======================================================================================================+=======================+
            | Resource Type         | **Event Monitoring** is selected in this example.                                                     | Event Monitoring      |
            +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+
            | Dimension             | Metric dimension of the selected resource type.                                                       | System event          |
            +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+
            | Monitoring Scope      | Monitoring scope for event monitoring.                                                                | ``-``                 |
            |                       |                                                                                                       |                       |
            |                       | Default value: **All resources**                                                                      |                       |
            +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+
            | Method                | Select Create manually.                                                                               | Create manually       |
            +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+
            | Alarm Policy          | Policy for triggering an alarm.                                                                       | ``-``                 |
            |                       |                                                                                                       |                       |
            |                       | :ref:`Table 4 <cbr_03_0115__table12179172910594>` lists the supported CBR events that trigger alarms. |                       |
            +-----------------------+-------------------------------------------------------------------------------------------------------+-----------------------+

         .. _cbr_03_0115__table12179172910594:

         .. table:: **Table 4** CBR events that trigger alarms

            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            | Event Source | Event Name                                     | Alarm Severity | Description                                    | Solution                                                                | Impact                    |
            +==============+================================================+================+================================================+=========================================================================+===========================+
            | CBR          | Failed to create the backup.                   | Major          | Backup creation failed.                        | Manually create a backup or contact the administrator.                  | Data may be lost.         |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | Failed to restore the resource using a backup. | Major          | Resource restoration using a backup failed.    | Restore the resource using another backup or contact the administrator. | Data may be lost.         |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | Failed to delete the backup.                   | Major          | Backup deletion failed.                        | Try again later or contact the administrator.                           | Charging may be abnormal. |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | Failed to delete the vault.                    | Major          | Vault deletion failed.                         | Try again later or contact the administrator.                           | Charging may be abnormal. |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | Replication failure                            | Major          | Backup replication failed.                     | Try again later or contact the administrator.                           | Data may be lost.         |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | The backup is created successfully.            | Major          | Backup created.                                | None                                                                    | None                      |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | Resource restoration using a backup succeeded. | Major          | Resource restoration using a backup succeeded. | Check that data is successfully restored.                               | None                      |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | The backup is deleted successfully.            | Major          | Backup deleted.                                | None                                                                    | None                      |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | The vault is deleted successfully.             | Major          | Vault deleted.                                 | None                                                                    | None                      |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+
            |              | Replication success                            | Major          | Backup replicated.                             | None                                                                    | None                      |
            +--------------+------------------------------------------------+----------------+------------------------------------------------+-------------------------------------------------------------------------+---------------------------+

         .. note::

            You can change the alarm severity as needed.

   c. Configure the alarm notification.

      .. table:: **Table 5** Parameters for configuring alarm notification

         +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Parameter             | Description                                                                                                                                                                                                                                                        | Example Value         |
         +=======================+====================================================================================================================================================================================================================================================================+=======================+
         | Alarm Notification    | Specifies whether to notify users when alarms are triggered. Notifications can be sent by email or text message, or through HTTP/HTTPS request to servers.                                                                                                         | ``-``                 |
         |                       |                                                                                                                                                                                                                                                                    |                       |
         |                       | You can enable (recommended) or disable **Alarm Notification**.                                                                                                                                                                                                    |                       |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Validity Period       | Cloud Eye sends notifications only within the validity period specified in the alarm rule.                                                                                                                                                                         | ``-``                 |
         |                       |                                                                                                                                                                                                                                                                    |                       |
         |                       | For example, if **Validity Period** is set to **00:00-8:00**, Cloud Eye sends notifications only within 00:00-8:00.                                                                                                                                                |                       |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Notification Object   | Specifies the name of the topic the alarm notification is to be sent to.                                                                                                                                                                                           | ``-``                 |
         |                       |                                                                                                                                                                                                                                                                    |                       |
         |                       | If you enable alarm notification, you need to select a topic. If no desirable topics are available, you need to create one first, whereupon the SMN service is invoked. For details about how to create a topic, see the *Simple Message Notification User Guide*. |                       |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Trigger Condition     | Specifies the condition for triggering the alarm notification. You can select **Generated alarm**, **Cleared alarm**, or both.                                                                                                                                     | ``-``                 |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   d. Click **Create**.

After the alarm rule is created, if the metric data reaches the specified threshold or a CBR event happens, Cloud Eye immediately informs you that an exception has occurred. For details, see the *Cloud Eye User Guide*.

.. |image1| image:: /_static/images/en-us_image_0297214500.png
