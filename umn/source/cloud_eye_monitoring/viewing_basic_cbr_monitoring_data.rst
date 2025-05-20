:original_name: cbr_03_0114.html

.. _cbr_03_0114:

Viewing Basic CBR Monitoring Data
=================================

Scenarios
---------

This section describes metrics reported by CBR as well as their namespaces and dimensions. You can use the console or APIs provided by Cloud Eye to query the metrics generated for CBR.

Namespace
---------

SYS.CBR

Metrics
-------

.. table:: **Table 1** CBR metrics

   +-----------------+-----------------+-----------------------------+-------------+------+-----------------+------------------------------+------------------------------+
   | Metric ID       | Metric Name     | Description                 | Value Range | Unit | Conversion Rule | Monitored Object (Dimension) | Monitoring Period (Raw Data) |
   +=================+=================+=============================+=============+======+=================+==============================+==============================+
   | used_vault_size | Used Vault Size | Used capacity of the vault  | >= 0        | GB   | 1024 (IEC)      | Vault                        | 15 min                       |
   +-----------------+-----------------+-----------------------------+-------------+------+-----------------+------------------------------+------------------------------+
   | vault_util      | Vault Usage     | Capacity usage of the vault | 0~100       | %    | N/A             | Vault                        | 15 min                       |
   +-----------------+-----------------+-----------------------------+-------------+------+-----------------+------------------------------+------------------------------+

Dimensions
----------

=========== =============
Key         Value
=========== =============
instance_id Vault name/ID
=========== =============

Viewing Monitoring Statistics
-----------------------------

#. Log in to the management console.

#. View the monitoring graphs using either of the following methods.

   -  Method 1: Choose **Storage** > **Cloud Backup and Recovery**. In the vault list, locate the vault whose monitoring data you want to view and choose **More** > **View Monitoring Data** in the **Operation** column.
   -  Method 2: Choose **Management & Deployment** > **Cloud Eye** > **Cloud Service Monitoring** > **Cloud Backup and Recovery**. In the vault list, click **View Metric** in the **Operation** column of the vault whose monitoring data you want to view.

#. View the vault monitoring data by metric or monitored duration.

   For more information, see the *Cloud Eye User Guide*.
