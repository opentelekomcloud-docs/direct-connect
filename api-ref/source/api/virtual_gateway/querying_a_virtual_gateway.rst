:original_name: en-dc_topic_0055025325.html

.. _en-dc_topic_0055025325:

Querying a Virtual Gateway
==========================

Function
--------

This API is used to query a virtual gateway.

URI
---

GET /v2.0/dcaas/virtual-gateways/{virtual_gateway_id}

.. table:: **Table 1** Parameter description

   ================== ====== ========= =================================
   Parameter          Type   Mandatory Description
   ================== ====== ========= =================================
   virtual_gateway_id String Yes       Specifies the virtual gateway ID.
   ================== ====== ========= =================================

Request
-------

:ref:`Table 2 <en-dc_topic_0055025325__table2198437322244>` lists the request parameter.

.. _en-dc_topic_0055025325__table2198437322244:

.. table:: **Table 2** Request parameter

   ================== ====== ========= =================================
   Parameter          Type   Mandatory Description
   ================== ====== ========= =================================
   virtual_gateway_id String Yes       Specifies the virtual gateway ID.
   ================== ====== ========= =================================

Response
--------

:ref:`Table 3 <en-dc_topic_0055025325__table50992744154526>` lists the response parameter.

.. _en-dc_topic_0055025325__table50992744154526:

.. table:: **Table 3** Response parameter

   +-----------------+---------------------------+-----------+-------------------------------------------+
   | Parameter       | Type                      | Mandatory | Description                               |
   +=================+===========================+===========+===========================================+
   | virtual_gateway | Dictionary data structure | Yes       | Specifies the **virtual_gateway** object. |
   +-----------------+---------------------------+-----------+-------------------------------------------+

.. table:: **Table 4** Description of field **virtual_gateway**

   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Type            | Mandatory       | Description                                                                                                                 |
   +=====================+=================+=================+=============================================================================================================================+
   | id                  | String          | Yes             | Specifies the virtual gateway ID.                                                                                           |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | tenant_id           | String          | Yes             | Specifies the project ID.                                                                                                   |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | name                | String          | No              | Specifies the virtual gateway name.                                                                                         |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | description         | String          | No              | Provides supplementary information about the virtual gateway.                                                               |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | vpc_id              | String          | Yes             | Specifies the ID of the VPC to be accessed.                                                                                 |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | local_ep_group_id   | String          | Yes             | Specifies the ID of the local endpoint group that records CIDR blocks of the VPC subnets.                                   |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | device_id           | String          | No              | Specifies the ID of the physical device used by the virtual gateway.                                                        |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | redundant_device_id | String          | No              | Specifies the ID of the redundant physical device used by the virtual gateway.                                              |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | type                | String          | No              | Specifies the virtual gateway type. The value can be **default** or **double ipsec**.                                       |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | ipsec_bandwidth     | Integer         | No              | Specifies the bandwidth provided for IPsec VPN in Mbit/s.                                                                   |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | bgp_asn             | Integer         | No              | Specifies the BGP ASN of the virtual gateway.                                                                               |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | status              | String          | No              | Specifies the virtual gateway status.                                                                                       |
   |                     |                 |                 |                                                                                                                             |
   |                     |                 |                 | The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_CREATE**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up      | Boolean         | No              | Specifies the administrative status of the virtual gateway.                                                                 |
   |                     |                 |                 |                                                                                                                             |
   |                     |                 |                 | The value can be **true** or **false**.                                                                                     |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET /v2.0/dcaas/virtual-gateways/{virtual_gateway_id}

-  Example response

   .. code-block::

      {
          "virtual_gateway" : {
              "id" : "7ec892f3-ca64-46c7-863f-a2eb1b9e8389",
              "tenant_id" : "6fbe9263116a4b68818cf1edce16bc4f",
              "name" : "virtual gateway1",
              "description" : "",
              "vpc_id" : "908d9cf3-da64-4acb-393f-e5eb6b9e838a",
              "local_ep_group_id" : "f8834cf1-5468-87c7-223d-56e78b9699ab",
              "device_id" : "aaa_01"
          }
      }

Returned Value
--------------

For details, see section :ref:`Common Returned Values <en-dc_topic_0055025342>`.
