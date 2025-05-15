:original_name: ShowVaultResourceInstances.html

.. _ShowVaultResourceInstances:

Querying Vault Resources
========================

Function
--------

This API is used to filter resources by tag.

Tag Management Service (TMS) uses this API to filter and list resources of each service by tag. These services must have the query capabilities.

URI
---

POST /v3/{project_id}/vault/resource_instances/action

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   ========== ========= ====== ===========

Request Parameters
------------------

.. table:: **Table 2** Request body parameters

   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                          | Description                                                                                                                                                                                                                                                                                                                          |
   +=================+=================+===============================================================================+======================================================================================================================================================================================================================================================================================================================================+
   | without_any_tag | No              | Boolean                                                                       | If this parameter is set to **true**, all resources without tags are queried. In this case, the **tag**, **not_tags**, **tags_any**, and **not_tags_any** fields are ignored.                                                                                                                                                        |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags            | No              | Array of :ref:`TagsReq <showvaultresourceinstances__request_tagsreq>` objects | List of included tags                                                                                                                                                                                                                                                                                                                |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | This list cannot be an empty list.                                                                                                                                                                                                                                                                                                   |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The list can contain up to 20 keys.                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Keys in this list must be unique.                                                                                                                                                                                                                                                                                                    |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Values in this list are in an AND relationship.                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The response returns resources containing all tags in this list. Keys in this list are in an AND relationship while values in each key-value structure is in an OR relationship.                                                                                                                                                     |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | If no filtering condition is specified, full data is returned.                                                                                                                                                                                                                                                                       |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags_any        | No              | Array of :ref:`TagsReq <showvaultresourceinstances__request_tagsreq>` objects | List of any included tags                                                                                                                                                                                                                                                                                                            |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | This list cannot be an empty list.                                                                                                                                                                                                                                                                                                   |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The list can contain up to 20 keys.                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Keys in this list must be unique.                                                                                                                                                                                                                                                                                                    |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The response returns resources containing any tag in this list. Keys in this list are in an OR relationship while values in each key-value structure is in an OR relationship.                                                                                                                                                       |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | If no filtering condition is specified, full data is returned.                                                                                                                                                                                                                                                                       |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags        | No              | Array of :ref:`TagsReq <showvaultresourceinstances__request_tagsreq>` objects | List of excluded tags                                                                                                                                                                                                                                                                                                                |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | This list cannot be an empty list.                                                                                                                                                                                                                                                                                                   |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The list can contain up to 20 keys.                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Keys in this list must be unique.                                                                                                                                                                                                                                                                                                    |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The response returns resources containing no tags in this list. Keys in this list are in an AND relationship while values in each key-value structure is in an OR relationship.                                                                                                                                                      |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | If no filtering condition is specified, full data is returned.                                                                                                                                                                                                                                                                       |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags_any    | No              | Array of :ref:`TagsReq <showvaultresourceinstances__request_tagsreq>` objects | List of any excluded tags                                                                                                                                                                                                                                                                                                            |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | This list cannot be an empty list.                                                                                                                                                                                                                                                                                                   |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The list can contain up to 20 keys.                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Keys in this list must be unique.                                                                                                                                                                                                                                                                                                    |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | The response returns resources without any tags in this list. Keys in this list are in an OR relationship while values in each key-value structure is in an OR relationship.                                                                                                                                                         |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | If no filtering condition is specified, full data is returned.                                                                                                                                                                                                                                                                       |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | String                                                                        | Query count. (This parameter is not displayed when **action** is set to **count**.) If action is set to **filter**, the value defaults to **1000**. The value ranges from **1** to **1000**. If you set a value not within this range, an error will be reported. The number of returned records does not exceed the value of limit. |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | String                                                                        | Index position. (This parameter is not displayed when **action** is set to **count**.) If **action** is set to **filter**, the value defaults to **0** and the minimum value of offset is **0**. The first record in the query result is the offset+1 record that meets the query criteria.                                          |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action          | Yes             | String                                                                        | Operation identifier. Possible values are **filter** and **count**. The value **filter** indicates pagination query. The value **count** indicates that the total number of query results meeting the search criteria will be returned.                                                                                              |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | matches         | No              | Array of :ref:`Match <showvaultresourceinstances__request_match>` objects     | Search criteria supported by resources                                                                                                                                                                                                                                                                                               |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Keys in this list must be unique.                                                                                                                                                                                                                                                                                                    |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Only one key is supported currently. Multiple-key support will be available later.                                                                                                                                                                                                                                                   |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | cloud_type      | No              | String                                                                        | Cloud type                                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Enumeration values:                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | -  **public**                                                                                                                                                                                                                                                                                                                        |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | object_type     | No              | String                                                                        | Resource type                                                                                                                                                                                                                                                                                                                        |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | Enumeration values:                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | -  **server**                                                                                                                                                                                                                                                                                                                        |
   |                 |                 |                                                                               |                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                                               | -  **disk**                                                                                                                                                                                                                                                                                                                          |
   +-----------------+-----------------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__request_tagsreq:

