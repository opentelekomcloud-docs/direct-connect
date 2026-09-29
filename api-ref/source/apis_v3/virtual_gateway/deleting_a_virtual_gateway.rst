:original_name: DeleteVirtualGateway.html

.. _DeleteVirtualGateway:

Deleting a Virtual Gateway
==========================

Function
--------

The API is used to delete a specified virtual gateway.

URI
---

DELETE /v3/{project_id}/dcaas/virtual-gateways/{virtual_gateway_id}

.. table:: **Table 1** Path Parameters

   ================== ========= ====== =================================
   Parameter          Mandatory Type   Description
   ================== ========= ====== =================================
   project_id         Yes       String Specifies the project ID.
   virtual_gateway_id Yes       String Specifies the virtual gateway ID.
   ================== ========= ====== =================================

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

Response Parameters
-------------------

None

Example Requests
----------------

Deleting a virtual gateway

.. code-block:: text

   DELETE https://{dc_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/dcaas/virtual-gateways/20082c1b-3c99-48d8-8e8c-116af5d7e9f0

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
204         No Content
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
