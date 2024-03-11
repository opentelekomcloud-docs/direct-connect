:original_name: ShowVirtualGateway.html

.. _ShowVirtualGateway:

Querying Details About a Virtual Gateway
========================================

Function
--------

This API is used to query details about a specified virtual gateway.

URI
---

GET /v3/{project_id}/dcaas/virtual-gateways/{virtual_gateway_id}

.. table:: **Table 1** Path Parameters

   ================== ========= ====== =================================
   Parameter          Mandatory Type   Description
   ================== ========= ====== =================================
   project_id         Yes       String Specifies the project ID.
   virtual_gateway_id Yes       String Specifies the virtual gateway ID.
   ================== ========= ====== =================================

.. table:: **Table 2** Query Parameters

   +-----------------+-----------------+-----------------+-----------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                   |
   +=================+=================+=================+===============================================+
   | fields          | No              | Array           | Specifies the list of fields to be displayed. |
   |                 |                 |                 |                                               |
   |                 |                 |                 | Array Length: **1 - 5**                       |
   +-----------------+-----------------+-----------------+-----------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                        |
   +=================+=================+=================+====================================================================================================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | Specifies the user token. To obtain the token, see section "Obtaining the User Token" in the *Identity and Access Management API Reference*. The token is the value of **X-Subject-Token** in the response header. |
   |                 |                 |                 |                                                                                                                                                                                                                    |
   |                 |                 |                 | Minimum: **0**                                                                                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                                                                                    |
   |                 |                 |                 | Maximum: **10240**                                                                                                                                                                                                 |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------------+---------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | Parameter       | Type                                                                                                    | Description                                          |
   +=================+=========================================================================================================+======================================================+
   | virtual_gateway | :ref:`VirtualGateway <showvirtualgateway__en-us_topic_0000001782745845_response_virtualgateway>` object | Specifies parameters for creating a virtual gateway. |
   +-----------------+---------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | request_id      | String                                                                                                  | Specifies the request ID.                            |
   +-----------------+---------------------------------------------------------------------------------------------------------+------------------------------------------------------+

.. _showvirtualgateway__en-us_topic_0000001782745845_response_virtualgateway:

.. table:: **Table 5** VirtualGateway

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                   |
   +=======================+=======================+===============================================================================================================================================================+
   | id                    | String                | Specifies the virtual gateway ID.                                                                                                                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vpc_id                | String                | Specifies the ID of the VPC connected by the virtual gateway.                                                                                                 |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_router_id  | String                | Specifies the ID of the enterprise router that the virtual gateway is attached to.                                                                            |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the ID of the project that the instance belongs to.                                                                                                 |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Minimum: **32**                                                                                                                                               |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Maximum: **32**                                                                                                                                               |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                | Specifies the virtual gateway name.                                                                                                                           |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Minimum: **0**                                                                                                                                                |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Maximum: **64**                                                                                                                                               |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the virtual gateway.                                                                                                 |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Minimum: **0**                                                                                                                                                |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Maximum: **128**                                                                                                                                              |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | type                  | String                | Specifies the virtual gateway type. The value can only be **default**.                                                                                        |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Default: **default**                                                                                                                                          |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | local_ep_group        | Array of strings      | Specifies the IPv4 subnets connected by the virtual gateway, which is usually the CIDR blocks of a VPC.                                                       |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | local_ep_group_ipv6   | Array of strings      | Specifies the IPv6 subnets connected by the virtual gateway, which is usually the CIDR blocks of a VPC. This is a reserved field.                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | Specifies the administrative status, which can be **true** or **false**.                                                                                      |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Default: **true**                                                                                                                                             |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Specifies the virtual gateway status, which can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_CREATE**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | bgp_asn               | Integer               | Specifies the local BGP ASN of the virtual gateway.                                                                                                           |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Minimum: **1**                                                                                                                                                |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Maximum: **4294967295**                                                                                                                                       |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | String                | Specifies the ID of the enterprise project that the virtual gateway belongs to.                                                                               |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Minimum: **36**                                                                                                                                               |
   |                       |                       |                                                                                                                                                               |
   |                       |                       | Maximum: **36**                                                                                                                                               |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | device_id             | String                | Specifies the ID of the device that the virtual interface belongs to.                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | redundant_device_id   | String                | Specifies the ID of the redundant device.                                                                                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | public_border_group   | String                | Specifies the public border group of the AZ, indicating whether the site is a HomeZones site.                                                                 |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Querying a virtual gateway

.. code-block:: text

   GET https://{dc_endpoint}/v3/0605768a3300d5762f82c01180692873/dcaas/virtual-gateways/20082c1b-3c99-48d8-8e8c-116af5d7e9f0

Example Responses
-----------------

**Status code: 200**

OK

-  The details of the virtual gateway associated with a VPC are queried.

   .. code-block::

      {
        "virtual_gateway" : {
          "id" : "20082c1b-3c99-48d8-8e8c-116af5d7e9f0",
          "name" : "vgw-c7b22",
          "description" : "",
          "tenant_id" : "0605768a3300d5762f82c01180692873",
          "vpc_id" : "6592c28e-95d7-4b0a-9f61-004fdf03420c",
          "device_id" : "26.151.63.100",
          "redundant_device_id" : "26.152.128.20",
          "type" : "default",
          "status" : "ACTIVE",
          "admin_state_up" : true,
          "bgp_asn" : 64512,
          "local_ep_group" : [ "192.168.1.0/24" ],
          "enterprise_project_id" : "0",
          "public_border_group" : "center"
        },
        "request_id" : "765f7aaf8f2edd0e719de564ef72e2de"
      }

-  The details of the virtual gateway attached to an enterprise router are queried.

   .. code-block::

      {
        "virtual_gateway" : {
          "name" : "vgw-er",
          "id" : "7a91797a-cbda-42ff-9f42-73f26c993dd9",
          "description" : "",
          "tenant_id" : "92ea72fe26294aa180a2712c28e43c21",
          "vpc_id" : null,
          "enterprise_router_id" : "61fa53c9-4446-4ebd-89b9-11a52b653a9c",
          "device_id" : "26.151.63.100",
          "redundant_device_id" : "26.152.128.20",
          "type" : "default",
          "status" : "ACTIVE",
          "admin_state_up" : true,
          "bgp_asn" : 64512,
          "local_ep_group" : null,
          "local_ep_group_ipv6" : null,
          "public_border_group" : null
        },
        "request_id" : "765f7aaf8f2edd0e719de564e8765fg4"
      }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
