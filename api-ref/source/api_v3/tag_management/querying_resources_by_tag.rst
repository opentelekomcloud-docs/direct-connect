:original_name: ListTagResourceInstances.html

.. _ListTagResourceInstances:

Querying Resources by Tag
=========================

Function
--------

This API is used to query resources by tag.

URI
---

POST /v3/{project_id}/{resource_type}/resource-instances/action

.. table:: **Table 1** URI parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                      |
   +=================+=================+=================+==================================================================================================================+
   | project_id      | Yes             | String          | Specifies the project ID.                                                                                        |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------+
   | resource_type   | Yes             | String          | -  Specifies the Direct Connect resource type. The value can be **dc-directconnect**, **dc-vgw**, or **dc-vif**. |
   |                 |                 |                 | -  **dc-directconnect**: Direct Connect connection                                                               |
   |                 |                 |                 | -  **dc-vgw**: virtual gateway                                                                                   |
   |                 |                 |                 | -  **dc-vif**: virtual interface                                                                                 |
   |                 |                 |                 |                                                                                                                  |
   |                 |                 |                 | Enumeration values:                                                                                              |
   |                 |                 |                 |                                                                                                                  |
   |                 |                 |                 | -  **dc-directconnect**                                                                                          |
   |                 |                 |                 | -  **dc-vgw**                                                                                                    |
   |                 |                 |                 | -  **dc-vif**                                                                                                    |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request body parameters

   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                                                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +=================+=================+======================================================================================================+================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | offset          | No              | String                                                                                               | Specifies the index position. The query starts from the next image indexed by this parameter. This parameter is not required when you query data on the first page. The value in the response returned for querying data on the previous page will be included in this parameter for querying data on subsequent pages. This parameter is not available when **action** is set to **count**. If **action** is set to **filter**, the value must be a number, and the default value is **0**. The value cannot be a negative number.                                            |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | String                                                                                               | Number of records. This parameter is not available when **action** is set to **count**. The default value is **1000** when **action** is set to **filter**. The maximum value is **1000**, and the minimum value is **1**. The value cannot be a negative number.                                                                                                                                                                                                                                                                                                              |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action          | Yes             | String                                                                                               | The value can only be **filter** or **count**. The value filter indicates pagination query. The value count indicates that the total number of query results meeting the search criteria will be returned. Returning other fields is not allowed.                                                                                                                                                                                                                                                                                                                              |
   |                 |                 |                                                                                                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |                 |                 |                                                                                                      | Enumeration values:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
   |                 |                 |                                                                                                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |                 |                 |                                                                                                      | -  **filter**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                                                                      | -  **count**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | matches         | No              | Array of :ref:`Match <listtagresourceinstances__en-us_topic_0000001735825440_request_match>` objects | Specifies the search criteria. The tag key is the parameter to match, for example, **resource_name**. The tag value indicates the value to be matched. This field is a fixed dictionary value. Determine whether fuzzy match is required based on different fields. For example, if **key** is **resource_name**, fuzzy search (case insensitive) is used by default. If **value** is an empty string, exact match is used. If **key** is **resource_id**, exact match is used. Only **resource_name** for **key** is supported. Other **key** values will be available later. |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags        | No              | Array of :ref:`Tags <listtagresourceinstances__en-us_topic_0000001735825440_request_tags>` objects   | Specifies the excluded tags. Each tag contains a maximum of 10 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value of a tag must also be unique. Resources not identified by different keys are in AND relationship, and values in one tag are in OR relationship. If **not_tags_any** is not specified, all resources will be returned.                                                                                     |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags            | No              | Array of :ref:`Tags <listtagresourceinstances__en-us_topic_0000001735825440_request_tags>` objects   | A maximum of 10 keys can be queried at a time, and each key can contain a maximum of 10 values. The structure body must be included. The tag key cannot be left blank or be an empty string. Each tag key must be unique, and each tag value of a tag must also be unique. Resources identified by different keys are in AND relationship, and values in one tag are in OR relationship. If no tag filtering criteria is specified, full data is returned.                                                                                                                     |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags_any        | No              | Array of :ref:`Tags <listtagresourceinstances__en-us_topic_0000001735825440_request_tags>` objects   | Specifies any included tags. Each tag contains a maximum of 10 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value of a tag must also be unique. Resources identified by different keys are in OR relationship, and values in one tag are in OR relationship. If **not_tags_any** is not specified, all resources will be returned.                                                                                          |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags_any    | No              | Array of :ref:`Tags <listtagresourceinstances__en-us_topic_0000001735825440_request_tags>` objects   | Specifies any excluded tags. Each tag contains a maximum of 10 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value of a tag must also be unique. Resources not identified by different keys are in OR relationship, and values in one tag are in OR relationship. If **not_tags_any** is not specified, all resources will be returned.                                                                                      |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sys_tags        | No              | Array of :ref:`Tags <listtagresourceinstances__en-us_topic_0000001735825440_request_tags>` objects   | Only users with the **op_service** permission can use this parameter to filter resources. Only one tag structure is contained when this API is called by Tag Management Service (TMS). The **key** is **\_sys_enterprise_project_id**, and the **value** is the enterprise project ID list. Currently, each key can contain only one value. **0** indicates the default enterprise project. **sys_tags** and tenant tag filtering conditions (**without_any_tag**, **tags**, **tags_any**, **not_tags**, and **not_tags_any**) cannot be used at the same time.                |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listtagresourceinstances__en-us_topic_0000001735825440_request_match:

.. table:: **Table 3** Match

   +-----------+-----------+--------+------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                              |
   +===========+===========+========+==========================================================================================+
   | key       | Yes       | String | Specifies the tag key. The value can be **dc-directconnect**, **dc-vgw**, or **dc-vif**. |
   +-----------+-----------+--------+------------------------------------------------------------------------------------------+
   | value     | Yes       | String | Specifies the tag value. It can contain a maximum of 255 Unicode characters.             |
   +-----------+-----------+--------+------------------------------------------------------------------------------------------+

.. _listtagresourceinstances__en-us_topic_0000001735825440_request_tags:

.. table:: **Table 4** Tags

   +-----------+-----------+------------------+-----------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type             | Description                                                                                                     |
   +===========+===========+==================+=================================================================================================================+
   | key       | Yes       | String           | Specifies the tag key. A key can contain a maximum of 127 Unicode characters. The tag key cannot be left blank. |
   +-----------+-----------+------------------+-----------------------------------------------------------------------------------------------------------------+
   | values    | Yes       | Array of strings | Lists the tag values. It can contain a maximum of 255 Unicode characters.                                       |
   +-----------+-----------+------------------+-----------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+
   | Parameter   | Type                                                                                                        | Description                              |
   +=============+=============================================================================================================+==========================================+
   | resources   | Array of :ref:`Resource <listtagresourceinstances__en-us_topic_0000001735825440_response_resource>` objects | Specifies the resource list.             |
   +-------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+
   | total_count | Integer                                                                                                     | Specifies the total number of resources. |
   +-------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+
   | request_id  | String                                                                                                      | Specifies the request ID.                |
   +-------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+

.. _listtagresourceinstances__en-us_topic_0000001735825440_response_resource:

.. table:: **Table 6** Resource

   +-----------------+---------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type                                                                                              | Description                                                                                                                            |
   +=================+===================================================================================================+========================================================================================================================================+
   | resource_detail | Object                                                                                            | Provides details about the resource. The value is a resource object, used for extension. **resource_detail** is left blank by default. |
   +-----------------+---------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | resource_id     | String                                                                                            | Specifies the resource ID.                                                                                                             |
   +-----------------+---------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | resource_name   | String                                                                                            | Resource name. This parameter is an empty string by default if there is no resource name.                                              |
   +-----------------+---------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | tags            | Array of :ref:`Tag <listtagresourceinstances__en-us_topic_0000001735825440_response_tag>` objects | Specifies the list of queried tags. If no tag is matched, an empty array is returned.                                                  |
   +-----------------+---------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | sys_tags        | Array of :ref:`Tag <listtagresourceinstances__en-us_topic_0000001735825440_response_tag>` objects | Specifies the list of queried tags. If no tag is matched, an empty array is returned.                                                  |
   +-----------------+---------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

.. _listtagresourceinstances__en-us_topic_0000001735825440_response_tag:

.. table:: **Table 7** Tag

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                       |
   +=======================+=======================+===================================================================================================+
   | key                   | String                | Specifies the tag key. The key:                                                                   |
   |                       |                       |                                                                                                   |
   |                       |                       | -  Cannot be left blank.                                                                          |
   |                       |                       | -  Must be unique for each resource.                                                              |
   |                       |                       | -  Can contain a maximum of 36 Unicode characters.                                                |
   |                       |                       | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.). |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------+
   | value                 | String                | Specifies the tag value. The value:                                                               |
   |                       |                       |                                                                                                   |
   |                       |                       | -  Can be left blank.                                                                             |
   |                       |                       | -  Can contain a maximum of 43 Unicode characters.                                                |
   |                       |                       | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.). |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------+

Example Requests
----------------

-  Querying resources (**action** set to **filter**)

   .. code-block::

      https://{endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/dc-vgw/resource-instances/action

      {
        "offset" : "10",
        "limit" : "10",
        "action" : "filter",
        "matches" : [ {
          "key" : "resource_name",
          "value" : "resource1"
        } ],
        "not_tags" : [ {
          "key" : "key1",
          "values" : [ "*value1", "value2" ]
        } ],
        "tags" : [ {
          "key" : "key1",
          "values" : [ "*value1", "value2" ]
        } ],
        "tags_any" : [ {
          "key" : "key1",
          "values" : [ "value1", "value2" ]
        } ],
        "not_tags_any" : [ {
          "key" : "key1",
          "values" : [ "value1", "value2" ]
        } ]
      }

-  Querying the total number of resources (**action** set to **count**)

   .. code-block::

      https://{endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/dc-vgw/resource_instances/action

      {
        "action" : "count",
        "not_tags" : [ {
          "key" : "key1",
          "values" : [ "value1", "*value2" ]
        } ],
        "tags" : [ {
          "key" : "key1",
          "values" : [ "value1", "value2" ]
        }, {
          "key" : "key2",
          "values" : [ "value1", "value2" ]
        } ],
        "tags_any" : [ {
          "key" : "key1",
          "values" : [ "value1", "value2" ]
        } ],
        "not_tags_any" : [ {
          "key" : "key1",
          "values" : [ "value1", "value2" ]
        } ],
        "sys_tags" : [ {
          "key" : "_sys_enterprise_project_id",
          "values" : [ "5aa119a8-d25b-45a7-8d1b-88e127885635" ]
        } ],
        "matches" : [ {
          "key" : "resource_name",
          "value" : "resource1"
        } ]
      }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "resources" : [ ],
     "total_count" : 0,
     "request_id" : "9a4f4dfc4fb2fc101e65bba07d908535"
   }

Status Code
-----------

=========== ===========
Status Code Description
=========== ===========
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
