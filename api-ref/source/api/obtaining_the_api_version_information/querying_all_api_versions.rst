:original_name: en-dc_topic_0055025311.html

.. _en-dc_topic_0055025311:

Querying All API Versions
=========================

Function
--------

This API is used to query all API versions supported by Direct Connect.

URI
---

GET /

Request
-------

None

Response
--------

:ref:`Table 1 <en-dc_topic_0055025311__table49902238182444>` lists the response parameters.

.. _en-dc_topic_0055025311__table49902238182444:

.. table:: **Table 1** Response parameters

   +-----------------------+-----------------------+----------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                            |
   +=======================+=======================+========================================================================================+
   | versions              | List                  | Specifies all API versions.                                                            |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------+
   | id                    | String                | Specifies the version number, for example, **v2.0**                                    |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------+
   | links                 | Array                 | Specifies the API URL.                                                                 |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------+
   | href                  | String                | Specifies the reference address of the current API version.                            |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------+
   | rel                   | String                | Specifies the relationship between the current API version and the referenced address. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------+
   | status                | String                | Specifies the version status. Value options are as follows:                            |
   |                       |                       |                                                                                        |
   |                       |                       | -  **CURRENT**: indicates a primary version.                                           |
   |                       |                       | -  **SUPPORTED**: indicates an old version that is still supported.                    |
   |                       |                       | -  **DEPRECATED**: indicates a deprecated version that may be deleted later.           |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET /

-  Example response

   .. code-block::

      {
       "versions": [
          {
            "status": "CURRENT",
            "id": "v2.0",
            "links":[
              {
                "href": "https://network.az0.dc0.domainname.com/v2.0","rel": "self"
               }
            ]
          }
        ]
      }
