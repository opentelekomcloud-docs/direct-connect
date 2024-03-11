:original_name: DeleteVirtualInterface.html

.. _DeleteVirtualInterface:

Deleting a Virtual Interface
============================

Function
--------

This API is used to delete a virtual interface.

URI
---

DELETE /v3/{project_id}/dcaas/virtual-interfaces/{virtual_interface_id}

.. table:: **Table 1** Path Parameters

   +----------------------+-----------------+-----------------+-------------------------------------+
   | Parameter            | Mandatory       | Type            | Description                         |
   +======================+=================+=================+=====================================+
   | project_id           | Yes             | String          | Specifies the project ID.           |
   +----------------------+-----------------+-----------------+-------------------------------------+
   | virtual_interface_id | Yes             | String          | Specifies the virtual interface ID. |
   |                      |                 |                 |                                     |
   |                      |                 |                 | Minimum: **36**                     |
   |                      |                 |                 |                                     |
   |                      |                 |                 | Maximum: **36**                     |
   +----------------------+-----------------+-----------------+-------------------------------------+

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

Deleting a virtual interface

.. code-block:: text

   DELETE https://{dc_endpoint}/v3/0605768a3300d5762f82c01180692873/dcaas/virtual-interfaces/0d0fdf63-f2c4-491c-8866-d504796189be

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
