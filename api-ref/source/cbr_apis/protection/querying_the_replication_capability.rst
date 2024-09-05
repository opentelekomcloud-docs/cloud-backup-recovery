:original_name: ShowReplicationCapabilities.html

.. _ShowReplicationCapabilities:

Querying the Replication Capability
===================================

Function
--------

This API is used to query the replication capability of the current region.

URI
---

GET /v3/{project_id}/replication-capabilities

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

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
   | Parameter | Type                                                                                                                                                      | Description                              |
   +===========+===========================================================================================================================================================+==========================================+
   | regions   | Array of :ref:`ProtectableReplicationCapabilitiesRespRegion <showreplicationcapabilities__response_protectablereplicationcapabilitiesrespregion>` objects | List of regions that support replication |
   +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+

.. _showreplicationcapabilities__response_protectablereplicationcapabilitiesrespregion:

.. table:: **Table 4** ProtectableReplicationCapabilitiesRespRegion

   +--------------------------+------------------+----------------------------------------+
   | Parameter                | Type             | Description                            |
   +==========================+==================+========================================+
   | name                     | String           | Region where the cloud service resides |
   +--------------------------+------------------+----------------------------------------+
   | replication_destinations | Array of strings | List of supported destination regions  |
   +--------------------------+------------------+----------------------------------------+

Example Requests
----------------

.. code-block:: text

   GET https://{endpoint}/v3/{project_id}/replication-capabilities

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "regions" : [ {
       "name" : "eu-de",
       "replication_destinations" : [ "eu-nl" ]
     } ]
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
