:original_name: en-us_topic_0055025317.html

.. _en-us_topic_0055025317:

Deleting a Connection
=====================

.. _en-us_topic_0055025317__section43031324205035:

Function
--------

This API is used to delete a connection.

.. _en-us_topic_0055025317__section29996404205035:

URI
---

DELETE /v2.0/dcaas/direct-connects/{direct_connect_id}

.. table:: **Table 1** Parameter description

   ================= ====== ========= ============================
   Parameter         Type   Mandatory Description
   ================= ====== ========= ============================
   direct_connect_id String Yes       Specifies the connection ID.
   ================= ====== ========= ============================

Request
-------

None

Response
--------

None

Examples
--------

-  Example request

.. code-block:: text

   DELETE /v2.0/dcaas/direct-connects/{direct_connect_id}

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