.. table:: **Table 3** TagsReq

   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                                                                        |
   +=================+=================+==================+====================================================================================================================================================================+
   | key             | Yes             | String           | Key                                                                                                                                                                |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | It contains a maximum of 127 Unicode characters.                                                                                                                   |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | A tag key cannot be an empty string.                                                                                                                               |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | Spaces before and after a key will be deprecated.                                                                                                                  |
   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | values          | Yes             | Array of strings | Lists the values                                                                                                                                                   |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | The list can contain up to 20 values.                                                                                                                              |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | A tag value contains up to 255 Unicode characters. Spaces before and after a key will be deprecated.                                                               |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | Values in this list must be unique.                                                                                                                                |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | Values in this list are in an OR relationship.                                                                                                                     |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | This list can be empty and each value can be an empty character string.                                                                                            |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | An empty value list means any values.                                                                                                                              |
   |                 |                 |                  |                                                                                                                                                                    |
   |                 |                 |                  | \* is a reserved character in the system. If the value starts with \*, fuzzy match is performed based on the value following \*. The value cannot contain only \*. |
   +-----------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__request_match:

.. table:: **Table 4** Match

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                             |
   +=================+=================+=================+=========================================================================================================================================+
   | key             | Yes             | String          | Key                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                         |
   |                 |                 |                 | A key can only be set to **resource_name**, indicating the resource name.                                                               |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------+
   | value           | Yes             | String          | Value                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                         |
   |                 |                 |                 | A value consists of up to 255 characters                                                                                                |
   |                 |                 |                 |                                                                                                                                         |
   |                 |                 |                 | If **key** is set to **resource_name**, an empty character string indicates exact match and any non-empty string indicates fuzzy match. |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-------------+----------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------+
   | Parameter   | Type                                                                                   | Description                                                                                    |
   +=============+========================================================================================+================================================================================================+
   | resources   | Array of :ref:`TagResource <showvaultresourceinstances__response_tagresource>` objects | List of matched resources (This parameter is not displayed if **action** is set to **count**.) |
   +-------------+----------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------+
   | total_count | Integer                                                                                | Total number of matched resources                                                              |
   +-------------+----------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__response_tagresource:

.. table:: **Table 6** TagResource

   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------+
   | Parameter             | Type                                                                       | Description                                            |
   +=======================+============================================================================+========================================================+
   | resource_id           | String                                                                     | Resource ID                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------+
   | resource_detail       | Array of :ref:`Vault <showvaultresourceinstances__response_vault>` objects | Resource details                                       |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------+
   | tags                  | Array of :ref:`Tag <showvaultresourceinstances__response_tag>` objects     | Tag list                                               |
   |                       |                                                                            |                                                        |
   |                       |                                                                            | If there is no tag, an empty array is used by default. |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------+
   | resource_name         | String                                                                     | Resource name                                          |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------+

