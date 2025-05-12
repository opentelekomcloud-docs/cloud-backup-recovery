:original_name: CopyBackup.html

.. _CopyBackup:

Replicating a Backup
====================

Function
--------

This API is used to replicate a backup across regions.

URI
---

POST /v3/{project_id}/backups/{backup_id}/replicate

.. table:: **Table 1** Path Parameters

   ========== ========= ====== =================================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =================================
   backup_id  Yes       String ID of the backup to be replicated
   project_id Yes       String Project ID
   ========== ========= ====== =================================

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                              |
   +=================+=================+=================+==========================================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | User token                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                          |
   |                 |                 |                 | The token can be obtained by calling the IAM API used to obtain a user token. The value of **X-Subject-Token** in the response header is the user token. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   +-----------+-----------+-----------------------------------------------------------------------------------+-----------------------+
   | Parameter | Mandatory | Type                                                                              | Description           |
   +===========+===========+===================================================================================+=======================+
   | replicate | Yes       | :ref:`BackupReplicateReqBody <copybackup__request_backupreplicatereqbody>` object | Replication parameter |
   +-----------+-----------+-----------------------------------------------------------------------------------+-----------------------+

.. _copybackup__request_backupreplicatereqbody:

.. table:: **Table 4** BackupReplicateReqBody

   +------------------------+-----------------+-----------------+-------------------------------------------------------+
   | Parameter              | Mandatory       | Type            | Description                                           |
   +========================+=================+=================+=======================================================+
   | description            | No              | String          | Replica description                                   |
   |                        |                 |                 |                                                       |
   |                        |                 |                 | Minimum: **0**                                        |
   |                        |                 |                 |                                                       |
   |                        |                 |                 | Maximum: **255**                                      |
   +------------------------+-----------------+-----------------+-------------------------------------------------------+
   | destination_project_id | Yes             | String          | ID of the replication destination project             |
   +------------------------+-----------------+-----------------+-------------------------------------------------------+
   | destination_region     | Yes             | String          | Replication destination region                        |
   |                        |                 |                 |                                                       |
   |                        |                 |                 | Minimum: **0**                                        |
   |                        |                 |                 |                                                       |
   |                        |                 |                 | Maximum: **255**                                      |
   +------------------------+-----------------+-----------------+-------------------------------------------------------+
   | destination_vault_id   | Yes             | String          | ID of the vault in the replication destination region |
   +------------------------+-----------------+-----------------+-------------------------------------------------------+
   | name                   | No              | String          | Replica name                                          |
   |                        |                 |                 |                                                       |
   |                        |                 |                 | Minimum: **1**                                        |
   |                        |                 |                 |                                                       |
   |                        |                 |                 | Maximum: **64**                                       |
   +------------------------+-----------------+-----------------+-------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-------------+--------------------------------------------------------------------------------------+--------------------------------+
   | Parameter   | Type                                                                                 | Description                    |
   +=============+======================================================================================+================================+
   | replication | :ref:`BackupReplicateRespBody <copybackup__response_backupreplicaterespbody>` object | Replication response parameter |
   +-------------+--------------------------------------------------------------------------------------+--------------------------------+

.. _copybackup__response_backupreplicaterespbody:

.. table:: **Table 6** BackupReplicateRespBody

   +------------------------+--------+-------------------------------------------------------+
   | Parameter              | Type   | Description                                           |
   +========================+========+=======================================================+
   | backup_id              | String | ID of the source backup used for replication          |
   +------------------------+--------+-------------------------------------------------------+
   | destination_project_id | String | ID of the replication destination project             |
   +------------------------+--------+-------------------------------------------------------+
   | destination_region     | String | Replication destination region                        |
   +------------------------+--------+-------------------------------------------------------+
   | destination_vault_id   | String | ID of the vault in the replication destination region |
   +------------------------+--------+-------------------------------------------------------+
   | project_id             | String | ID of the project where replication is performed      |
   +------------------------+--------+-------------------------------------------------------+
   | provider_id            | String | Resource type ID                                      |
   +------------------------+--------+-------------------------------------------------------+
   | replication_record_id  | String | Replication record ID                                 |
   +------------------------+--------+-------------------------------------------------------+
   | source_region          | String | Replication source region                             |
   +------------------------+--------+-------------------------------------------------------+

Example Requests
----------------

.. code-block:: text

   POST https://{endpoint}/v3/f841e01fd2b14e7fa41b6ae7aa6b0594/backups/a5200268-74a5-4806-acc6-95793ab0228b/replicate

   {
     "replicate" : {
       "description" : "backup_description",
       "destination_project_id" : "68589cac08274b82b4e254268a3862d8",
       "destination_region" : "region2",
       "destination_vault_id" : "0ca3eb86-8800-46da-9c37-9d657a825274",
       "name" : "backup_name"
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
       "backup_id" : "6df2b54c-dd62-4059-a07c-1b8f24f2725d",
       "destination_project_id" : "68589cac08274b82b4e254268a3862d8",
       "destination_region" : "region2",
       "source_region" : "region1",
       "project_id" : "4229d7a45436489f8c3dc2b1d35d4987",
       "replication_record_id" : "1579a71e-8d8d-41e6-85dc-d77f5ce8d91a"
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
