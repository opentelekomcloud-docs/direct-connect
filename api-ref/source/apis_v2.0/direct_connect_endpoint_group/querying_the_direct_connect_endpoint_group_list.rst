:original_name: en-us_topic_0055025337.html

.. _en-us_topic_0055025337:

Querying the Direct Connect Endpoint Group List
===============================================

Function
--------

This API is used to query the Direct Connect endpoint group list.

URI
---

GET /v2.0/dcaas/dc-endpoint-groups

Request
-------

:ref:`Table 1 <en-us_topic_0055025337__en-us_topic_0070658771_table2198437322244>` lists the request parameter.

.. _en-us_topic_0055025337__en-us_topic_0070658771_table2198437322244:

.. table:: **Table 1** Request parameter

   +-----------------+-----------------+-----------------+------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                |
   +=================+=================+=================+============================================================+
   | fields          | String          | No              | Specifies the parameters expected to be returned.          |
   |                 |                 |                 |                                                            |
   |                 |                 |                 | If you do not specify it, all parameters will be returned. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------+

Response
--------

:ref:`Table 2 <en-us_topic_0055025337__en-us_topic_0070658771_table33326591155835>` lists the response parameter.

.. _en-us_topic_0055025337__en-us_topic_0070658771_table33326591155835:

.. table:: **Table 2** Response parameter

   +--------------------+------+---------------------------------------------------+
   | Parameter          | Type | Description                                       |
   +====================+======+===================================================+
   | dc_endpoint_groups | List | Specifies the Direct Connect endpoint group list. |
   +--------------------+------+---------------------------------------------------+

.. table:: **Table 3** Description of field **dc_endpoint_groups**

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                         |
   +=======================+=======================+=====================================================================================+
   | id                    | String                | Specifies the ID of the Direct Connect endpoint group.                              |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------+
   | name                  | String                | Specifies the name of the Direct Connect endpoint group.                            |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the Direct Connect endpoint group.         |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------+
   | endpoints             | List<String>          | Specifies the list of the endpoints in a Direct Connect endpoint group.             |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------+
   | type                  | String                | Specifies the type of the Direct Connect endpoints. The value can only be **cidr**. |
   |                       |                       |                                                                                     |
   |                       |                       | Only IPv4 CIDR blocks are supported.                                                |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   #. Querying all Direct Connect endpoint groups

   .. code-block:: text

      GET /v2.0/dcaas/dc-endpoint-groups

   2. Querying a Direct Connect endpoint group by ID

   .. code-block:: text

      GET /v2.0/dcaas/dc-endpoint-groups?id=6ecd9cf3-ca64-46c7-863f-f2eb1b9e838a

-  Example response

   .. code-block::

      {
           "dc_endpoint_groups" : [{
               "id" : "6ecd9cf3-ca64-46c7-863f-f2eb1b9e838a",
               "tenant_id" : "6fbe9263116a4b68818cf1edce16bc4f",
               "name" : "endpoint group1",
               "description" : "",
               "endpoints" : [ "10.2.0.0/24", "10.3.0.0/24" ],
               "type" : "cidr"
          }]
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