.. _showvaultresourceinstances__response_vault:

.. table:: **Table 7** Vault

   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                                     | Description                                                                                       |
   +=======================+==========================================================================================+===================================================================================================+
   | billing               | :ref:`Billing <showvaultresourceinstances__response_billing>` object                     | Operation info                                                                                    |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | description           | String                                                                                   | User-defined vault description                                                                    |
   |                       |                                                                                          |                                                                                                   |
   |                       |                                                                                          | Minimum: **0**                                                                                    |
   |                       |                                                                                          |                                                                                                   |
   |                       |                                                                                          | Maximum: **255**                                                                                  |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | id                    | String                                                                                   | Vault ID                                                                                          |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | name                  | String                                                                                   | Vault name                                                                                        |
   |                       |                                                                                          |                                                                                                   |
   |                       |                                                                                          | Minimum: **1**                                                                                    |
   |                       |                                                                                          |                                                                                                   |
   |                       |                                                                                          | Maximum: **64**                                                                                   |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | project_id            | String                                                                                   | Project ID                                                                                        |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | provider_id           | String                                                                                   | ID of the vault resource type                                                                     |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | resources             | Array of :ref:`ResourceResp <showvaultresourceinstances__response_resourceresp>` objects | Vault resources                                                                                   |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | tags                  | Array of :ref:`Tag <showvaultresourceinstances__response_tag>` objects                   | Vault tags                                                                                        |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | auto_bind             | Boolean                                                                                  | Indicates whether automatic association is enabled. Its default value is **false** (not enabled). |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | bind_rules            | :ref:`VaultBindRules <showvaultresourceinstances__response_vaultbindrules>` object       | Association rule                                                                                  |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | user_id               | String                                                                                   | User ID                                                                                           |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | created_at            | String                                                                                   | Creation time, for example, **2020-02-05T10:38:34.209782**                                        |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | auto_expand           | Boolean                                                                                  | Whether to enable auto capacity expansion for the vault.                                          |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | locked                | Boolean                                                                                  | Whether the vault is locked.                                                                      |
   +-----------------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__response_billing:

.. table:: **Table 8** Billing

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                     |
   +=======================+=======================+=================================================================================================================================================================+
   | allocated             | Integer               | Allocated capacity, in GB.                                                                                                                                      |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | charging_mode         | String                | Billing mode, which is **post_paid**                                                                                                                            |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | cloud_type            | String                | Cloud type, which is **public**                                                                                                                                 |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | consistent_level      | String                | Vault specification, which is **crash_consistent** by default (crash consistent backup)                                                                         |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | object_type           | String                | Object type, which can be **server**, **disk**, or **turbo**                                                                                                    |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | order_id              | String                | Order ID                                                                                                                                                        |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | product_id            | String                | Product ID                                                                                                                                                      |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protect_type          | String                | Protection type, which can be **backup** or **replication**                                                                                                     |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | size                  | Integer               | Capacity, in GB                                                                                                                                                 |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | Minimum: **1**                                                                                                                                                  |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | Maximum: **10485760**                                                                                                                                           |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | spec_code             | String                | Specification code                                                                                                                                              |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | Server backup vault: **vault.backup.server.normal**; Disk backup vault: **vault.backup.volume.normal**; File system backup vault: **vault.backup.turbo.normal** |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Vault status                                                                                                                                                    |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | Enumeration values:                                                                                                                                             |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | -  **available**                                                                                                                                                |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | -  **lock**                                                                                                                                                     |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | -  **frozen**                                                                                                                                                   |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | -  **deleting**                                                                                                                                                 |
   |                       |                       |                                                                                                                                                                 |
   |                       |                       | -  **error**                                                                                                                                                    |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | storage_unit          | String                | Name of the bucket for the vault                                                                                                                                |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | used                  | Integer               | Used capacity, in MB.                                                                                                                                           |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | frozen_scene          | String                | Scenario when an account is frozen                                                                                                                              |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__response_resourceresp:

