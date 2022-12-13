:original_name: ShowVaultTag.html

.. _ShowVaultTag:

Querying Tags of an Associated Resource
=======================================

Function
--------

This API is used to query tags of a specified resource. TMS uses this API to query all tags of a specified resource.

URI
---

GET /v3/{project_id}/vault/{vault_id}/tags

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   vault_id   Yes       String Resource ID
   ========== ========= ====== ===========

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------+----------------------------------------------------------+-----------------------------------------------+
   | Parameter | Type                                                     | Description                                   |
   +===========+==========================================================+===============================================+
   | tags      | Array of :ref:`Tag <showvaulttag__response_tag>` objects | Tag list Keys in the tag list must be unique. |
   +-----------+----------------------------------------------------------+-----------------------------------------------+

.. _showvaulttag__response_tag:

.. table:: **Table 3** Tag

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                                                     |
   +=======================+=======================+=================================================================================================================================================================================================================+
   | key                   | String                | Key                                                                                                                                                                                                             |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It can contain a maximum of 36 characters.                                                                                                                                                                      |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It cannot be an empty string.                                                                                                                                                                                   |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | Spaces before and after a key will be discarded.                                                                                                                                                                |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It cannot contain the following characters: ASCII (0-31), equal signs (=), asterisks (``*``), left angle brackets (<), right angle brackets (>), backslashes (), commas (,), vertical bars (|), and slashes (/) |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It can contain only letters, digits, hyphens (-), and underscores (_).                                                                                                                                          |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value                 | String                | Value                                                                                                                                                                                                           |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It is mandatory when a tag is added and optional when a tag is deleted.                                                                                                                                         |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It can contain a maximum of 43 characters.                                                                                                                                                                      |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It can be an empty string.                                                                                                                                                                                      |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | Spaces before and after a value will be discarded.                                                                                                                                                              |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It cannot contain the following characters: ASCII (0-31), equal signs (=), asterisks (``*``), left angle brackets (<), right angle brackets (>), backslashes (), commas (,), vertical bars (|), and slashes (/) |
   |                       |                       |                                                                                                                                                                                                                 |
   |                       |                       | It can contain only letters, digits, hyphens (-), and underscores (_).                                                                                                                                          |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

**Status code: 400**

.. table:: **Table 4** Response body parameters

   ========== ====== ================================================
   Parameter  Type   Description
   ========== ====== ================================================
   error_code String For details, see :ref:`Error Codes <errorcode>`.
   error_msg  String Error message
   ========== ====== ================================================

Example Requests
----------------

.. code-block:: text

   GET  https://{endpoint}/v3/{project_id}/vault/{vault_id}/tags

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "tags" : [ {
       "key" : "string",
       "value" : ""
     } ]
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "BackupService.9900",
     "error_msg" : "Invalid vault_id provided."
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         OK
400         Bad Request
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
