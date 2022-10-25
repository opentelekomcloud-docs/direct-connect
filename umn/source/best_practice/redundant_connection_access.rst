:original_name: en-us_topic_0128466510.html

.. _en-us_topic_0128466510:

Redundant Connection Access
===========================

Scenarios
---------

A local data center is connected to a VPC through a connection. To prevent a single connection failure from affecting services, you are advised to create two connections with different access locations. If a connection fails, services are switched to the other connection quickly. Therefore, the communication between the local data center and the VPC is of high quality and high reliability.


.. figure:: /_static/images/en-us_image_0159220007.png
   :alt: **Figure 1** Redundant connection access

   **Figure 1** Redundant connection access

Operation Flowchart
-------------------

You need to create two connections, with one connecting to Biere and the other to Magdeburg. Create a virtual gateway and access the VPC to which the services belong. Create two virtual interfaces and connect them to the same virtual gateway associated with the target VPC. :ref:`Figure 2 <en-us_topic_0128466510__fig159261841102013>` shows how to create a redundant connection.

.. _en-us_topic_0128466510__fig159261841102013:

.. figure:: /_static/images/en-us_image_0159221137.png
   :alt: **Figure 2** Flowchart for creating a redundant connection

   **Figure 2** Flowchart for creating a redundant connection

Procedure
---------

**Creating a Connection**

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and a project.

#. Under **Network**, click **Direct Connect**.

#. .. _en-us_topic_0128466510__li1734982310613:

   In the navigation pane of **Network Console**, choose **Direct Connect** > **Connections**.

#. On the displayed **Connections** page, click **Create Connection** in the upper right corner to create the first connection.

#. Follow the prompts to set the following parameters.

   .. table:: **Table 1** Connection parameters

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                                                        | Example Value         |
      +=======================+====================================================================================================================================================================================================================+=======================+
      | Region                | Specifies the region in which the services will be handled.                                                                                                                                                        | eu-de                 |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | If you already selected a region and a project on the management console, you do not need to select the region here.                                                                                               |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                  | Specifies the connection name.                                                                                                                                                                                     | dc-123                |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | It can contain 1 to 64 characters.                                                                                                                                                                                 |                       |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                                                                                |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Location              | Specifies the connection access location.                                                                                                                                                                          | Biere                 |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | You can select **Biere** or **Magdeburg**. The access location of the first connection must be different from that of the second connection.                                                                       |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Peering Position      | Specifies the physical location of the connection. The address is an identifier.                                                                                                                                   | "Marderbug-DC01"      |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                                                                                |                       |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | It can contain 0 to 64 characters.                                                                                                                                                                                 |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Bandwidth             | Specifies the bandwidth size in the unit of Mbit/s.                                                                                                                                                                | 100                   |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | You can select one of the bandwidths provided on the scroll bar by dragging it. Also, typing a value in the input field is allowed. It is automatically changed to the next allowed value shown on the slider bar. |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Provides supplementary information about the connection.                                                                                                                                                           | This is a connection. |
      |                       |                                                                                                                                                                                                                    |                       |
      |                       | It can contain 0 to 128 characters.                                                                                                                                                                                |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. .. _en-us_topic_0128466510__li111521031181317:

   Click **Create Now**, confirm the connection details, and click **Submit**.

   .. note::

      -  Click **Back to Connection List** to view the created connections.
      -  After clicking **Submit**, you will be automatically redirected to the connection list after a timeout.

#. Repeat step :ref:`4 <en-us_topic_0128466510__li1734982310613>` to step :ref:`7 <en-us_topic_0128466510__li111521031181317>` to create the second connection.

**Creating a Virtual Gateway**

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Gateways**.
#. In the upper right corner of the **Virtual Gateways** page, click **Create Virtual Gateway**.
#. Follow the prompts to set the following parameters.

   .. table:: **Table 2** Virtual gateway parameters

      +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Parameter             | Description                                                                                                        | Example Value              |
      +=======================+====================================================================================================================+============================+
      | Name                  | Specifies the virtual gateway name.                                                                                | vgw-123                    |
      |                       |                                                                                                                    |                            |
      |                       | It can contain 1 to 64 characters.                                                                                 |                            |
      |                       |                                                                                                                    |                            |
      |                       | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                |                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
      | VPC                   | Specifies the VPC that you need to access.                                                                         | VPC-001                    |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
      | CIDR Block            | Specifies the CIDR network segment of the VPC to be accessed by the direct connection.                             | 192.168.0.0/16             |
      |                       |                                                                                                                    |                            |
      |                       | You can add a maximum of 50 CIDR blocks. Each pair must be unique. Separate every two CIDR blocks with commas (,). |                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Description           | Provides supplementary information about the virtual gateway.                                                      | This is a virtual gateway. |
      |                       |                                                                                                                    |                            |
      |                       | It can contain 0 to 128 characters.                                                                                |                            |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+

#. Click **OK**.

**Creating a Virtual Interface**

#. .. _en-us_topic_0128466510__li1022162832914:

   In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. On the displayed **Virtual Interfaces** page, click **Create Virtual Interface** in the upper right corner to create the first virtual interface.

#. Follow the prompts to set the following parameters.

   .. table:: **Table 3** Virtual interface parameters

      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Parameter             | Description                                                                                                                                                                                       | Example Value                |
      +=======================+===================================================================================================================================================================================================+==============================+
      | Region                | Specifies the region in which the services will be handled.                                                                                                                                       | eu-de                        |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | If you already selected a region and a project on the management console, you do not need to select the region here.                                                                              |                              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Name                  | Specifies the virtual interface name.                                                                                                                                                             | vif-123                      |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | It can contain 1 to 64 characters.                                                                                                                                                                |                              |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                                                               |                              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Connection            | Specifies the connection to be associated.                                                                                                                                                        | dc-123                       |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | Select the connection that is connected to Biere or Magdeburg. The access locations of the two connections must be different.                                                                     |                              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Virtual Gateway       | Select the virtual gateway to be associated.                                                                                                                                                      | vgw-123                      |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | VLAN                  | Specifies the virtual interface VLAN ID.                                                                                                                                                          | 30                           |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | The system automatically allocates a VLAN ID. You do not need to set this parameter.                                                                                                              |                              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Bandwidth             | Specifies the virtual interface bandwidth in the unit of Mbit/s.                                                                                                                                  | 100                          |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | If the selected connection is a hosting connection, the virtual interface exclusively uses the connection bandwidth. That is, the connection bandwidth is the bandwidth of the virtual interface. |                              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Remote Subnet         | Specifies the remote subnet and mask. You can enter a maximum of 50 remote subnets. Each pair must be unique. Separate every two remote subnets with commas (,).                                  | 192.168.51.0/24              |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | The remote subnet of the virtual interface cannot be the same as the VPC CIDR block of the virtual gateway.                                                                                       |                              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Description           | Provides supplementary information about the virtual interface.                                                                                                                                   | This is a virtual interface. |
      |                       |                                                                                                                                                                                                   |                              |
      |                       | It can contain 0 to 128 characters.                                                                                                                                                               |                              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+

#. .. _en-us_topic_0128466510__li13735165074810:

   Click **Create Now**.

#. Repeat step :ref:`1 <en-us_topic_0128466510__li1022162832914>` to step :ref:`4 <en-us_topic_0128466510__li13735165074810>` to create the second virtual interface.

.. |image1| image:: /_static/images/en-us_image_0070860784.png
