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

Response
--------

:ref:`Table 2 <en-dc_topic_0055025323__table50992744154526>` lists the response parameter.

.. _en-dc_topic_0055025323__table50992744154526:

.. table:: **Table 2** Response parameter

   ================ =================== ===================================
   Parameter        Type                Description
   ================ =================== ===================================
   virtual_gateways List data structure Specifies the virtual gateway list.
   ================ =================== ===================================

.. table:: **Table 3** Description of field **virtual_gateways**

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                 |
   +=======================+=======================+=============================================================================================================================+
   | id                    | String                | Specifies the virtual gateway ID.                                                                                           |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                | Specifies the virtual gateway name.                                                                                         |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the virtual gateway.                                                               |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | vpc_id                | String                | Specifies the ID of the VPC to be accessed.                                                                                 |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | local_ep_group_id     | String                | Specifies the ID of the local endpoint group that records CIDR blocks of the VPC subnets.                                   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | device_id             | String                | Specifies the ID of the physical device used by the virtual gateway.                                                        |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | redundant_device_id   | String                | Specifies the ID of the redundant physical device used by the virtual gateway.                                              |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | type                  | String                | Specifies the virtual gateway type. The value can be **default** or **double ipsec**.                                       |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | bgp_asn               | Integer               | Specifies the BGP ASN of the virtual gateway.                                                                               |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | ipsec_bandwidth       | Integer               | Specifies the bandwidth provided for IPsec VPN in Mbit/s.                                                                   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Specifies the virtual gateway status.                                                                                       |
   |                       |                       |                                                                                                                             |
   |                       |                       | The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_CREATE**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | Specifies the administrative status of the virtual gateway.                                                                 |
   |                       |                       |                                                                                                                             |
   |                       |                       | The value can be **true** or **false**.                                                                                     |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   #. All parameters are returned:

   .. code-block:: text

      GET /v2.0/dcaas/virtual-gateways

   2. Filtered parameters are returned (for example, the filter is ID):

   .. code-block:: text

      GET /v2.0/dcaas/virtual-gateways?id=7ec892f3-ca64-46c7-863f-a2eb1b9e8389

-  Example response

   .. code-block::

      {
          "virtual_gateways" : [{
              "id" : "7ec892f3-ca64-46c7-863f-a2eb1b9e8389",
              "tenant_id" : "6fbe9263116a4b68818cf1edce16bc4f",
              "name" : "virtual gateway1",
              "description" : "",
              "vpc_id" : "908d9cf3-da64-4acb-393f-e5eb6b9e838a",
              "local_ep_group_id" : "f8834cf1-5468-87c7-223d-56e78b9699ab",
              "device_id" : "aaa_01"
          }]
      }

Returned Value
--------------

For details, see section :ref:`Common Returned Values <en-dc_topic_0055025342>`.
