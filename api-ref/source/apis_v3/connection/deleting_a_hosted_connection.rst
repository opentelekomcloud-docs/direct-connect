:original_name: DeleteHostedDirectConnect.html

.. _DeleteHostedDirectConnect:

Deleting a Hosted Connection
============================

Function
--------

This API is used by partners to delete hosted connections.

URI
---

DELETE /v3/{project_id}/dcaas/hosted-connects/{hosted_connect_id}

.. table:: **Table 1** Path Parameters

   +-------------------+-----------------+-----------------+-------------------------------------+
   | Parameter         | Mandatory       | Type            | Description                         |
   +===================+=================+=================+=====================================+
   | project_id        | Yes             | String          | Specifies the project ID.           |
   +-------------------+-----------------+-----------------+-------------------------------------+
   | hosted_connect_id | Yes             | String          | Specifies the hosted connection ID. |
   |                   |                 |                 |                                     |
   |                   |                 |                 | Minimum: **36**                     |
   |                   |                 |                 |                                     |
   |                   |                 |                 | Maximum: **36**                     |
   +-------------------+-----------------+-----------------+-------------------------------------+

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

Deleting a hosted connection

.. code-block:: text

   DELETE https://{dc_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/dcaas/hosted-connects/94c2b814-99dc-939a-e811-ae84c61ea3ff

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
