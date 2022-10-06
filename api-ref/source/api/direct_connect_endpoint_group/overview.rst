:original_name: en-dc_topic_0055025335.html

.. _en-dc_topic_0055025335:

Overview
========

Object Introduction
-------------------

This section describes the APIs for managing and operating Direct Connect endpoint groups, including the APIs used to create, query, update, and delete a Direct Connect endpoint group, and the API used to query the Direct Connect endpoint group list.

Object Model
------------

.. table:: **Table 1** Direct Connect endpoint group objects

   +-------------+--------------+-----------+-------------------------+--------------------------------------------+-----------------------------------------------------------------------------+
   | Attribute   | Type         | CRUD      | Default Value           | Constraint                                 | Description                                                                 |
   +=============+==============+===========+=========================+============================================+=============================================================================+
   | id          | String       | R         | Automatically generated | uuid                                       | Specifies the ID of the Direct Connect endpoint group.                      |
   +-------------+--------------+-----------+-------------------------+--------------------------------------------+-----------------------------------------------------------------------------+
   | tenant_id   | String       | CR        | N/A                     | The value can contain 0 to 255 characters. | Specifies the project ID.                                                   |
   +-------------+--------------+-----------+-------------------------+--------------------------------------------+-----------------------------------------------------------------------------+
   | name        | String       | CRU       | No                      | The value can contain 0 to 64 characters.  | Specifies the name of the Direct Connect endpoint group.                    |
   +-------------+--------------+-----------+-------------------------+--------------------------------------------+-----------------------------------------------------------------------------+
   | description | String       | CRU       | No                      | The value can contain 0 to 128 characters. | Provides supplementary information about the Direct Connect endpoint group. |
   +-------------+--------------+-----------+-------------------------+--------------------------------------------+-----------------------------------------------------------------------------+
   | endpoints   | List<String> | CR        | N/A                     | N/A                                        | Specifies the list of the endpoints in a Direct Connect endpoint group.     |
   +-------------+--------------+-----------+-------------------------+--------------------------------------------+-----------------------------------------------------------------------------+
   | type        | String       | CR        | N/A                     | Only **cidr** is supported.                | Specifies the type of the Direct Connect endpoints.                         |
   |             |              |           |                         |                                            |                                                                             |
   |             |              |           |                         |                                            | The value can only be **cidr**.                                             |
   +-------------+--------------+-----------+-------------------------+--------------------------------------------+-----------------------------------------------------------------------------+
