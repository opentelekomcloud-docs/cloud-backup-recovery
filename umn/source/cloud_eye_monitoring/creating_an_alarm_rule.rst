:original_name: cbr_03_0115.html

.. _cbr_03_0115:

Creating an Alarm Rule
======================

Cloud Eye allows you to use alarm templates to create alarm rules, making it easy and convenient to add or modify alarm rules for resources or cloud services, especially for a large number of resources and cloud services.

You can create alarm rules for CBR.

Creating an Alarm Rule Using Cloud Eye
--------------------------------------

#. Log in to the Cloud Eye console.
#. In the upper left corner, click |image1| and select a region.
#. Under **Management & Deployment**, select **Cloud Eye**. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.
#. On the displayed page, click **Create Alarm Rule** in the upper right corner.
#. On the displayed **Create alarm rule** page, configure the parameters.

   a. Set **Name** and **Description**.

      Parameters for configuring the rule name and description

      +-------------+---------------------------------------------------------------------------------------+---------------+
      | Parameter   | Description                                                                           | Example Value |
      +=============+=======================================================================================+===============+
      | Name        | Name of the alarm rule. Cloud Eye will generate a random name, but you can modify it. | alarm-cgnw    |
      +-------------+---------------------------------------------------------------------------------------+---------------+
      | Description | Alarm rule description. This parameter is optional.                                   | ``-``         |
      +-------------+---------------------------------------------------------------------------------------+---------------+

   b. Configure alarm content parameters.

      -  If you select **Cloud Backup and Recovery** for **Resource Type**, vaults are monitored with two metrics. :ref:`Table 1 <cbr_03_0115__table15644526289>` describes the parameters.

         .. _cbr_03_0115__table15644526289:

         .. table:: **Table 1** Parameters

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

   c. Configure alarm notifications.

      .. table:: **Table 2** Parameters for configuring alarm notifications

         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Parameter             | Description                                                                                                                                                                                                   | Example Value         |
         +=======================+===============================================================================================================================================================================================================+=======================+
         | Alarm Notification    | Specifies whether users are notified when alarms are triggered. Notifications can be delivered by email, text message, or HTTP/HTTPS requests.                                                                | ``-``                 |
         |                       |                                                                                                                                                                                                               |                       |
         |                       | You can enable (recommended) or disable **Alarm Notification**.                                                                                                                                               |                       |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Notification Window   | Cloud Eye sends notifications only within the notification window specified in the alarm rule.                                                                                                                | ``-``                 |
         |                       |                                                                                                                                                                                                               |                       |
         |                       | If **Notification Window** is set to **00:00-8:00**, Cloud Eye sends alarm notifications only within 00:00-8:00.                                                                                              |                       |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Notification Object   | The name of the topic the alarm notification is to be sent to.                                                                                                                                                | ``-``                 |
         |                       |                                                                                                                                                                                                               |                       |
         |                       | If you enable alarm notification, you need to select a topic. If no desirable topics are available, create one and subscribe to it first. For more details, see the *Simple Message Notification User Guide*. |                       |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Trigger Condition     | The condition for triggering the alarm notification. You can select **Generated alarm**, **Cleared alarm**, or both.                                                                                          | ``-``                 |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   d. Click **Create**.

After the alarm rule is created, if the metric data reaches the specified threshold or there is a CBR event, Cloud Eye immediately informs you that an exception has occurred. For details, see the *Cloud Eye User Guide*.

.. |image1| image:: /_static/images/en-us_image_0297214500.png
