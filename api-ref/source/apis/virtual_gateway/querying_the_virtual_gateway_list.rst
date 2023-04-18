:original_name: en-dc_topic_0055025323.html

.. _en-dc_topic_0055025323:

Querying the Virtual Gateway List
=================================

Function
--------

This API is used to query the virtual gateway list.

URI
---

GET /v2.0/dcaas/virtual-gateways

Request
-------

:ref:`Table 1 <en-dc_topic_0055025323__table2198437322244>` lists the request parameter.

.. _en-dc_topic_0055025323__table2198437322244:

.. table:: **Table 1** Request parameter

   +-----------------+-----------------+-----------------+------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                |
   +=================+=================+=================+============================================================+
   | fields          | String          | No              | Specifies the parameters expected to be returned.          |
   |                 |                 |                 |                                                            |
   |                 |                 |                 | If you do not specify it, all parameters will be returned. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------+

.. _en-dc_topic_0055025323__section44370581:

Response
--------

:ref:`Table 2 <en-dc_topic_0055025323__table50992744154526>` lists the response parameter.

.. _en-dc_topic_0055025323__table50992744154526:

.. table:: **Table 2** Response parameter

   ================ ==== ===================================
   Parameter        Type Description
   ================ ==== ===================================
   virtual_gateways List Specifies the virtual gateway list.
   ================ ==== ===================================

For details about the **virtual_gateway** field, see :ref:`Table 1 <en-dc_topic_0055025321__en-us_topic_0070676570_table49902238182444>`.

.. _en-dc_topic_0055025323__section63790914:

Examples
--------

-  Example request

   #. Querying all virtual gateways

   .. code-block:: text

      GET /v2.0/dcaas/virtual-gateways

   2. Querying a virtual gateway by ID

   .. code-block:: text

      GET /v2.0/dcaas/virtual-gateways?id=7ec892f3-ca64-46c7-863f-a2eb1b9e8389

-  Example response

   .. code-block::

      {
          "virtual_gateways" : [{
                  "id": "0a0888a6-4096-43a6-81c6-923912933451",
                  "name": "virtual gateway",
                  "description": null,
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
                  "bgp_asn": 64512,
                  "region_id": null
          }]
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-dc_topic_0055025342>`.
