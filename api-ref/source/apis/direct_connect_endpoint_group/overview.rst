:original_name: en-dc_topic_0055025335.html

.. _en-dc_topic_0055025335:

Overview
========

.. _en-dc_topic_0055025335__en-us_topic_0070658768_section23215317204921:

Object Introduction
-------------------

This section describes the APIs for managing and operating Direct Connect endpoint groups, including the APIs used to create, query, update, and delete a Direct Connect endpoint group, and the API used to query the Direct Connect endpoint group list.

.. note::

   Direct Connect endpoint group APIs do not support IPv6 addresses.

.. _en-dc_topic_0055025335__en-us_topic_0070658768_section51721924204921:

Object Model
------------

.. table:: **Table 1** Direct Connect endpoint group objects

   +-------------+--------------+-----------+-------------------------+----------------------------------------------------------------------------------+-----------------------------------------------------------------------------+
   | Parameter   | Type         | CRUD      | Default Value           | Constraint                                                                       | Description                                                                 |
   +=============+==============+===========+=========================+==================================================================================+=============================================================================+
   | id          | String       | R         | Automatically generated | UUID                                                                             | Specifies the ID of the Direct Connect endpoint group.                      |
   +-------------+--------------+-----------+-------------------------+----------------------------------------------------------------------------------+-----------------------------------------------------------------------------+
   | tenant_id   | String       | CR        | N/A                     | The value can contain 0 to 255 characters.                                       | Specifies the tenant ID.                                                    |
   +-------------+--------------+-----------+-------------------------+----------------------------------------------------------------------------------+-----------------------------------------------------------------------------+
   | name        | String       | CRU       | No                      | The value can contain 0 to 64 characters.                                        | Specifies the name of the Direct Connect endpoint group.                    |
   |             |              |           |                         |                                                                                  |                                                                             |
   |             |              |           |                         | Only letters, digits, underscores (_), hyphens (-), and periods (.) are allowed. |                                                                             |
   +-------------+--------------+-----------+-------------------------+----------------------------------------------------------------------------------+-----------------------------------------------------------------------------+
   | description | String       | CRU       | No                      | The value can contain 0 to 128 characters.                                       | Provides supplementary information about the Direct Connect endpoint group. |
   |             |              |           |                         |                                                                                  |                                                                             |
   |             |              |           |                         | Angle brackets (<>) are not allowed.                                             |                                                                             |
   +-------------+--------------+-----------+-------------------------+----------------------------------------------------------------------------------+-----------------------------------------------------------------------------+
   | endpoints   | List<String> | CR        | N/A                     | N/A                                                                              | Specifies the list of the endpoints in a Direct Connect endpoint group.     |
   +-------------+--------------+-----------+-------------------------+----------------------------------------------------------------------------------+-----------------------------------------------------------------------------+
   | type        | String       | CR        | N/A                     | Only IPv4 CIDR blocks are supported.                                             | Specifies the type of the Direct Connect endpoints.                         |
   +-------------+--------------+-----------+-------------------------+----------------------------------------------------------------------------------+-----------------------------------------------------------------------------+
