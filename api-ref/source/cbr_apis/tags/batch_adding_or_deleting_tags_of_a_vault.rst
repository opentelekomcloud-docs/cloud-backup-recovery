:original_name: BatchCreateAndDeleteVaultTags.html

.. _BatchCreateAndDeleteVaultTags:

Batch Adding or Deleting Tags of a Vault
========================================

Function
--------

This API is used to batch add or delete tags for a specified instance. TMS uses this API to manage service resource tags. A resource can have a maximum of 10 tags. This API is idempotent. If there are duplicate keys in the request body when you add tags, an error is reported. If a to-be-added tag has the same key as an existing tag, the tag will be added and overwrite the existing tag. When deleting tags, you can upload duplicate keys. When deleting tags, if some tags do not exist, the deletion is considered to be successful by default. The character set of the tags will not be verified. A key and a value can individually consist of up to 127 and 255 characters. When you delete tags, the tags structure cannot be missing, and the key cannot be left blank or be an empty string.

URI
---

POST /v3/{project_id}/vault/{vault_id}/tags/action

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   vault_id   Yes       String Resource ID
   ========== ========= ====== ===========

Request Parameters
------------------

.. table:: **Table 2** Request body parameters

   +-----------------+-----------------+--------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                     | Description                                                                       |
   +=================+=================+==========================================================================+===================================================================================+
   | tags            | No              | Array of :ref:`Tag <batchcreateanddeletevaulttags__request_tag>` objects | Tag list                                                                          |
   |                 |                 |                                                                          |                                                                                   |
   |                 |                 |                                                                          | This list cannot be an empty list.                                                |
   |                 |                 |                                                                          |                                                                                   |
   |                 |                 |                                                                          | The list can contain up to 10 keys.                                               |
   |                 |                 |                                                                          |                                                                                   |
   |                 |                 |                                                                          | Keys in this list must be unique.                                                 |
   +-----------------+-----------------+--------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | action          | Yes             | String                                                                   | Operation to be performed. The value can be set to **create** or **delete** only. |
   |                 |                 |                                                                          |                                                                                   |
   |                 |                 |                                                                          | Enumeration values:                                                               |
   |                 |                 |                                                                          |                                                                                   |
   |                 |                 |                                                                          | -  **create**                                                                     |
   |                 |                 |                                                                          |                                                                                   |
   |                 |                 |                                                                          | -  **delete**                                                                     |
   +-----------------+-----------------+--------------------------------------------------------------------------+-----------------------------------------------------------------------------------+

.. _batchcreateanddeletevaulttags__request_tag:

.. table:: **Table 3** Tag

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                     |
   +=================+=================+=================+=================================================================================================================================================================================================================+
   | key             | Yes             | String          | Key                                                                                                                                                                                                             |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It can contain a maximum of 36 characters.                                                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It cannot be an empty string.                                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | Spaces before and after a key will be discarded.                                                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It cannot contain the following characters: ASCII (0-31), equal signs (=), asterisks (``*``), left angle brackets (<), right angle brackets (>), backslashes (), commas (,), vertical bars (|), and slashes (/) |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It can contain only letters, digits, hyphens (-), and underscores (_).                                                                                                                                          |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value           | No              | String          | Value                                                                                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It is mandatory when a tag is added and optional when a tag is deleted.                                                                                                                                         |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It can contain a maximum of 43 characters.                                                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It can be an empty string.                                                                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | Spaces before and after a value will be discarded.                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It cannot contain the following characters: ASCII (0-31), equal signs (=), asterisks (``*``), left angle brackets (<), right angle brackets (>), backslashes (), commas (,), vertical bars (|), and slashes (/) |
   |                 |                 |                 |                                                                                                                                                                                                                 |
   |                 |                 |                 | It can contain only letters, digits, hyphens (-), and underscores (_).                                                                                                                                          |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

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

Example request

.. code-block:: text

   POST  https://{endpoint}/v3/{project_id}/vault/{vault_id}/tags/action

   {
     "tags" : [ {
       "key" : "string",
       "value" : "string"
     }, {
       "key" : "string1",
       "value" : "string2"
     } ],
     "action" : "create"
   }

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
204         No Content
400         Bad Request
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
