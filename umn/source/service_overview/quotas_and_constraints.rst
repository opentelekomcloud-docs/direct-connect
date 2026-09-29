:original_name: en-us_topic_0166140183.html

.. _en-us_topic_0166140183:

Quotas and Constraints
======================

Quotas
------

+-------------------------------------------------------------------------------+-------+
| Resource                                                                      | Quota |
+===============================================================================+=======+
| Number of connections that can be created by an account in each region        | 10    |
+-------------------------------------------------------------------------------+-------+
| Number of virtual interfaces that can be created by an account in each region | 50    |
+-------------------------------------------------------------------------------+-------+
| Number of virtual gateways that can be created by an account in each region   | 5     |
+-------------------------------------------------------------------------------+-------+
| Number of local subnets for a virtual gateway                                 | 50    |
+-------------------------------------------------------------------------------+-------+
| Number of routes for BGP sessions on a virtual interface                      | 100   |
+-------------------------------------------------------------------------------+-------+
| Number of static routes on a virtual interface                                | 50    |
+-------------------------------------------------------------------------------+-------+

.. note::

   Online quota adjustment is not supported. If you need to increase a quota, contact the administrator.

   Before contacting the administrator, ensure that you have obtained the following information:

   -  Domain name, project name, and project ID, which can be obtained by performing the following operations:

      To obtain the preceding information, log in to the management console, click the username in the upper-right corner, and choose **My Credentials** from the drop-down list.

   -  Quota information, which includes service name, quota type, and required quota

.. _en-us_topic_0166140183__section15484181915473:

Constraints
-----------

-  The CIDR block of the VPC cannot overlap with the CIDR block used by the on-premises network.

   The on-premises network cannot use 100.64.0.0/10, 127.0.0.0/8, 169.254.0.0/16, and 224.0.0.0/3 because they are reserved for the VPC service.

-  Currently, 1GE and 10GE single-mode optical ports can transmit data up to 10 km. If you need an optical port to transmit data for more than 10 km, or you need a 40GE or 100GE port, you need to purchase the optical modules by yourself.

-  If you use a Direct Connect connection to access ELB, you must select **Source IP hash** as the load balancing algorithm and disable sticky sessions for ELB.

-  Direct Connect can respond to common ICMP packets (echo packets whose type is 8 and code is 0 and do not carry IP options) for ping detections.

-  For each connection, a maximum of 30 ping detections can be performed on the local gateway IP address over the port per second.

-  A virtual gateway can be associated with only two different devices.
