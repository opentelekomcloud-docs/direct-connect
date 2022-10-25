:original_name: en-us_topic_0085241899.html

.. _en-us_topic_0085241899:

Creating a Direct Connection
============================

Scenarios
---------

Apply for a direct connection in the self-service mode to enable ECSs in your VPC to communicate with your data center or private network.

To request a direct connection, you need to create a connection, a virtual gateway, and a virtual interface.

In case the created single connection is faulty, you are recommended to create two connections to connect to different access locations. For details, see :ref:`Redundant Connection Access <en-us_topic_0128466510>`.

.. _en-us_topic_0085241899__section767665016484:

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and a project.

#. Under **Network**, click **Direct Connect**.

#. In the navigation pane on the left of **Network Console**, under **Direct Connect**, choose **Direct Connect** > **Connections**.

#. In the upper right corner of the **Connections** page, click **Create Connection**.

#. Follow the prompts to set the parameters.


   .. figure:: /_static/images/en-us_image_0210221955.png
      :alt: **Figure 1** Create Connection


      **Figure 1** Create Connection

   .. _en-us_topic_0085241899__table27593495173236:

   .. table:: **Table 1** Connection parameters

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                                                           | Example Value         |
      +=======================+=======================================================================================================================================================================================================================+=======================+
      | Region                | Specifies the region in which the services will be handled.                                                                                                                                                           | eu-de                 |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       | If you already selected a region and a project on the management console, you do not need to select the region here.                                                                                                  |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                  | Specifies the connection name.                                                                                                                                                                                        | dc-123                |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       | -  It can contain 1 to 64 characters.                                                                                                                                                                                 |                       |
      |                       | -  Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                                                                                |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Location              | Specifies the connection access location.                                                                                                                                                                             | Biere                 |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       | You can select **Biere** or **Magdeburg**.                                                                                                                                                                            |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Peering Position      | Specifies the physical location of the connection. The address is an identifier.                                                                                                                                      | Marderbug-DC01        |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       | -  Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                                                                                |                       |
      |                       | -  It can contain 0 to 64 characters.                                                                                                                                                                                 |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Bandwidth             | Specifies the bandwidth size in the unit of Mbit/s.                                                                                                                                                                   | 100                   |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       | -  You can select one of the bandwidths provided on the scroll bar by dragging it. Also, typing a value in the input field is allowed. It is automatically changed to the next allowed value shown on the slider bar. |                       |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       | -  The value ranges from 10 Mbit/s to 1000 Mbit/s.                                                                                                                                                                    |                       |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       |    Possible values are as follows:                                                                                                                                                                                    |                       |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       |    **10**, **50**, **100**, **150**, **200**, **300**, **400**, **500**, **600**, and **1000**                                                                                                                        |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Provides supplementary information about the connection.                                                                                                                                                              | This is a connection. |
      |                       |                                                                                                                                                                                                                       |                       |
      |                       | It can contain 0 to 128 characters.                                                                                                                                                                                   |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

#. Check the connection details and click **Submit**.

   .. note::

      -  Click **Back to Connection List** to view the created connections.
      -  After clicking **Submit**, you will be automatically redirected to the connection list after a timeout.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Gateways**.

#. In the upper right corner of the **Virtual Gateways** page, click **Create Virtual Gateway**.

#. Follow the prompts to set the parameters.


   .. figure:: /_static/images/en-us_image_0085245645.png
      :alt: **Figure 2** Create Virtual Gateway


      **Figure 2** Create Virtual Gateway

   .. _en-us_topic_0085241899__table128947911279:

   .. table:: **Table 2** Virtual gateway parameters

      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Parameter             | Description                                                                                                                                       | Example Value              |
      +=======================+===================================================================================================================================================+============================+
      | Name                  | Specifies the virtual gateway name.                                                                                                               | vgw-123                    |
      |                       |                                                                                                                                                   |                            |
      |                       | It can contain 1 to 64 characters.                                                                                                                |                            |
      |                       |                                                                                                                                                   |                            |
      |                       | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                               |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | VPC                   | Specifies the VPC where the virtual gateway resides.                                                                                              | VPC-001                    |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | CIDR Block            | Specifies the CIDR network segment of the VPC to be accessed by the direct connection.                                                            | 192.168.0.0/16             |
      |                       |                                                                                                                                                   |                            |
      |                       | You can add a maximum of 50 CIDR blocks. Each pair must be unique. Separate every two CIDR blocks with commas (,).                                |                            |
      |                       |                                                                                                                                                   |                            |
      |                       | A direct connection can access multiple VPCs. For details, see :ref:`Using a Direct Connection to Access Multiple VPCs <en-us_topic_0087378059>`. |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Description           | Provides supplementary information about the virtual gateway.                                                                                     | This is a virtual gateway. |
      |                       |                                                                                                                                                   |                            |
      |                       | It can contain 0 to 128 characters.                                                                                                               |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+

#. Click **OK**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. In the upper right corner of the **Virtual Interfaces** page, click **Create Virtual Interface**.

#. Follow the prompts to set the parameters.

   .. _en-us_topic_0085241899__fig1674715216343:

   .. figure:: /_static/images/en-us_image_0155708475.png
      :alt: **Figure 3** Create Virtual Interface


      **Figure 3** Create Virtual Interface

   .. _en-us_topic_0085241899__table54552924110:

   .. table:: **Table 3** Virtual interface parameters

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Parameter             | Description                                                                                                                                                                                                        | Example Value                |
      +=======================+====================================================================================================================================================================================================================+==============================+
      | Region                | Specifies the region in which the services will be handled.                                                                                                                                                        | eu-de                        |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | If you already selected a region and a project on the management console, you do not need to select the region here.                                                                                               |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Name                  | Specifies the virtual interface name.                                                                                                                                                                              | vif-123                      |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | It can contain 1 to 64 characters.                                                                                                                                                                                 |                              |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                                                                                |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Connection            | Specifies the connection to be associated.                                                                                                                                                                         | dc-123                       |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | A connection can be associated with only one virtual interface. Only connections that are not bound to other interfaces are available in the list.                                                                 |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Virtual Gateway       | Select the virtual gateway to be associated.                                                                                                                                                                       | vgw-123                      |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | You can select a virtual gateway that has virtual interfaces bound. However, the connection associated with the virtual interfaces that have been bound to the virtual gateway needs to be at different locations. |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | VLAN                  | Specifies the virtual interface VLAN ID.                                                                                                                                                                           | 30                           |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | The system automatically allocates a VLAN ID. You do not need to set this parameter.                                                                                                                               |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Bandwidth             | Specifies the virtual interface bandwidth in the unit of Mbit/s.                                                                                                                                                   | 100                          |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | If the selected connection is a hosting connection, the virtual interface exclusively uses the connection bandwidth. That is, the connection bandwidth is the bandwidth of the virtual interface.                  |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Remote Subnet         | Specifies the remote subnet and mask. You can enter a maximum of 50 remote subnets. Each pair must be unique. Separate every two remote subnets with commas (,).                                                   | 192.168.51.0/24              |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | The remote subnet of the virtual interface cannot be the same as the VPC CIDR block of the virtual gateway.                                                                                                        |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Description           | Provides supplementary information about the virtual interface.                                                                                                                                                    | This is a virtual interface. |
      |                       |                                                                                                                                                                                                                    |                              |
      |                       | It can contain 0 to 128 characters.                                                                                                                                                                                |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+

#. Click **Create Now**.

.. |image1| image:: /_static/images/en-us_image_0070860784.png
