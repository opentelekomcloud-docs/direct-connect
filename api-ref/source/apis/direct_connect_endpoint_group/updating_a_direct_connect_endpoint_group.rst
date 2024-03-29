:original_name: en-dc_topic_0055025340.html

.. _en-dc_topic_0055025340:

Updating a Direct Connect Endpoint Group
========================================

Function
--------

This API is used to update a Direct Connect endpoint group.

URI
---

PUT /v2.0/dcaas/dc-endpoint-groups/{endpoint_group_id}

.. table:: **Table 1** Parameter description

   +-------------------+--------+-----------+--------------------------------------------------------+
   | Parameter         | Type   | Mandatory | Description                                            |
   +===================+========+===========+========================================================+
   | endpoint_group_id | String | Yes       | Specifies the ID of the Direct Connect endpoint group. |
   +-------------------+--------+-----------+--------------------------------------------------------+

Request
-------

:ref:`Table 2 <en-dc_topic_0055025340__en-us_topic_0070658694_table49278871155710>` lists the request parameter.

.. _en-dc_topic_0055025340__en-us_topic_0070658694_table49278871155710:

.. table:: **Table 2** Request parameter

   +-------------------+------------+-----------+---------------------------------------------+
   | Parameter         | Type       | Mandatory | Description                                 |
   +===================+============+===========+=============================================+
   | dc_endpoint_group | Dictionary | Yes       | Specifies the **dc_endpoint_group** object. |
   +-------------------+------------+-----------+---------------------------------------------+

.. table:: **Table 3** Description of field **dc_endpoint_group**

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                      |
   +=================+=================+=================+==================================================================================+
   | description     | String          | No              | Provides supplementary information about the Direct Connect endpoint group.      |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | Angle brackets (<>) are not allowed.                                             |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | name            | String          | No              | Specifies the name of the Direct Connect endpoint group.                         |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+

Response
--------

:ref:`Table 4 <en-dc_topic_0055025340__en-us_topic_0070658694_table33326591155835>` lists the response parameter.

.. _en-dc_topic_0055025340__en-us_topic_0070658694_table33326591155835:

.. table:: **Table 4** Response parameter

   ================= ========== ===========================================
   Parameter         Type       Description
   ================= ========== ===========================================
   dc_endpoint_group Dictionary Specifies the **dc_endpoint_group** object.
   ================= ========== ===========================================

.. table:: **Table 5** Description of field **dc_endpoint_group**

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

   .. code-block:: text

      PUT /v2.0/dcaas/dc-endpoint-groups/{endpoint_group_id}
      {
          "dc_endpoint_group" : {
              "name" : "endpoint group1",
              "description" : "New description"
          }
      }

-  Example response

   .. code-block::

      {
           "dc_endpoint_groups" : {
               "id" : "6ecd9cf3-ca64-46c7-863f-f2eb1b9e838a",
               "tenant_id" : "6fbe9263116a4b68818cf1edce16bc4f",
               "name" : "endpoint group1",
               "description" : "New description",
               "endpoints" : [ "10.2.0.0/24", "10.3.0.0/24" ],
               "type" : "cidr"
          }
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-dc_topic_0055025342>`.
