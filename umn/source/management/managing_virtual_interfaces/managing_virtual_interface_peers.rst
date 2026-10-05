:original_name: dc_04_0405.html

.. _dc_04_0405:

Managing Virtual Interface Peers
================================

Overview
--------

A configuration of the virtual interface to support the IPv4/IPv6 dual stack. The IP address type of a virtual interface peer depends on the associated connection.

Constraints
-----------

-  If the connection supports IPv6, you can create an IPv4 peer and an IPv6 peer for a virtual interface to connect your on-premises data center to the cloud over an IPv4 network and an IPv6 network.

   If an IPv4 virtual interface peer already exists, only an IPv6 virtual interface peer can be created, and vice versa.

-  If the connection does not support IPv6, only an IPv4 peer can be created for the virtual interface.

-  A virtual interface must have at least one virtual interface peer, and the last virtual interface peer cannot be deleted.

Creating a Virtual Interface Peer
---------------------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. Locate the virtual interface and click its name.

#. Click **Create Peer** above the virtual interface peer list.

   Configure the parameters based on :ref:`Table 1 <dc_04_0405__en-us_topic_0000001279593829_table443012227148>`.


   .. figure:: /_static/images/en-us_image_0000002626992036.png
      :alt: **Figure 1** Creating a virtual interface peer

      **Figure 1** Creating a virtual interface peer

   .. _dc_04_0405__en-us_topic_0000001279593829_table443012227148:

   .. table:: **Table 1** Parameters required for creating a virtual interface peer

      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                  | Description                                                                                                                                                            | Example Value         |
      +============================+========================================================================================================================================================================+=======================+
      | Name                       | Specifies the virtual interface peer name.                                                                                                                             | vifpeer               |
      |                            |                                                                                                                                                                        |                       |
      |                            | The name can contain 1 to 64 characters.                                                                                                                               |                       |
      |                            |                                                                                                                                                                        |                       |
      |                            | Only digits, letters, underscores (_), hyphens (-), and periods (.) are allowed.                                                                                       |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IP Address Family          | -  If an IPv6 virtual interface peer already exists, IPv4 is selected by default.                                                                                      | IPv4                  |
      |                            | -  If an IPv4 virtual interface peer already exists, IPv6 is selected by default.                                                                                      |                       |
      |                            |                                                                                                                                                                        |                       |
      |                            | .. note::                                                                                                                                                              |                       |
      |                            |                                                                                                                                                                        |                       |
      |                            |    The IP address type of the peer must be the same as that of the virtual gateway to be associated with the virtual interface to ensure normal network communication. |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Local Gateway              | Specifies the IP address for connecting to the cloud network.                                                                                                          | 10.0.x.1/30           |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Gateway             | Specifies the IP address for connecting to the on-premises network.                                                                                                    | 10.0.x.2/30           |
      |                            |                                                                                                                                                                        |                       |
      |                            | The remote gateway must be in the same CIDR block as the local gateway. Generally, a subnet with a 30-bit mask is recommended.                                         |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Subnet              | Specifies the subnets and masks of your network.                                                                                                                       | 192.168.x.x/24        |
      |                            |                                                                                                                                                                        |                       |
      |                            | If you enter multiple remote subnets, separate them with commas (,) or line breaks.                                                                                    | 10.1.x.x/24           |
      |                            |                                                                                                                                                                        |                       |
      |                            | .. caution::                                                                                                                                                           |                       |
      |                            |                                                                                                                                                                        |                       |
      |                            |    CAUTION:                                                                                                                                                            |                       |
      |                            |                                                                                                                                                                        |                       |
      |                            |    -  Remote subnets cannot overlap with local subnets.                                                                                                                |                       |
      |                            |    -  Using 100.64.0.0/10 as the remote subnet may cause services such as OBS, DNS, and API Gateway to become unavailable.                                             |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Routing Mode               | Specifies the routing mode. Static routing and BGP routing are supported.                                                                                              | BGP                   |
      |                            |                                                                                                                                                                        |                       |
      |                            | If there are two or more connections, select BGP routing.                                                                                                              |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | BGP ASN                    | Specifies the BGP ASN used on your on-premises network.                                                                                                                | 12345                 |
      |                            |                                                                                                                                                                        |                       |
      |                            | This parameter is required when BGP routing is selected.                                                                                                               |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | BGP MD5 Authentication Key | Specifies the password used to authenticate the BGP peer using MD5. The value is case sensitive and cannot contain spaces.                                             | Qaz12345678           |
      |                            |                                                                                                                                                                        |                       |
      |                            | This parameter is mandatory if you select BGP routing, and you must ensure that the parameter values on both gateways are the same.                                    |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description                | Provides the description about the virtual interface peer.                                                                                                             | ``-``                 |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

Viewing a Virtual Interface Peer
--------------------------------

#. Log in to the management console.

#. Click |image2| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. Locate the virtual interface and click its name.

#. In the lower part of the page, locate the virtual interface peer you want to view and view its details.


   .. figure:: /_static/images/en-us_image_0000002627013000.png
      :alt: **Figure 2** Viewing a virtual interface peer

      **Figure 2** Viewing a virtual interface peer

Modifying a Virtual Interface Peer
----------------------------------

#. Log in to the management console.

#. Click |image3| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. Locate the virtual interface and click its name.

#. In the lower part of the page, locate the virtual interface peer you want to modify and click **Modify** in the **Operation** column.

   Modify the name, remote subnet, and description of the virtual interface peer as prompted.


   .. figure:: /_static/images/en-us_image_0000002627175696.png
      :alt: **Figure 3** Modifying a virtual interface peer (using IPv4 as an example)

      **Figure 3** Modifying a virtual interface peer (using IPv4 as an example)

#. Click **OK**.

Deleting a Virtual Interface Peer
---------------------------------

A virtual interface peer cannot be deleted if it is the only peer of a virtual interface.

#. Log in to the management console.

#. Click |image4| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. Locate the virtual interface and click its name.

#. In the virtual interface peer list, click **Delete** in the **Operation** column of the target virtual interface peer.

#. Confirm the information and click **OK**.


   .. figure:: /_static/images/en-us_image_0000002627188368.png
      :alt: **Figure 4** Deleting a virtual interface peer

      **Figure 4** Deleting a virtual interface peer

.. |image1| image:: /_static/images/en-us_image_0000002429106732.png
.. |image2| image:: /_static/images/en-us_image_0000002429106732.png
.. |image3| image:: /_static/images/en-us_image_0000002429106732.png
.. |image4| image:: /_static/images/en-us_image_0000002429106732.png
