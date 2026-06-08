:original_name: en-us_topic_0055025315.html

.. _en-us_topic_0055025315:

Creating a Connection
=====================

Function
--------

This API is used to create a hosted connection.

.. note::

   This API can only be used to create hosted connections.

URI
---

POST /v2.0/dcaas/direct-connects

.. table:: **Table 1** Parameter description

   +----------------+------------+-----------+------------------------------------------+
   | Parameter      | Type       | Mandatory | Description                              |
   +================+============+===========+==========================================+
   | direct_connect | Dictionary | Yes       | Specifies the **direct_connect** object. |
   +----------------+------------+-----------+------------------------------------------+

Request
-------

For details about the **direct_connect** field, see :ref:`Table 2 <en-us_topic_0055025315__table26517876>`.

.. _en-us_topic_0055025315__table26517876:

.. table:: **Table 2** Request parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                                                                              |
   +=================+=================+=================+==========================================================================================================================================================================================+
   | tenant_id       | String          | No              | Specifies the project ID.                                                                                                                                                                |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name            | String          | No              | Specifies the connection name.                                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                                                          |
   |                 |                 |                 | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed.                                                                                                         |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description     | String          | No              | Provides supplementary information about the connection.                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                                                          |
   |                 |                 |                 | Angle brackets (<>) are not allowed.                                                                                                                                                     |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | port_type       | String          | Yes             | Specifies the type of the port used by the connection. The value can be **1G**, **10G**, **40G**, or **100G**.                                                                           |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | bandwidth       | Integer         | Yes             | Specifies the bandwidth of the connection in Mbit/s.                                                                                                                                     |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | location        | String          | Yes             | Specifies the connection access location.                                                                                                                                                |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | peer_location   | String          | No              | Specifies the physical location of the peer device accessed by the connection, specific to the street or data center name.                                                               |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | device_id       | String          | No              | Specifies the gateway device ID of the connection.                                                                                                                                       |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | interface_name  | String          | No              | Specifies the name of the interface accessed by the connection.                                                                                                                          |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | redundant_id    | String          | No              | Specifies the ID of the redundant connection using the same gateway.                                                                                                                     |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | provider        | String          | Yes             | Specifies the carrier who provides the leased line.                                                                                                                                      |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | provider_status | String          | No              | Specifies the status of the carrier's leased line.                                                                                                                                       |
   |                 |                 |                 |                                                                                                                                                                                          |
   |                 |                 |                 | The value can be **ACTIVE** or **DOWN**.                                                                                                                                                 |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | type            | String          | No              | Specifies the connection type. The value can only be **hosted**.                                                                                                                         |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | hosting_id      | String          | No              | Specifies the ID of the operations connection on which the hosted connection is created.                                                                                                 |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | charge_mode     | String          | No              | Specifies the billing mode. This parameter is not mandatory. The value can only be **port** for operations connections.                                                                  |
   |                 |                 |                 |                                                                                                                                                                                          |
   |                 |                 |                 | This parameter is not possible to be used for hosted connections.                                                                                                                        |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | order_id        | String          | No              | Specifies the order number of the connection.                                                                                                                                            |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | product_id      | String          | No              | Specifies the product ID corresponding to the connection's order.                                                                                                                        |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status          | String          | No              | Specifies the connection status.                                                                                                                                                         |
   |                 |                 |                 |                                                                                                                                                                                          |
   |                 |                 |                 | The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_DELETE**, **DELETED**, **APPLY**, **DENY**, **PENDING_PAY**, **PAID**, **ORDERING**, **ACCEPT,** or **REJECTED**. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up  | Boolean         | No              | Specifies the administrative status of the connection.                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                                          |
   |                 |                 |                 | The value can be **true** or **false**.                                                                                                                                                  |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

:ref:`Table 3 <en-us_topic_0055025315__table50787760154022>` lists the response parameter.

.. _en-us_topic_0055025315__table50787760154022:

.. table:: **Table 3** Response parameter

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

      POST /v2.0/dcaas/direct-connects
      {
          "direct_connect" : {
              "name": "client-dc-55df",
              "bandwidth": 2,
              "description": "",
              "type": "hosted",
              "vlan": "1234",
              "port_type": "1G",
              "location": "Biere",
              "provider": "OTC",
              "hosting_id": "07fa7f82-826f-4bf1-9a90-8364e53b91f4",
              "tenant_id": "06057682ed80d5762f25c00b5deb794a"
          }
      }

-  Example response

   .. code-block::

      {
          "direct_connect" : {
              "id" : "10a91e67-90e9-4b06-87c8-e762296fada1",
              "name" : "client-dc-65de",
              "description" : "",
              "tenant_id" : "06057682ed80d5762f25c00b5deb794a",
              "type" : "hosted",
              "hosting_id" : "07fa7f82-826f-4bf1-9a90-8364e53b91f4",
              "vlan" : 1234,
              "charge_mode" : null,
              "port_type" : "1G",
              "bandwidth" : 2,
              "location" : "Biere",
              "peer_location" : "",
              "device_id" : "18.8.215.131",
              "provider" : "OTC",
              "provider_status" : "ACTIVE",
              "status" : "BUILD",
              "apply_time" : "2023-02-12T23:46:26.000Z",
              "reason" : null,
              "admin_state_up" : true,
              "order_id" : null,
              "product_id" : null,
              "spec_code" : null,
              "create_time" : "2023-02-12T23:46:26.000Z",
              "peer_port_type" : null,
              "peer_provider" : null,
              "onestop_product_id" : null,
              "building_line_product_id" : null,
              "last_building_line_product_id" : null,
              "last_onestop_product_id" : null,
              "period_type" : null,
              "period_num" : null,
              "vgw_type" : "default",
              "lag_id" : null
          }
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
