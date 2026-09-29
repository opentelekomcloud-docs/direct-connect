:original_name: en-us_topic_0055025333.html

.. _en-us_topic_0055025333:

Updating a Virtual Interface
============================

.. _en-us_topic_0055025333__section20784174143924:

Function
--------

This API is used to update a virtual interface.

.. note::

   The bandwidth specified for a virtual interface associated with a standard connection can be increased or decreased, but the bandwidth specified for a virtual interface associated with a hosted connection cannot be changed.

URI
---

PUT /v2.0/dcaas/virtual-interfaces/{virtual_interface_id}

.. table:: **Table 1** Parameter description

   +----------------------+--------+-----------+-------------------------------------+
   | Parameter            | Type   | Mandatory | Description                         |
   +======================+========+===========+=====================================+
   | virtual_interface_id | String | Yes       | Specifies the virtual interface ID. |
   +----------------------+--------+-----------+-------------------------------------+

.. _en-us_topic_0055025333__section17286486143924:

Request
-------

:ref:`Table 2 <en-us_topic_0055025333__table10476506155243>` lists the request parameter.

.. _en-us_topic_0055025333__table10476506155243:

.. table:: **Table 2** Request parameter

   +-------------------+------------+-----------+---------------------------------------------+
   | Parameter         | Type       | Mandatory | Description                                 |
   +===================+============+===========+=============================================+
   | virtual_interface | Dictionary | Yes       | Specifies the **virtual_interface** object. |
   +-------------------+------------+-----------+---------------------------------------------+

.. table:: **Table 3** Description of field **virtual_interface**

   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | Parameter            | Type            | Mandatory       | Description                                                                                                 |
   +======================+=================+=================+=============================================================================================================+
   | virtual_interface_id | String          | Yes             | Specifies the virtual interface ID.                                                                         |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | description          | String          | No              | Provides supplementary information about the virtual interface.                                             |
   |                      |                 |                 |                                                                                                             |
   |                      |                 |                 | Angle brackets (<>) are not allowed.                                                                        |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | name                 | String          | No              | Specifies the virtual interface name.                                                                       |
   |                      |                 |                 |                                                                                                             |
   |                      |                 |                 | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed.                            |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | bandwidth            | Integer         | No              | Specifies the virtual interface bandwidth.                                                                  |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | remote_ep_group_id   | String          | No              | Specifies the ID of the remote endpoint group that records the CIDR blocks used by the on-premises network. |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0055025333__section33278910143924:

Response
--------

:ref:`Table 4 <en-us_topic_0055025333__table2216502815556>` lists the response parameter.

.. _en-us_topic_0055025333__table2216502815556:

.. table:: **Table 4** Response parameter

   ================= ========== ===========================================
   Parameter         Type       Description
   ================= ========== ===========================================
   virtual_interface Dictionary Specifies the **virtual_interface** object.
   ================= ========== ===========================================

For details about the **virtual_interface** field, see :ref:`Table 1 <en-us_topic_0055025328__en-us_topic_0070658680_table1529059104553>`.

.. _en-us_topic_0055025333__section9931099143924:

Examples
--------

-  Example request

   .. code-block:: text

      PUT /v2.0/dcaas/virtual-interfaces/{virtual_interface_id}
      {
          "virtual_interface" : {
              "name" : "virtual interface1",
              "description" : "New description"
          }
      }

-  Example response

   .. code-block::

      {
          "virtual_interface" : {
              "id": "634c61d0-fd7b-4961-adb6-37a2e3c42d08",
              "name": "virtual-interface1",
              "description": "New description",
              "tenant_id": "06057682ed80d5762f25c00b5deb794a",
              "direct_connect_id": "73707953-df69-4d03-8df5-b46a087c1424",
              "vgw_id": "9b5cab66-7634-4213-8d01-fa37cb908e12",
              "type": "private",
              "service_type": "vpc",
              "vlan": 687,
              "bandwidth": 2,
              "local_gateway_v4_ip": "11.11.11.1/30",
              "remote_gateway_v4_ip": "11.11.11.2/30",
              "route_mode": "static",
              "bgp_asn": null,
              "bgp_md5": null,
              "remote_ep_group_id": "a2b81f07-826f-40b0-9e8d-17d1af5230cf",
              "service_ep_group_id": null,
              "status": "ACTIVE",
              "create_time": "2021-12-15T08:31:27Z",
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
          }
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
