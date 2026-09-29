:original_name: en-us_topic_0055025326.html

.. _en-us_topic_0055025326:

Updating a Virtual Gateway
==========================

Function
--------

This API is used to update a virtual gateway.

URI
---

PUT /v2.0/dcaas/virtual-gateways/{virtual_gateway_id}

.. table:: **Table 1** Parameter description

   ================== ====== ========= =================================
   Parameter          Type   Mandatory Description
   ================== ====== ========= =================================
   virtual_gateway_id String Yes       Specifies the virtual gateway ID.
   ================== ====== ========= =================================

.. _en-us_topic_0055025326__section36252627:

Request
-------

:ref:`Table 2 <en-us_topic_0055025326__table50992744154526>` lists the request parameter.

.. _en-us_topic_0055025326__table50992744154526:

.. table:: **Table 2** Request parameter

   +-----------------+------------+-----------+-------------------------------------------+
   | Parameter       | Type       | Mandatory | Description                               |
   +=================+============+===========+===========================================+
   | virtual_gateway | Dictionary | Yes       | Specifies the **virtual_gateway** object. |
   +-----------------+------------+-----------+-------------------------------------------+

+-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------+
| Parameter         | Type            | Mandatory       | Description                                                                               |
+===================+=================+=================+===========================================================================================+
| description       | String          | No              | Provides supplementary information about the virtual gateway.                             |
|                   |                 |                 |                                                                                           |
|                   |                 |                 | Angle brackets (<>) are not allowed.                                                      |
+-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------+
| name              | String          | No              | Specifies the virtual gateway name.                                                       |
|                   |                 |                 |                                                                                           |
|                   |                 |                 | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed.          |
+-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------+
| local_ep_group_id | String          | No              | Specifies the ID of the local endpoint group that records CIDR blocks of the VPC subnets. |
+-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------+

.. _en-us_topic_0055025326__section57838187:

Response
--------

:ref:`Table 3 <en-us_topic_0055025326__table4284712915501>` lists the response parameter.

.. _en-us_topic_0055025326__table4284712915501:

.. table:: **Table 3** Response parameter

   =============== ========== =========================================
   Parameter       Type       Description
   =============== ========== =========================================
   virtual_gateway Dictionary Specifies the **virtual_gateway** object.
   =============== ========== =========================================

For details about the **virtual_gateway** field, see :ref:`Table 1 <en-us_topic_0055025321__en-us_topic_0070676570_table49902238182444>`.

.. _en-us_topic_0055025326__section5055526711495:

Examples
--------

-  Example request

   .. code-block:: text

      PUT /v2.0/dcaas/virtual-gateways/{virtual_gateway_id}
      {
          "virtual_gateway" : {
              "name" : "virtual gateway1",
              "description" : "New description"
          }
      }

-  Example response

   .. code-block::

      {
           "virtual_gateway" : {
                  "id": "0a0888a6-4096-43a6-81c6-923912933451",
                  "name": "virtual gateway1",
                  "description": "New description",
                  "tenant_id": "0605768a3300d5762f82c01180692873",
                  "vpc_id": "5352423b-b4ff-4a9e-839d-02698c2b36af",
                  "local_ep_group_id": "f8834cf1-5468-87c7-223d-56e78b9699ab",
                  "local_ep_group_ipv6_id": null,
                  "device_id": "aaa_01",
                  "redundant_device_id": null,
                  "type": "default",
                  "ipsec_bandwidth": 1,
                  "status": "PENDING_CREATE",
                  "admin_state_up": true,
                  "bgp_asn": null,
                  "region_id": null
          }
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
