:original_name: ListProjectTags.html

.. _ListProjectTags:

Querying Tags by Project
========================

Function
--------

-  This API is used to query all resource tags of a resource in a specified project.
-  TMS uses this API to list tags created by a tenant to ease tag creation and resource filtering.

URI
---

GET /v3/{project_id}/{resource_type}/tags

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

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +------------+------------------------------------------------------------------------------------------+---------------------------+
   | Parameter  | Type                                                                                     | Description               |
   +============+==========================================================================================+===========================+
   | tags       | Array of :ref:`Tag <listprojecttags__en-us_topic_0000001782705393_response_tag>` objects | Specifies the tag list.   |
   +------------+------------------------------------------------------------------------------------------+---------------------------+
   | request_id | String                                                                                   | Specifies the request ID. |
   +------------+------------------------------------------------------------------------------------------+---------------------------+

.. _listprojecttags__en-us_topic_0000001782705393_response_tag:

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

.. code-block:: text

   GET https://{dc_endpoint}/v3/ed28c294165741faaeccab26913122a1/dc-directconnect/tags

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "tags" : [ {
       "key" : "department",
       "value" : "finance"
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
