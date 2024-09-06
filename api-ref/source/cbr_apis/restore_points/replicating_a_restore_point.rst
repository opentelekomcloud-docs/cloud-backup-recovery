:original_name: CopyCheckpoint.html

.. _CopyCheckpoint:

Replicating a Restore Point
===========================

Function
--------

This API is used to replicate a restore point. In compare to console, it is vault replication and this API replicates all backups from source vault to destination vault.

URI
---

POST /v3/{project_id}/checkpoints/replicate

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   ========== ========= ====== ===========

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +--------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter    | Mandatory | Type   | Description                                                                                                                                                         |
   +==============+===========+========+=====================================================================================================================================================================+
   | X-Auth-Token | Yes       | String | User token The token can be obtained by calling the IAM API used to obtain a user token. The value of **X-Subject-Token** in the response header is the user token. |
   +--------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   +-----------+-----------+-------------------------------------------------------------------------------------------+------------------------------------------------------------+
   | Parameter | Mandatory | Type                                                                                      | Description                                                |
   +===========+===========+===========================================================================================+============================================================+
   | replicate | Yes       | :ref:`CheckpointReplicateParam <copycheckpoint__request_checkpointreplicateparam>` object | Parameters in the request body of performing a replication |
   +-----------+-----------+-------------------------------------------------------------------------------------------+------------------------------------------------------------+

.. _copycheckpoint__request_checkpointreplicateparam:

.. table:: **Table 4** CheckpointReplicateParam

   +------------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter              | Mandatory       | Type            | Description                                                                                                                                        |
   +========================+=================+=================+====================================================================================================================================================+
   | auto_trigger           | No              | Boolean         | Whether to automatically trigger replication this time. The default value is **false**, indicating the replication needs to be manually triggered. |
   +------------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | destination_project_id | Yes             | String          | ID of the replication destination project                                                                                                          |
   +------------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | destination_region     | Yes             | String          | ID of the replication destination region                                                                                                           |
   |                        |                 |                 |                                                                                                                                                    |
   |                        |                 |                 | Minimum: **0**                                                                                                                                     |
   |                        |                 |                 |                                                                                                                                                    |
   |                        |                 |                 | Maximum: **255**                                                                                                                                   |
   +------------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | destination_vault_id   | Yes             | String          | ID of the vault in the replication destination region                                                                                              |
   +------------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | vault_id               | Yes             | String          | Vault ID (UUID)                                                                                                                                    |
   +------------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-------------+--------------------------------------------------------------------------------------------------+-------------+
   | Parameter   | Type                                                                                             | Description |
   +=============+==================================================================================================+=============+
   | replication | :ref:`CheckpointReplicateRespBody <copycheckpoint__response_checkpointreplicaterespbody>` object |             |
   +-------------+--------------------------------------------------------------------------------------------------+-------------+

.. _copycheckpoint__response_checkpointreplicaterespbody:

.. table:: **Table 6** CheckpointReplicateRespBody

   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | Parameter              | Type                                                                                                             | Description                                                                       |
   +========================+==================================================================================================================+===================================================================================+
   | backups                | Array of :ref:`CheckpointReplicateRespbackups <copycheckpoint__response_checkpointreplicaterespbackups>` objects | List of backups to be replicated                                                  |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | destination_project_id | String                                                                                                           | ID of the replication destination project                                         |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | destination_region     | String                                                                                                           | Replication destination region                                                    |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | destination_vault_id   | String                                                                                                           | ID of the vault in the replication destination region                             |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | project_id             | String                                                                                                           | ID of the project where replication is performed                                  |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | provider_id            | String                                                                                                           | Backup provider ID, which specifies whether the backup object is a server or disk |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | source_region          | String                                                                                                           | Replication source region                                                         |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | vault_id               | String                                                                                                           | Vault ID                                                                          |
   +------------------------+------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+

.. _copycheckpoint__response_checkpointreplicaterespbackups:

.. table:: **Table 7** CheckpointReplicateRespbackups

   +-----------------------+--------+----------------------------------------------+
   | Parameter             | Type   | Description                                  |
   +=======================+========+==============================================+
   | backup_id             | String | ID of the source backup used for replication |
   +-----------------------+--------+----------------------------------------------+
   | replication_record_id | String | Replication record ID                        |
   +-----------------------+--------+----------------------------------------------+

Example Requests
----------------

Replicating backups

.. code-block:: text

   POST https://{endpoint}/v3/f841e01fd2b14e7fa41b6ae7aa6b0594/checkpoints/replicate

   {
     "replicate" : {
       "auto_trigger" : false,
       "destination_project_id" : "68589cac08274b82b4e254268a3862d8",
       "destination_region" : "region2",
       "destination_vault_id" : "0ca3eb86-8800-46da-9c37-9d657a825274",
       "vault_id" : "3b5816b5-f29c-4172-9d9a-76c719a659ce"
     }
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "replication" : {
       "destination_vault_id" : "0ca3eb86-8800-46da-9c37-9d657a825274",
       "provider_id" : "0daac4c5-6707-4851-97ba-169e36266b66",
       "source_region" : "region1",
       "vault_id" : "3b5816b5-f29c-4172-9d9a-76c719a659ce",
       "destination_region" : "region2",
       "destination_project_id" : "68589cac08274b82b4e254268a3862d8",
       "backups" : [ {
         "replication_record_id" : "de128dfa-5451-4905-9c11-8fc842b2f41e",
         "backup_id" : "7558e1a3-7046-4787-95cd-14b0ad0642a8"
       }, {
         "replication_record_id" : "892a7d1e-17c8-4751-ad75-cfbed7051857",
         "backup_id" : "6df2b54c-dd62-4059-a07c-1b8f24f2725d"
       }, {
         "replication_record_id" : "8bf5ce8f-bfa1-4d57-98de-d6159ab9d86d",
         "backup_id" : "aa00034d-ef40-443d-ab7a-dc846d988cdf"
       } ],
       "project_id" : "4229d7a45436489f8c3dc2b1d35d4987"
     }
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
