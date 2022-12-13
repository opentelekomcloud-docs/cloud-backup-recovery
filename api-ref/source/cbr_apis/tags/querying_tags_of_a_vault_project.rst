:original_name: ShowVaultProjectTag.html

.. _ShowVaultProjectTag:

Querying Tags of a Vault Project
================================

Function
--------

This API is used to query a tenant's tag set in a specific region and of a specific instance type. TMS uses this API to list tags created by a tenant to facilitate tag creation and resource filtering on the console.

URI
---

GET /v3/{project_id}/vault/tags

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   ========== ========= ====== ===========

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------+---------------------------------------------------------------------------+-------------+
   | Parameter | Type                                                                      | Description |
   +===========+===========================================================================+=============+
   | tags      | Array of :ref:`TagsResp <showvaultprojecttag__response_tagsresp>` objects | Tag list    |
   +-----------+---------------------------------------------------------------------------+-------------+

.. _showvaultprojecttag__response_tagsresp:

.. table:: **Table 3** TagsResp

   +-----------------------+-----------------------+----------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                    |
   +=======================+=======================+================================================================+
   | key                   | String                | Key                                                            |
   |                       |                       |                                                                |
   |                       |                       | It consists of up to 36 characters.                            |
   |                       |                       |                                                                |
   |                       |                       | It cannot be an empty string.                                  |
   |                       |                       |                                                                |
   |                       |                       | It can contain only letters, digits, hyphens, and underscores. |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | values                | String                | List of values                                                 |
   |                       |                       |                                                                |
   |                       |                       | It consists of up to 43 characters.                            |
   |                       |                       |                                                                |
   |                       |                       | It can be an empty string.                                     |
   |                       |                       |                                                                |
   |                       |                       | It can contain only letters, digits, hyphens, and underscores. |
   +-----------------------+-----------------------+----------------------------------------------------------------+

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

   GET  https://{endpoint}/v3/{project_id}/vault/tags

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "tags" : [ {
       "values" : [ "b" ],
       "key" : "a"
     }, {
       "values" : [ "", "string" ],
       "key" : "string"
     } ]
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
