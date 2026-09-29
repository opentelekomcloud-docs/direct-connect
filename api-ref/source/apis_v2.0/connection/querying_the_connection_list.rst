:original_name: en-us_topic_0055025316.html

.. _en-us_topic_0055025316:

Querying the Connection List
============================

Function
--------

This API is used to query the connection list.

.. _en-us_topic_0055025316__section23166934:

URI
---

GET /v2.0/dcaas/direct-connects

.. table:: **Table 1** Parameter description

   =============== ==== ========= ==============================
   Parameter       Type Mandatory Description
   =============== ==== ========= ==============================
   direct_connects List Yes       Specifies the connection list.
   =============== ==== ========= ==============================

Request
-------

:ref:`Table 2 <en-us_topic_0055025316__table2198437322244>` lists the request parameter.

.. _en-us_topic_0055025316__table2198437322244:

.. table:: **Table 2** Request parameter

   +-----------------+-----------------+-----------------+------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                |
   +=================+=================+=================+============================================================+
   | fields          | String          | No              | Specifies the parameters expected to be returned.          |
   |                 |                 |                 |                                                            |
   |                 |                 |                 | If you do not specify it, all parameters will be returned. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------+

.. _en-us_topic_0055025316__section44370581:

Response
--------

:ref:`Table 3 <en-us_topic_0055025316__table122627546489>` lists the response parameter.

.. _en-us_topic_0055025316__table122627546489:

.. table:: **Table 3** Response parameter

   =============== ==== ==============================
   Parameter       Type Description
   =============== ==== ==============================
   direct_connects List Specifies the connection list.
   =============== ==== ==============================

For details about the **direct_connects** field, see :ref:`Table 1 <en-us_topic_0055025314__en-us_topic_0070676569_table49902238182444>`.

.. _en-us_topic_0055025316__section63790914:

Examples
--------

-  Example request

   #. Querying all connections

   .. code-block:: text

      GET /v2.0/dcaas/direct-connects

   2. Querying a connection using its ID

   .. code-block:: text

      GET /v2.0/dcaas/direct-connects?id=6ecd9cf3-ca64-46c7-863f-f2eb1b9e838a

-  .. _en-us_topic_0055025316__li14754114114217:

   Example response

   .. code-block::

      {
              "direct_connects" : [{
              "name": "direct connect",
              "id": "294ebeeb-62dd-4ece-99f5-73055df6d835",
              "description": "",
              "tenant_id": "0605768ad980d5762f8ac010b919754c",
              "type": "hosted",
              "hosting_id": "0e85c677-6eb5-4ef6-87a7-74d4586be895",
              "vlan": 228,
              "charge_mode": null,
              "port_type": "1G",
              "bandwidth": 2,
              "location": "Biere",
              "peer_location": "",
              "device_id": "18.8.215.131",
              "interface_name": "Eth-Trunk2",
              "redundant_id": null,
              "provider": "OTC",
              "provider_status": "ACTIVE",
              "status": "ACTIVE",
              "apply_time": "2022-12-08T01:59:36.000Z",
              "reason": null,
              "admin_state_up": true,
              "order_id": null,
              "product_id": null,
              "spec_code": null,
              "applicant": null,
              "mobile": null,
              "email": null,
              "create_time": "2022-12-08T01:59:36.000Z",
              "region_id": null,
              "service_key": null,
              "cable_label": null,
              "peer_port_type": null,
              "peer_provider": null,
              "onestop_product_id": null,
              "building_line_product_id": null,
              "last_onestop_product_id": null,
              "period_type": null,
              "period_num": null,
              "vgw_type": "default",
              "lag_id": null
          }]
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
