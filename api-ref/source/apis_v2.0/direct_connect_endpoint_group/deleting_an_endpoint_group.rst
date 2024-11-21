:original_name: en-us_topic_0055025338.html

.. _en-us_topic_0055025338:

Deleting an Endpoint Group
==========================

Function
--------

This API is used to delete a Direct Connect endpoint group.

URI
---

DELETE /v2.0/dcaas/dc-endpoint-groups/{endpoint_group_id}

.. table:: **Table 1** Parameter description

   +-------------------+--------+-----------+--------------------------------------------------------+
   | Parameter         | Type   | Mandatory | Description                                            |
   +===================+========+===========+========================================================+
   | endpoint_group_id | String | Yes       | Specifies the ID of the Direct Connect endpoint group. |
   +-------------------+--------+-----------+--------------------------------------------------------+

Request
-------

:ref:`Table 2 <en-us_topic_0055025338__en-us_topic_0070658809_table2198437322244>` lists the request parameter.

.. _en-us_topic_0055025338__en-us_topic_0070658809_table2198437322244:

.. table:: **Table 2** Request parameter

   +-------------------+--------+-----------+--------------------------------------------------------+
   | Parameter         | Type   | Mandatory | Description                                            |
   +===================+========+===========+========================================================+
   | endpoint_group_id | String | Yes       | Specifies the ID of the Direct Connect endpoint group. |
   +-------------------+--------+-----------+--------------------------------------------------------+

Response
--------

None

Examples
--------

-  Example request

.. code-block:: text

   DELETE /v2.0/dcaas/dc-endpoint-groups/{endpoint_group_id}

-  Response example

   None

Status Codes
------------

For details, see :ref:`Common Status Codes <en-us_topic_0055025342>`.
