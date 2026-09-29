:original_name: en-us_topic_0055025312.html

.. _en-us_topic_0055025312:

Querying a Specified API Version
================================

Function
--------

This API is used to query a specified API version supported by Direct Connect.

URI
---

GET /{api_version}

Request
-------

None

.. _en-us_topic_0055025312__section15686020:

Response
--------

:ref:`Table 1 <en-us_topic_0055025312__table49902238182444>` lists the response parameters.

.. _en-us_topic_0055025312__table49902238182444:

.. table:: **Table 1** Response parameters

   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                                        |
   +=======================+=======================+====================================================================================================================================================================================================+
   | id                    | String                | Specifies the version number, for example, **v2.0**.                                                                                                                                               |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | links                 | Array                 | Specifies the API URL.                                                                                                                                                                             |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | href                  | String                | Specifies the reference address of the current API version.                                                                                                                                        |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rel                   | String                | Specifies the relationship between the current API version and the referenced address.                                                                                                             |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | version               | String                | Specifies the version. If APIs of this version support minor versions, set this parameter to the supported maximum minor version. If minor versions are not supported, leave this parameter blank. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Specifies the version status. Value options are as follows:                                                                                                                                        |
   |                       |                       |                                                                                                                                                                                                    |
   |                       |                       | -  **CURRENT**: indicates a primary version.                                                                                                                                                       |
   |                       |                       | -  **SUPPORTED**: indicates an old version that is still supported.                                                                                                                                |
   |                       |                       | -  **DEPRECATED**: indicates a deprecated version that may be deleted later.                                                                                                                       |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated               | String                | Specifies the version release time in UTC. For example, the release time format of v2.0 APIs is YYYY-MM-DDTHH:MM:SSZ.                                                                              |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | min_version           | String                | Specifies the version. If APIs of this version support minor versions, set this parameter to the supported minimum minor version. If minor versions are not supported, leave this parameter blank. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

-  Example request

   .. code-block:: text

      GET /v2.0

-  .. _en-us_topic_0055025312__li426275618505:

   Example response

   .. code-block::

      {
        "version": {
          "id": "v2.0",
          "links": [
            {
              "href": "https://dcaas.eu-de.otc.t-systems.com/v2.0",
              "rel": "self"
            }
          ],
          "updated": "YYYY-MM-DDTHH:MM:SSZ",
          "status": "CURRENT",
          "version": "",
          "min_version": ""
        }
      }