.. table:: **Table 9** ResourceResp

   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                                     | Description                                                                                                            |
   +=======================+==========================================================================================+========================================================================================================================+
   | extra_info            | :ref:`ResourceExtraInfo <showvaultresourceinstances__response_resourceextrainfo>` object | Additional information of the resource                                                                                 |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | id                    | String                                                                                   | ID of the resource to be backed up                                                                                     |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                                                                                   | Name of the resource to be backed up                                                                                   |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | Minimum: **0**                                                                                                         |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | Maximum: **255**                                                                                                       |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | protect_status        | String                                                                                   | Protection status                                                                                                      |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | Enumeration values:                                                                                                    |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | -  **available**                                                                                                       |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | -  **error**                                                                                                           |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | -  **protecting**                                                                                                      |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | -  **restoring**                                                                                                       |
   |                       |                                                                                          |                                                                                                                        |
   |                       |                                                                                          | -  **removing**                                                                                                        |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | size                  | Integer                                                                                  | Allocated capacity for the associated resources, in GB                                                                 |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | type                  | String                                                                                   | Type of the resource to be backed up, which can be **OS::Nova::Server**, **OS::Cinder::Volume**, or **OS::Sfs::Turbo** |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | backup_size           | Integer                                                                                  | Backup size                                                                                                            |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+
   | backup_count          | Integer                                                                                  | Number of backups                                                                                                      |
   +-----------------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__response_resourceextrainfo:

.. table:: **Table 10** ResourceExtraInfo

   +-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type             | Description                                                                                                                                                                                                                                                                                 |
   +=================+==================+=============================================================================================================================================================================================================================================================================================+
   | exclude_volumes | Array of strings | IDs of the disks that will not be backed up. This parameter is used when servers are added to a vault, which include all server disks. But some disks do not need to be backed up. Or in case that a server was previously added and some disks on this server do not need to be backed up. |
   +-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__response_vaultbindrules:

.. table:: **Table 11** VaultBindRules

   +-----------+--------------------------------------------------------------------------------------------+----------------------------------------------------+
   | Parameter | Type                                                                                       | Description                                        |
   +===========+============================================================================================+====================================================+
   | tags      | Array of :ref:`BindRulesTags <showvaultresourceinstances__response_bindrulestags>` objects | Filters automatically associated resources by tag. |
   +-----------+--------------------------------------------------------------------------------------------+----------------------------------------------------+

.. _showvaultresourceinstances__response_bindrulestags:

.. table:: **Table 12** BindRulesTags

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                             |
   +=======================+=======================+=========================================================================================================+
   | key                   | String                | The key cannot contain non-printable ASCII characters (0-31) and the following characters: ``=*<>\,|/`` |
   |                       |                       |                                                                                                         |
   |                       |                       | The key can contain only letters, digits, underscores (_), and hyphens (-).                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------+
   | value                 | String                | The value cannot contain non-printable ASCII characters (0-31) and the following characters: =*<>,|/    |
   |                       |                       |                                                                                                         |
   |                       |                       | The value can contain only letters, digits, underscores (_), and hyphens (-).                           |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------+

.. _showvaultresourceinstances__response_tag:

.. table:: **Table 13** Tag

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

.. table:: **Table 14** Response body parameters

   ========== ====== ================================================
   Parameter  Type   Description
   ========== ====== ================================================
   error_code String For details, see :ref:`Error Codes <errorcode>`.
   error_msg  String Error message
   ========== ====== ================================================

Example Requests
----------------

.. code-block:: text

   POST  https://{endpoint}/v3/{project_id}/vault/resource_instances/action

   {
     "tags" : [ {
       "key" : "string",
       "values" : [ "value" ]
     } ],
     "action" : "filter"
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "tags" : [ {
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
