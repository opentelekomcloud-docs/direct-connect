:original_name: ShowResourceTag.html

.. _ShowResourceTag:

Querying Tags of a Resource
===========================

Function
--------

This API is used to query the tags of a resource.

URI
---

GET /v3/{project_id}/{resource_type}/{resource_id}/tags

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
   | resource_id     | Yes             | String          | Specifies the resource ID.                                                                                       |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
   | Parameter  | Type                                                                                     | Description                                                                           |
   +============+==========================================================================================+=======================================================================================+
   | tags       | Array of :ref:`Tag <showresourcetag__en-us_topic_0000001735825436_response_tag>` objects | Specifies the tag list.                                                               |
   +------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
   | sys_tags   | Array of :ref:`Tag <showresourcetag__en-us_topic_0000001735825436_response_tag>` objects | Specifies the list of queried tags. If no tag is matched, an empty array is returned. |
   +------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
   | request_id | String                                                                                   | Specifies the request ID.                                                             |
   +------------+------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+

.. _showresourcetag__en-us_topic_0000001735825436_response_tag:

.. table:: **Table 3** Tag

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

Querying tags of a resource

.. code-block::

   https://{endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/dc-vgw/resource-instances/action

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "request_id" : "80ef5f21-b81a-4546-b23d-84272507d330",
     "tags" : [ {
       "key" : "key2",
       "value" : "value2"
     }, {
       "key" : "key1",
       "value" : "value1"
     }, {
       "key" : "key3",
       "value" : "value3"
     } ]
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
