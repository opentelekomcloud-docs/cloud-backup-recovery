:original_name: DeleteVaultTag.html

.. _DeleteVaultTag:

Deleting a Tag from an Associated Resource
==========================================

Function
--------

This API is used to delete a tag from an associated resource. The API is idempotent. When you delete a nonexistent tag, error code 404 will be returned. Tag keys cannot be empty or be empty character strings.

URI
---

DELETE /v3/{project_id}/vault/{vault_id}/tags/{key}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                                                                 |
   +============+===========+========+=============================================================================================================================================================================================================================================+
   | key        | Yes       | String | The key cannot be left blank or be an empty string. The key length and character set are not verified. Keys are verified and used after the spaces before and after them are deleted. Even invalid tags at the bottom layer can be deleted. |
   +------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id | Yes       | String | Project ID                                                                                                                                                                                                                                  |
   +------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vault_id   | Yes       | String | Resource ID                                                                                                                                                                                                                                 |
   +------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 400**

.. table:: **Table 2** Response body parameters

   ========== ====== ================================================
   Parameter  Type   Description
   ========== ====== ================================================
   error_code String For details, see :ref:`Error Codes <errorcode>`.
   error_msg  String Error message
   ========== ====== ================================================

Example Requests
----------------

.. code-block:: text

   DELETE  https://{endpoint}/v3/{project_id}/vault/{vault_id}/tags/{key}

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
