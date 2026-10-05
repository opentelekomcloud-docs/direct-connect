:original_name: en-us_topic_0055025329.html

.. _en-us_topic_0055025329:

Creating a Virtual Interface
============================

Function
--------

This API is used to create a virtual interface.

URI
---

POST /v2.0/dcaas/virtual-interfaces

.. _en-us_topic_0055025329__section31485239:

Request
-------

:ref:`Table 1 <en-us_topic_0055025329__table10476506155243>` lists the request parameter.

.. _en-us_topic_0055025329__table10476506155243:

.. table:: **Table 1** Request parameter

   +-------------------+------------+-----------+---------------------------------------------+
   | Parameter         | Type       | Mandatory | Description                                 |
   +===================+============+===========+=============================================+
   | virtual_interface | Dictionary | Yes       | Specifies the **virtual_interface** object. |
   +-------------------+------------+-----------+---------------------------------------------+

.. _en-us_topic_0055025329__table26517876:

.. table:: **Table 2** Description of field **virtual_interface**

   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | Parameter            | Type            | Mandatory       | Description                                                                                                 |
   +======================+=================+=================+=============================================================================================================+
   | tenant_id            | String          | No              | Specifies the project ID.                                                                                   |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | name                 | String          | No              | Specifies the virtual interface name.                                                                       |
   |                      |                 |                 |                                                                                                             |
   |                      |                 |                 | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed.                            |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | description          | String          | No              | Provides supplementary information about the virtual interface.                                             |
   |                      |                 |                 |                                                                                                             |
   |                      |                 |                 | Angle brackets (<>) are not allowed.                                                                        |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | direct_connect_id    | String          | Yes             | Specifies the connection ID.                                                                                |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | vgw_id               | String          | Yes             | Specifies the virtual gateway ID.                                                                           |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | type                 | String          | Yes             | Specifies the virtual interface type. The value can only be **private**.                                    |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | service_type         | String          | Yes             | Specifies what is to be accessed over the connection. The value can only be **vpc**.                        |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | vlan                 | Integer         | Yes             | Specifies the VLAN used by the local gateway to communicate with the remote gateway.                        |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | bandwidth            | Integer         | Yes             | Specifies the virtual interface bandwidth.                                                                  |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | local_gateway_v4_ip  | String          | Yes             | Specifies the IPv4 address of the local gateway.                                                            |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | remote_gateway_v4_ip | String          | Yes             | Specifies the IPv4 address of the remote gateway.                                                           |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | route_mode           | String          | Yes             | Specifies the routing mode. The value can be **static** or **bgp**.                                         |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | bgp_asn              | Integer         | No              | Specifies the AS number of the BGP peer.                                                                    |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | bgp_md5              | String          | No              | Specifies the MD5 password of the BGP peer.                                                                 |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | remote_ep_group_id   | String          | Yes             | Specifies the ID of the remote endpoint group that records the CIDR blocks used by the on-premises network. |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+
   | admin_state_up       | Boolean         | No              | Specifies the administrative status of the virtual interface.                                               |
   |                      |                 |                 |                                                                                                             |
   |                      |                 |                 | The value can be **true** or **false**.                                                                     |
   +----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0055025329__section14931696:

Response
--------

:ref:`Table 3 <en-us_topic_0055025329__table15831690155351>` lists the response parameter.

.. _en-us_topic_0055025329__table15831690155351:

.. table:: **Table 3** Response parameter

   ================= ========== ===========================================
   Parameter         Type       Description
   ================= ========== ===========================================
   virtual_interface Dictionary Specifies the **virtual_interface** object.
   ================= ========== ===========================================

For details about the **virtual_interface** field, see :ref:`Table 1 <en-us_topic_0055025328__en-us_topic_0070658680_table1529059104553>`.

.. _en-us_topic_0055025329__section38241653113834:

Examples
--------

-  Example request

   .. code-block:: text

      POST /v2.0/dcaas/virtual-interfaces
      {
          "virtual_interface" : {
              "name" : "virtual interface1",
              "direct_connect_id" : "6ecd9cf3-ca64-46c7-863f-f2eb1b9e838a",
              "vgw_id" : "7ec892f3-ca64-46c7-863f-a2eb1b9e8389",
              "type" : "private",
              "service_type" : "vpc",
              "vlan" : 100,
              "bandwidth" : 10,
              "local_gateway_v4_ip" : "180.1.1.1/24",
              "remote_gateway_v4_ip"  : "180.1.1.2/24",
              "route_mode"  : "static",
              "remote_ep_group_id" : "78e34cf1-5468-87c7-223d-56e78b9699ef"
          }
      }

-  Example response

   .. code-block::

      {
          "virtual_interface" : {
              "id": "634c61d0-fd7b-4961-adb6-37a2e3c42d08",
              "name": "test-vif",
              "description": null,
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
              "status": "PENDING_CREATE",
              "create_time": "2021-12-15T00:31:27Z",
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
