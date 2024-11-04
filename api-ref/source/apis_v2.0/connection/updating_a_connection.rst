:original_name: en-us_topic_0055025319.html

.. _en-us_topic_0055025319:

Updating a Connection
=====================

.. _en-us_topic_0055025319__section10267951:

Function
--------

This API is used to update a connection.

URI
---

PUT /v2.0/dcaas/direct-connects/{direct_connect_id}

.. table:: **Table 1** Parameter description

   ================= ====== ========= ============================
   Parameter         Type   Mandatory Description
   ================= ====== ========= ============================
   direct_connect_id String No        Specifies the connection ID.
   ================= ====== ========= ============================

Request
-------

:ref:`Table 2 <en-us_topic_0055025319__table7364283175427>` lists the request parameter.

.. _en-us_topic_0055025319__table7364283175427:

.. table:: **Table 2** Request parameter

   +----------------+------------+-----------+------------------------------------------+
   | Parameter      | Type       | Mandatory | Description                              |
   +================+============+===========+==========================================+
   | direct_connect | Dictionary | No        | Specifies the **direct_connect** object. |
   +----------------+------------+-----------+------------------------------------------+

.. table:: **Table 3** Description of field **direct_connect**

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                      |
   +=================+=================+=================+==================================================================================+
   | description     | String          | No              | Provides supplementary information about the connection.                         |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | Angle brackets (<>) are not allowed.                                             |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | name            | String          | No              | Specifies the connection name.                                                   |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | bandwidth       | Integer         | No              | Specifies the bandwidth of the connection in Mbit/s.                             |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | provider_status | String          | No              | Specifies the status of the carrier's leased line.                               |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | The value can be **ACTIVE** or **DOWN**.                                         |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+

.. _en-us_topic_0055025319__section57838187:

Response
--------

:ref:`Table 4 <en-us_topic_0055025319__table49073182143140>` lists the response parameter.

.. _en-us_topic_0055025319__table49073182143140:

.. table:: **Table 4** Response parameter

   ============== ========== ========================================
   Parameter      Type       Description
   ============== ========== ========================================
   direct_connect Dictionary Specifies the **direct_connect** object.
   ============== ========== ========================================

For details about the **direct_connect** field, see :ref:`Table 1 <en-us_topic_0055025314__en-us_topic_0070676569_table49902238182444>`.

Examples
--------

-  Example request

   .. code-block:: text

      PUT /v2.0/dcaas/direct-connects/{direct_connect_id}
      {
          "direct_connect" : {
              "name" : "direct connect1",
              "description" : "New description"
          }
      }

-  .. _en-us_topic_0055025319__li19940216124110:

   Example response

   .. code-block::

      {
              "direct_connects" : {
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
          }
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
