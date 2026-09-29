:original_name: en-us_topic_0035014627.html

.. _en-us_topic_0035014627:

Application Scenarios
=====================

Access to Multiple VPCs Within a Region from an On-premises Data Center
-----------------------------------------------------------------------

After you connect your on-premises data center to the cloud using Direct Connect, you can use a peering connection to connect the VPC that your on-premises data center is accessing to those in the same region, so that your on-premises data center can access all connected VPCs.

|image1|

Hybrid Cloud Deployment
-----------------------

Direct Connect allows you to build a hybrid environment for your on-premises data center and leverage the scalability of the cloud to expand the computing capability of your applications.


.. figure:: /_static/images/en-us_image_0000001146013067.png
   :alt: **Figure 1** Hybrid cloud

   **Figure 1** Hybrid cloud

.. table:: **Table 1** Comparisons of Direct Connect and VPN in hybrid cloud deployment

   +-------------------------------+---------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Cloud Service                 | Application Scenario                                                                  | Description                                                                                                                                                                                                                            |
   +===============================+=======================================================================================+========================================================================================================================================================================================================================================+
   | Virtual Private Network (VPN) | Connect an on-premises data center to the cloud through an IPsec tunnel.              | An encrypted tunnel is used to connect a VPC to an on-premises data center over the Internet. The tunnel features low cost, simple configuration, and ease-of-use. However, the network quality depends on the Internet.               |
   +-------------------------------+---------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Direct Connect                | Connect an on-premises data center to the cloud using a dedicated network connection. | A dedicated connection connects a VPC to an on-premises data center. The connection features low latency, high security, and dedicated use. It is applicable to scenarios that require high network transmission quality and security. |
   +-------------------------------+---------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001490649208.png
