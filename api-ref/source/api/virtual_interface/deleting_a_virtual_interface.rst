:original_name: en-dc_topic_0055025331.html

.. _en-dc_topic_0055025331:

Deleting a Virtual Interface
============================

Function
--------

This API is used to delete a virtual interface.

URI
---

DELETE /v2.0/dcaas/virtual-interfaces/{virtual_interface_id}

.. table:: **Table 1** Parameter description

   +----------------------+--------+-----------+-------------------------------------+
   | Parameter            | Type   | Mandatory | Description                         |
   +======================+========+===========+=====================================+
   | virtual_interface_id | String | Yes       | Indicates the virtual interface ID. |
   +----------------------+--------+-----------+-------------------------------------+

Request
-------

:ref:`Table 2 <en-dc_topic_0055025331__table5224055914306>` lists the request parameter.

.. _en-dc_topic_0055025331__table5224055914306:

.. table:: **Table 2** Request parameter

   +----------------------+--------+-----------+-------------------------------------+
   | Parameter            | Type   | Mandatory | Description                         |
   +======================+========+===========+=====================================+
   | virtual_interface_id | String | Yes       | Indicates the virtual interface ID. |
   +----------------------+--------+-----------+-------------------------------------+

Response
--------

None

Examples
--------

-  Example request

.. code-block:: text

   DELETE /v2.0/dcaas/virtual-interfaces/{virtual_interface_id}

-  Response example

   None

Returned Value
--------------

For details, see section :ref:`Common Returned Values <en-dc_topic_0055025342>`.
