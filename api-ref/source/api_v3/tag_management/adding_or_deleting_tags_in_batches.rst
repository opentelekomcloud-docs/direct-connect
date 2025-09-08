:original_name: BatchCreateResourceTags.html

.. _BatchCreateResourceTags:

Adding or Deleting Tags in Batches
==================================

Function
--------

-  This API is used to add or delete tags of a specific resource in batches.
-  TMS may use this API to manage service resource tags.
-  A resource can have a maximum of 20 tags.

URI
---

POST /v3/{project_id}/{resource_type}/{resource_id}/tags/action

.. table:: **Table 1** URI parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                      |
   +=================+=================+=================+==================================================================================================================+
   | project_id      | Yes             | String          | Specifies the project ID.                                                                                        |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------+
   | resource_id     | Yes             | String          | Specifies the resource ID.                                                                                       |
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

   +-----------------+-----------------+-------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                                            | Description                                                         |
   +=================+=================+=================================================================================================+=====================================================================+
   | action          | Yes             | String                                                                                          | Specifies the action type. Value options: **create** and **delete** |
   |                 |                 |                                                                                                 |                                                                     |
   |                 |                 |                                                                                                 | Enumeration values:                                                 |
   |                 |                 |                                                                                                 |                                                                     |
   |                 |                 |                                                                                                 | -  **create**                                                       |
   |                 |                 |                                                                                                 | -  **delete**                                                       |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+
   | tags            | No              | Array of :ref:`Tag <batchcreateresourcetags__en-us_topic_0000001735666320_request_tag>` objects | Specifies the tag list.                                             |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+
   | sys_tags        | No              | Array of :ref:`Tag <batchcreateresourcetags__en-us_topic_0000001735666320_request_tag>` objects | Specifies the tag list.                                             |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+

.. _batchcreateresourcetags__en-us_topic_0000001735666320_request_tag:

.. table:: **Table 3** Tag

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                       |
   +=================+=================+=================+===================================================================================================+
   | key             | Yes             | String          | Specifies the tag key. The key:                                                                   |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | -  Cannot be left blank.                                                                          |
   |                 |                 |                 | -  Must be unique for each resource.                                                              |
   |                 |                 |                 | -  Can contain a maximum of 36 Unicode characters.                                                |
   |                 |                 |                 | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.). |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | value           | No              | String          | Specifies the tag value. The value:                                                               |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | -  Can be left blank.                                                                             |
   |                 |                 |                 | -  Can contain a maximum of 43 Unicode characters.                                                |
   |                 |                 |                 | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.). |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

None

Example Requests
----------------

-  Batch adding resource tags

   .. code-block:: text

      POST https://{endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/dc-vgw/3320166e-b937-40cc-a35c-02cd3f2b3ee2/tags/action

      {
        "action" : "create",
        "tags" : [ {
          "key" : "key1",
          "value" : "value1"
        }, {
          "key" : "key2",
          "value" : "value2"
        } ]
      }

-  Batch deleting resource tags

   .. code-block:: text

      POST https://{endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/dc-vgw/3320166e-b937-40cc-a35c-02cd3f2b3ee2/tags/action

      {
        "action" : "delete",
        "tags" : [ {
          "key" : "key1"
        }, {
          "key" : "key2",
          "value" : "value3"
        } ]
      }

Example Responses
-----------------

None

Status Code
-----------

=========== ===========
Status Code Description
=========== ===========
204         No Content
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
