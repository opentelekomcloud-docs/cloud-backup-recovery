:original_name: CreateVaultTags.html

.. _CreateVaultTags:

Adding a Tag to an Associated Resource
======================================

Function
--------

This API is used to add a tag to an associated resource. A resource can have a maximum of 20 tags.

This API is idempotent. If a to-be-added tag has the same key as an existing tag, the tag will be added and will overwrite the existing tag.

URI
---

POST /v3/{project_id}/vault/{vault_id}/tags

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

   +-----------+-----------+--------------------------------------------------+-------------+
   | Parameter | Mandatory | Type                                             | Description |
   +===========+===========+==================================================+=============+
   | tag       | No        | :ref:`Tag <createvaulttags__request_tag>` object | Tag         |
   +-----------+-----------+--------------------------------------------------+-------------+

.. _createvaulttags__request_tag:

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

   POST  https://{endpoint}/v3/{project_id}/vault/{vault_id}/tags

   {
     "tag" : {
       "key" : "key1",
       "value" : "key2"
     }
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
