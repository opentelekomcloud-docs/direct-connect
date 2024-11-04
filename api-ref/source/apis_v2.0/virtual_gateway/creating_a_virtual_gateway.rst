:original_name: en-us_topic_0055025322.html

.. _en-us_topic_0055025322:

Creating a Virtual Gateway
==========================

Function
--------

This API is used to create a virtual gateway.

URI
---

POST /v2.0/dcaas/virtual-gateways

.. table:: **Table 1** Parameter description

   +-----------------+------------+-----------+-------------------------------------------+
   | Parameter       | Type       | Mandatory | Description                               |
   +=================+============+===========+===========================================+
   | virtual_gateway | Dictionary | Yes       | Specifies the **virtual_gateway** object. |
   +-----------------+------------+-----------+-------------------------------------------+

.. _en-us_topic_0055025322__section2281784192910:

Request
-------

For details about the **virtual_gateway** field, see :ref:`Table 2 <en-us_topic_0055025322__table3523051192910>`.

.. _en-us_topic_0055025322__table3523051192910:

.. table:: **Table 2** Request parameters

   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | Parameter           | Type            | Mandatory       | Description                                                                                                     |
   +=====================+=================+=================+=================================================================================================================+
   | tenant_id           | String          | No              | Specifies the project ID.                                                                                       |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | name                | String          | No              | Specifies the virtual gateway name.                                                                             |
   |                     |                 |                 |                                                                                                                 |
   |                     |                 |                 | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed.                                |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | description         | String          | No              | Provides supplementary information about the virtual gateway.                                                   |
   |                     |                 |                 |                                                                                                                 |
   |                     |                 |                 | Angle brackets (<>) are not allowed.                                                                            |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | vpc_id              | String          | Yes             | Specifies the ID of the VPC to be accessed.                                                                     |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | local_ep_group_id   | String          | Yes             | Specifies the ID of the local endpoint group that records CIDR blocks of the VPC subnets.                       |
   |                     |                 |                 |                                                                                                                 |
   |                     |                 |                 | For details about how to obtain the ID, see section :ref:`Creating an Endpoint Group <en-us_topic_0055025336>`. |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | bgp_asn             | Integer         | No              | Specifies the BGP ASN of the virtual gateway.                                                                   |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | device_id           | String          | No              | Specifies the ID of the physical device used by the virtual gateway.                                            |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | redundant_device_id | String          | No              | Specifies the ID of the redundant physical device used by the virtual gateway.                                  |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | type                | String          | No              | Specifies the virtual gateway type. The value can only be **default**.                                          |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+
   | admin_state_up      | Boolean         | No              | Specifies the administrative status of the virtual gateway.                                                     |
   |                     |                 |                 |                                                                                                                 |
   |                     |                 |                 | The value can be **true** or **false**.                                                                         |
   +---------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0055025322__section1915447592910:

Response
--------

:ref:`Table 3 <en-us_topic_0055025322__table50992744154526>` lists the response parameter.

.. _en-us_topic_0055025322__table50992744154526:

.. table:: **Table 3** Response parameter

   =============== ========== =========================================
   Parameter       Type       Description
   =============== ========== =========================================
   virtual_gateway Dictionary Specifies the **virtual_gateway** object.
   =============== ========== =========================================

For details about the **virtual_gateway** field, see :ref:`Table 1 <en-us_topic_0055025321__en-us_topic_0070676570_table49902238182444>`.

.. _en-us_topic_0055025322__section5174176392910:

Examples
--------

-  Example request

   .. code-block:: text

      POST /v2.0/dcaas/virtual-gateways
       {
          "virtual_gateway" : {
              "name" : "virtual gateway1",
              "vpc_id" : "5352423b-b4ff-4a9e-839d-02698c2b36af ",
              "local_ep_group_id" : "f8834cf1-5468-87c7-223d-56e78b9699ab",
              "device_id" : "aaa_01"
          }
      }

-  Example response

   .. code-block::

      {
          "virtual_gateway":{
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
                  "bgp_asn": null,
                  "region_id": null
          }
      }

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
