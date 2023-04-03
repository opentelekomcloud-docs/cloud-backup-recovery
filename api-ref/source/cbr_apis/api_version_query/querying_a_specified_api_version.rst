:original_name: ShowVersion.html

.. _ShowVersion:

Querying a Specified API Version
================================

Function
--------

This API is used to query the information of a specified API version.

URI
---

GET /{api_version}

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                |
   +=================+=================+=================+============================================================================================+
   | api_version     | Yes             | String          | API version (cloud service) to be queried. The value can be **vbs**, **csbs**, or **cbr**. |
   |                 |                 |                 |                                                                                            |
   |                 |                 |                 | Minimum: **3**                                                                             |
   |                 |                 |                 |                                                                                            |
   |                 |                 |                 | Maximum: **4**                                                                             |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 300**

.. table:: **Table 2** Response body parameters

   +-----------+-----------------------------------------------------------------+----------------------+
   | Parameter | Type                                                            | Description          |
   +===========+=================================================================+======================+
   | versions  | Array of :ref:`Version <showversion__response_version>` objects | List of API versions |
   +-----------+-----------------------------------------------------------------+----------------------+

.. _showversion__response_version:

.. table:: **Table 3** Version

   +-----------------------+-----------------------------------------------------------+------------------------+
   | Parameter             | Type                                                      | Description            |
   +=======================+===========================================================+========================+
   | id                    | String                                                    | API version ID         |
   |                       |                                                           |                        |
   |                       |                                                           | Enumeration values:    |
   |                       |                                                           |                        |
   |                       |                                                           | -  **v3**              |
   +-----------------------+-----------------------------------------------------------+------------------------+
   | status                | String                                                    | API version status     |
   |                       |                                                           |                        |
   |                       |                                                           | Enumeration values:    |
   |                       |                                                           |                        |
   |                       |                                                           | -  **CURRENT**         |
   +-----------------------+-----------------------------------------------------------+------------------------+
   | links                 | Array of :ref:`Link <showversion__response_link>` objects | URI of the API version |
   +-----------------------+-----------------------------------------------------------+------------------------+

.. _showversion__response_link:

.. table:: **Table 4** Link

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
