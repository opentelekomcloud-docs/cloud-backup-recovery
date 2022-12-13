:original_name: ListVersions.html

.. _ListVersions:

Querying API Versions
=====================

Function
--------

This API is used to query the information of API versions.

URI
---

GET /

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 300**

.. table:: **Table 1** Response body parameters

   +-----------+------------------------------------------------------------------+----------------------+
   | Parameter | Type                                                             | Description          |
   +===========+==================================================================+======================+
   | versions  | Array of :ref:`Version <listversions__response_version>` objects | List of API versions |
   +-----------+------------------------------------------------------------------+----------------------+

.. _listversions__response_version:

.. table:: **Table 2** Version

   +-----------------------+------------------------------------------------------------+------------------------+
   | Parameter             | Type                                                       | Description            |
   +=======================+============================================================+========================+
   | id                    | String                                                     | API version ID         |
   |                       |                                                            |                        |
   |                       |                                                            | Enumeration values:    |
   |                       |                                                            |                        |
   |                       |                                                            | -  **v3**              |
   +-----------------------+------------------------------------------------------------+------------------------+
   | status                | String                                                     | API version status     |
   |                       |                                                            |                        |
   |                       |                                                            | Enumeration values:    |
   |                       |                                                            |                        |
   |                       |                                                            | -  **CURRENT**         |
   +-----------------------+------------------------------------------------------------+------------------------+
   | links                 | Array of :ref:`Link <listversions__response_link>` objects | URI of the API version |
   +-----------------------+------------------------------------------------------------+------------------------+

.. _listversions__response_link:

.. table:: **Table 3** Link

   ========= ====== =======================
   Parameter Type   Description
   ========= ====== =======================
   href      String Domain name
   rel       String Domain name description
   ========= ====== =======================

Example Requests
----------------

None

Example Responses
-----------------

None

Status Codes
------------

=========== ====================
Status Code Description
=========== ====================
300         List of API versions
=========== ====================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
