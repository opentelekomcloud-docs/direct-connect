:original_name: en-dc_topic_0055025330.html

.. _en-dc_topic_0055025330:

Querying the Virtual Interface List
===================================

Function
--------

This API is used to query the virtual interface list.

URI
---

GET /v2.0/dcaas/virtual-interfaces

.. _en-dc_topic_0055025330__section64582388:

Request
-------

:ref:`Table 1 <en-dc_topic_0055025330__table2198437322244>` lists the request parameter.

.. _en-dc_topic_0055025330__table2198437322244:

.. table:: **Table 1** Request parameter

   +-----------------+-----------------+-----------------+------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                |
   +=================+=================+=================+============================================================+
   | fields          | String          | No              | Specifies the parameters expected to be returned.          |
   |                 |                 |                 |                                                            |
   |                 |                 |                 | If you do not specify it, all parameters will be returned. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------+

.. _en-dc_topic_0055025330__section44370581:

Response
--------

:ref:`Table 2 <en-dc_topic_0055025330__table10476506155243>` lists the response parameter.

.. _en-dc_topic_0055025330__table10476506155243:

.. table:: **Table 2** Response parameter

   ================== ==== =====================================
   Parameter          Type Description
   ================== ==== =====================================
   virtual_interfaces List Specifies the virtual interface list.
   ================== ==== =====================================

For details about the **virtual_interfaces** field, see :ref:`Table 1 <en-dc_topic_0055025328__en-us_topic_0070658680_table1529059104553>`.

.. _en-dc_topic_0055025330__section63790914:

Examples
--------

-  Example request

   #. Querying all virtual interfaces

   .. code-block:: text

      GET /v2.0/dcaas/virtual-interfaces

   2. Querying a virtual interface by ID

   .. code-block:: text

      GET /v2.0/dcaas/virtual-interfaces?id=67c59cf4-1a64-46c7-763f-22eb1b9e8986

-  Example response

   .. code-block::

      {
          "virtual_interfaces" : [{
                  "id": "026895e2-23bf-44bd-8ef1-93618ab92b99",
                  "name": "vif-test",
                  "description": null,
                  "tenant_id": "06057679cc80d5762fb2c01e71b5a593",
                  "direct_connect_id": "b07d42dc-6137-4af3-a93b-853d879ae268",
                  "vgw_id": "d27d5bd2-97b3-4bd8-b7e5-189a71c14846",
                  "type": "private",
                  "service_type": "vpc",
                  "vlan": 2202,
                  "bandwidth": 6,
                  "local_gateway_v4_ip": "16.16.16.1/30",
                  "remote_gateway_v4_ip": "16.16.16.2/30",
                  "route_mode": "static",
                  "bgp_asn": null,
                  "bgp_md5": null,
                  "remote_ep_group_id": "31dd8536-1ac7-4a38-b2fc-178a69f11b11",
                  "service_ep_group_id": null,
                  "status": "ACTIVE",
                  "create_time": "2021-12-15T06:55:46Z",
                  "admin_state_up": true,
                  "rate_limit": false,
                  "enable_bfd": false,
                  "health_check_source_ip": null,
                  "route_limit": 50,
                  "address_family": "ipv4",
                  "local_gateway_v6_ip": null,
                  "remote_gateway_v6_ip": null,
                  "region_id": null,
                  "enable_nqa": false,
                  "enable_gre": false,
                  "local_gre_tunnel_ip": null,
                  "remote_gre_tunnel_ip": null,
                  "lag_id": null
              }]
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-dc_topic_0055025342>`.
