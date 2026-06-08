:original_name: CreateHostedDirectConnect.html

.. _CreateHostedDirectConnect:

Creating a Hosted Connection
============================

Function
--------

This API is used by partners to create hosted connections for their users. The creator must have the partner qualification and have an operations connection.

URI
---

POST /v3/{project_id}/dcaas/hosted-connects

.. table:: **Table 1** Path Parameters

   ========== ========= ====== =========================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =========================
   project_id Yes       String Specifies the project ID.
   ========== ========= ====== =========================

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                        |
   +=================+=================+=================+====================================================================================================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | Specifies the user token. To obtain the token, see section "Obtaining the User Token" in the *Identity and Access Management API Reference*. The token is the value of **X-Subject-Token** in the response header. |
   |                 |                 |                 |                                                                                                                                                                                                                    |
   |                 |                 |                 | Minimum: **0**                                                                                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                                                                                    |
   |                 |                 |                 | Maximum: **10240**                                                                                                                                                                                                 |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   +----------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------+
   | Parameter      | Mandatory | Type                                                                                                                                | Description                                                |
   +================+===========+=====================================================================================================================================+============================================================+
   | hosted_connect | Yes       | :ref:`CreateHostedDirectConnect <createhosteddirectconnect__en-us_topic_0000001735825656_request_createhosteddirectconnect>` object | Specifies the parameters for creating a hosted connection. |
   +----------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------+

.. _createhosteddirectconnect__en-us_topic_0000001735825656_request_createhosteddirectconnect:

.. table:: **Table 4** CreateHostedDirectConnect

   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter          | Mandatory       | Type            | Description                                                                                                                        |
   +====================+=================+=================+====================================================================================================================================+
   | name               | No              | String          | Specifies the hosted connection name.                                                                                              |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Minimum: **0**                                                                                                                     |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Maximum: **64**                                                                                                                    |
   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
   | description        | No              | String          | Provides supplementary information about the hosted connection.                                                                    |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Minimum: **0**                                                                                                                     |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Maximum: **128**                                                                                                                   |
   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
   | bandwidth          | Yes             | Integer         | Specifies the bandwidth size of the hosted connection in Mbit/s.                                                                   |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Minimum: **2**                                                                                                                     |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Maximum: **400000**                                                                                                                |
   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
   | hosting_id         | Yes             | String          | Specifies the ID of the operations connection on which the hosted connection is created.                                           |
   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
   | vlan               | Yes             | Integer         | Specifies the VLAN allocated to the hosted connection.                                                                             |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Minimum: **0**                                                                                                                     |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Maximum: **3999**                                                                                                                  |
   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
   | resource_tenant_id | Yes             | String          | Specifies the project ID of the specified tenant for whom a hosted connection is to be created.                                    |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Minimum: **0**                                                                                                                     |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Maximum: **32**                                                                                                                    |
   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
   | peer_location      | No              | String          | Specifies the location of the on-premises facility at the other end of the connection, specific to the street or data center name. |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Minimum: **0**                                                                                                                     |
   |                    |                 |                 |                                                                                                                                    |
   |                    |                 |                 | Maximum: **255**                                                                                                                   |
   +--------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 201**

.. table:: **Table 5** Response body parameters

   +----------------+--------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------+
   | Parameter      | Type                                                                                                                     | Description                                                |
   +================+==========================================================================================================================+============================================================+
   | request_id     | String                                                                                                                   | Specifies the request ID.                                  |
   +----------------+--------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------+
   | hosted_connect | :ref:`HostedDirectConnect <createhosteddirectconnect__en-us_topic_0000001735825656_response_hosteddirectconnect>` object | Specifies the parameters for creating a hosted connection. |
   +----------------+--------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------+

.. _createhosteddirectconnect__en-us_topic_0000001735825656_response_hosteddirectconnect:

.. table:: **Table 6** HostedDirectConnect

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                            |
   +=======================+=======================+========================================================================================================================================================================+
   | id                    | String                | Specifies the hosted connection ID.                                                                                                                                    |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Minimum: **36**                                                                                                                                                        |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Maximum: **36**                                                                                                                                                        |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the ID of the project that the instance belongs to.                                                                                                          |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                | Specifies the connection name.                                                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Minimum: **0**                                                                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Maximum: **64**                                                                                                                                                        |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the connection.                                                                                                               |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Minimum: **0**                                                                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Maximum: **128**                                                                                                                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | bandwidth             | Integer               | Specifies the connection bandwidth in Mbit/s.                                                                                                                          |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Minimum: **2**                                                                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Maximum: **400000**                                                                                                                                                    |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | location              | String                | Specifies information about the Direct Connect location.                                                                                                               |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Minimum: **0**                                                                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Maximum: **255**                                                                                                                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | peer_location         | String                | Specifies the location of the on-premises facility at the other end of the connection, specific to the street or data center name.                                     |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Minimum: **0**                                                                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Maximum: **255**                                                                                                                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | hosting_id            | String                | Specifies the ID of the operations connection on which the hosted connection is created.                                                                               |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | provider              | String                | Specifies the provider of the leased line.                                                                                                                             |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | Specifies the administrative status, which can be **true** or **false**.                                                                                               |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Default: **true**                                                                                                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vlan                  | Integer               | Specifies the VLAN allocated to the hosted connection.                                                                                                                 |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Minimum: **0**                                                                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Maximum: **3999**                                                                                                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Specifies the operating status of the hosted connection. The options are as follows:                                                                                   |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | -  **BUILD**: The hosted connection has been created.                                                                                                                  |
   |                       |                       | -  **ACTIVE**: The associated virtual gateway is normal.                                                                                                               |
   |                       |                       | -  **DOWN**: The port used by the hosted connection is down, indicating that there may be line faults.                                                                 |
   |                       |                       | -  **ERROR**: The associated virtual gateway is abnormal.                                                                                                              |
   |                       |                       | -  **PENDING_DELETE**: The hosted connection is being deleted.                                                                                                         |
   |                       |                       | -  **PENDING_UPDATE**: The hosted connection is being updated.                                                                                                         |
   |                       |                       | -  **PENDING_CREATE**: The hosted connection is being created.                                                                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Enumeration values:                                                                                                                                                    |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | -  **BUILD**                                                                                                                                                           |
   |                       |                       | -  **ACTIVE**                                                                                                                                                          |
   |                       |                       | -  **DOWN**                                                                                                                                                            |
   |                       |                       | -  **ERROR**                                                                                                                                                           |
   |                       |                       | -  **PENDING_DELETE**                                                                                                                                                  |
   |                       |                       | -  **PENDING_UPDATE**                                                                                                                                                  |
   |                       |                       | -  **PENDING_CREATE**                                                                                                                                                  |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | apply_time            | String                | Specifies when the connection was requested. The UTC time format **yyyy-MM-ddTHH:mm:ss.SSSZ** is used.                                                                 |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | create_time           | String                | Specifies when the connection was created. The UTC time format **yyyy-MM-ddTHH:mm:ss.SSSZ** is used.                                                                   |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | provider_status       | String                | Specifies the status of the carrier's leased line. The status can be **ACTIVE** or **DOWN**.                                                                           |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Enumeration values:                                                                                                                                                    |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | -  **ACTIVE**                                                                                                                                                          |
   |                       |                       | -  **DOWN**                                                                                                                                                            |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | port_type             | String                | Specifies the type of the port used by the connection. The value can be **1G**, **10G**, **40G**, or **100G**.                                                         |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Enumeration values:                                                                                                                                                    |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | -  **1G**                                                                                                                                                              |
   |                       |                       | -  **10G**                                                                                                                                                             |
   |                       |                       | -  **40G**                                                                                                                                                             |
   |                       |                       | -  **100G**                                                                                                                                                            |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | type                  | String                | Specifies the type of a connection. The value can be **standard** (a standard connection), **hosting** (an operations connection) or **hosted** (a hosted connection). |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Default: **standard**                                                                                                                                                  |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | Enumeration values:                                                                                                                                                    |
   |                       |                       |                                                                                                                                                                        |
   |                       |                       | -  **standard**                                                                                                                                                        |
   |                       |                       | -  **hosting**                                                                                                                                                         |
   |                       |                       | -  **hosted**                                                                                                                                                          |
   |                       |                       | -  **onestop_standard**                                                                                                                                                |
   |                       |                       | -  **onestop_hosted**                                                                                                                                                  |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Creating a hosting connection with the bandwidth set to 10 Mbit/s and VLAN to 441

.. code-block:: text

   POST https://{dc_endpoint}/v3/6fbe9263116a4b68818cf1edce16bc4f/dcaas/hosted-connects

   {
     "hosted_connect" : {
       "name" : "client-dc-faf1",
       "description" : "Hosted Connect",
       "resource_tenant_id" : "0605768a3300d5762f82c01180692873",
       "hosting_id" : "2cfb53be-b05f-40d5-a2f8-3a59ac383836",
       "vlan" : 441,
       "bandwidth" : 10
     }
   }

Example Responses
-----------------

**Status code: 201**

Created

-  The hosted connection is created.

   .. code-block::

      {
        "hosted_connect" : {
          "id" : "0278b472-ffa5-4eb3-8c0d-979d479f8ef6",
          "name" : "client-dc-faf1",
          "description" : "Hosted Connect",
          "tenant_id" : "0605768a3300d5762f82c01180692873",
          "hosting_id" : "2cfb53be-b05f-40d5-a2f8-3a59ac383836",
          "vlan" : 441,
          "bandwidth" : 10,
          "location" : "Biere",
          "peer_location" : "",
          "provider" : "OTC",
          "type" : "hosted",
          "port_type" : "10G",
          "provider_status" : "ACTIVE",
          "status" : "ACTIVE",
          "apply_time" : "2022-07-13T08:25:38.000Z",
          "admin_state_up" : true,
          "create_time" : "2022-07-13T08:25:38.000Z"
        },
        "request_id" : "a59a3776faa1d055f8124dc7b0977a90"
      }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
201         Created
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
