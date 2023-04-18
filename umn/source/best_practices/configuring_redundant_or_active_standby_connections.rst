:original_name: en-us_topic_0128466510.html

.. _en-us_topic_0128466510:

Configuring Redundant or Active/Standby Connections
===================================================

Scenarios
---------

You plan to use Direct Connect to connect your on-premises data center to your VPCs. To prevent service interruption resulted from connection failures, you need to request two connections terminated at different locations. The two connections are mutually backed up to ensure high reliability. If a connection fails, the other connection will be used for communications.

.. _en-us_topic_0128466510__fig1613412318719:

.. figure:: /_static/images/en-us_image_0000001500493814.png
   :alt: **Figure 1** Redundant or active/standby connections

   **Figure 1** Redundant or active/standby connections

Operation Flowchart
-------------------

You need to select two locations and request two connections. For example, in the **eu-de** region, select Biere for one connection, and Magdeburg for the other connection. Create a virtual gateway and access the VPC to which the services belong. Create two virtual interfaces and connect them to the same virtual gateway associated with the target VPC. :ref:`Figure 2 <en-us_topic_0128466510__fig159261841102013>` shows how to request two connections to allow your on-premises data center to access the same VPC.

.. _en-us_topic_0128466510__fig159261841102013:

.. figure:: /_static/images/en-us_image_0000001551687625.png
   :alt: **Figure 2** Flowchart for requesting redundant connections

   **Figure 2** Flowchart for requesting redundant connections

Procedure
---------

#. Request two connections.

   a. Collect the information required for requesting two connections based on :ref:`Table 1 <en-us_topic_0128466510__dc_02_0202_table27593495173236>`.

      .. _en-us_topic_0128466510__dc_02_0202_table27593495173236:

      .. table:: **Table 1** Information required for requesting a connection

         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Parameter             | Description                                                                                                                                                 | Example Value                    |
         +=======================+=============================================================================================================================================================+==================================+
         | Domain Name           | Specifies the account name.                                                                                                                                 | abc123                           |
         |                       |                                                                                                                                                             |                                  |
         |                       | For details about how to obtain the domain name, see :ref:`Obtaining the Domain Name <dc_02_0203>`.                                                         |                                  |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Project ID            | Specifies the project ID. Perform the following operations to obtain the project name.                                                                      | f9578ed9f9b1496da3ddf4ad29ccd891 |
         |                       |                                                                                                                                                             |                                  |
         |                       | #. Hover the cursor over the username in the upper right corner and select **My Credentials** from the drop-down list.                                      |                                  |
         |                       | #. In the lower part of the **My Credentials** page, locate the project.                                                                                    |                                  |
         |                       | #. View the project ID.                                                                                                                                     |                                  |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Provider              | Specifies the carrier that provides the connection.                                                                                                         | others                           |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Region                | Specifies the region where the connection resides.                                                                                                          | eu-de                            |
         |                       |                                                                                                                                                             |                                  |
         |                       | For details about how to obtain the region, see :ref:`Obtaining the Region <dc_02_0204>`.                                                                   |                                  |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Location              | Specifies the location where the connection will be terminated.                                                                                             | Biere/Magdeburg                  |
         |                       |                                                                                                                                                             |                                  |
         |                       | In the **eu-de** region, you can select **Biere** or **Magdeburg**. In the **eu-nl** region, you can select **Amsterdam-Aalsmeer** or **Amsterdam-Almere**. |                                  |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Port Type             | Specifies the port type. The value can be **1GE**, **10GE**, **40GE**, or **100GE**.                                                                        | 40GE                             |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Bandwidth             | Specifies the bandwidth of the connection in the unit of Mbit/s.                                                                                            | 100 Mbit/s                       |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Name                  | Specifies the connection name. The name can contain a maximum of 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.         | directconnect-001                |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+

   b. .. _en-us_topic_0128466510__dc_04_0611_li13212641144613:

      Request the two connections using any of the following methods:

      -  `Email us <https://open-telekom-cloud.com/en/contact>`__ with the title "Applying for Enabling Direct Connect".
      -  `Call us <https://open-telekom-cloud.com/en/contact>`__ and provide the collected information to our customer service.
      -  Contact our sales representative and provide the collected information.

   c. Wait for the notification from your account manager or customer service.

   d. Log in to the management console.

   e. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

   f. In the navigation pane on the left, choose **Direct Connect** > **Connections**.

      View the connections in the connection list.

2. Create a virtual gateway.

   a. In the navigation pane on the left, choose **Direct Connect** > **Virtual Gateways**.
   b. In the upper right corner of the **Virtual Gateways** page, click **Create Virtual Gateway**.
   c. Configure the parameters.

      .. table:: **Table 2** Parameters for creating a virtual gateway

         +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Parameter             | Description                                                                                                        | Example Value              |
         +=======================+====================================================================================================================+============================+
         | Name                  | Specifies the virtual gateway name.                                                                                | vgw-123                    |
         |                       |                                                                                                                    |                            |
         |                       | The name can contain 1 to 64 characters.                                                                           |                            |
         |                       |                                                                                                                    |                            |
         |                       | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
         | VPC                   | Specifies the VPC that you need to access.                                                                         | VPC-001                    |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
         | CIDR Block            | Specifies the CIDR block of the VPC to be accessed using the connection.                                           | 192.168.0.0/16             |
         |                       |                                                                                                                    |                            |
         |                       | You can add a maximum of 50 CIDR blocks. Each pair must be unique. Separate every two CIDR blocks with commas (,). |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Description           | Provides supplementary information about the virtual gateway.                                                      | This is a virtual gateway. |
         |                       |                                                                                                                    |                            |
         |                       | You can enter 0 to 128 characters.                                                                                 |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------+----------------------------+

   d. Click **OK**.

3. Create two virtual interfaces.

   a. .. _en-us_topic_0128466510__li1022162832914:

      In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

   b. On the displayed **Virtual Interfaces** page, click **Create Virtual Interface** in the upper right corner to create the first virtual interface.

   c. Configure the parameters.

      .. _en-us_topic_0128466510__table54552924110:

      .. table:: **Table 3** Parameters for creating a virtual interface

         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Parameter             | Description                                                                                                                                                                                       | Example Value                                                                     |
         +=======================+===================================================================================================================================================================================================+===================================================================================+
         | Region                | Specifies the region in which the services will be handled.                                                                                                                                       | Select **eu-de** for the Germany region and **eu-nl** for the Netherlands region. |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | If you already selected a region and a project on the management console, you do not need to select the region here.                                                                              |                                                                                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Name                  | Specifies the virtual interface name.                                                                                                                                                             | vif-123                                                                           |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | The name can contain 1 to 64 characters.                                                                                                                                                          |                                                                                   |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                                                               |                                                                                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Connection            | Specifies the connection to be associated.                                                                                                                                                        | dc-123                                                                            |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | Select the connection that is connected to Biere or Magdeburg. The locations of the two connections must be different.                                                                            |                                                                                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Virtual Gateway       | Select the virtual gateway to be associated.                                                                                                                                                      | vgw-123                                                                           |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | VLAN                  | Specifies the virtual interface VLAN ID.                                                                                                                                                          | 30                                                                                |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | The system allocates a VLAN ID. You do not need to set this parameter.                                                                                                                            |                                                                                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Bandwidth             | Specifies the virtual interface bandwidth in the unit of Mbit/s.                                                                                                                                  | 100                                                                               |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | If the selected connection is a hosting connection, the virtual interface exclusively uses the connection bandwidth. That is, the connection bandwidth is the bandwidth of the virtual interface. |                                                                                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Remote Subnet         | Specifies the remote subnet using CIDR notation. You can enter a maximum of 50 remote subnets. Each pair must be unique. Separate every two remote subnets with commas (,).                       | 192.168.51.0/24                                                                   |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | The remote subnet of the virtual interface cannot be the same as the VPC CIDR block of the virtual gateway.                                                                                       |                                                                                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Description           | Provides supplementary information about the virtual interface.                                                                                                                                   | This is a virtual interface.                                                      |
         |                       |                                                                                                                                                                                                   |                                                                                   |
         |                       | You can enter 0 to 128 characters.                                                                                                                                                                |                                                                                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+

   d. .. _en-us_topic_0128466510__li13735165074810:

      Click **Create Now**.

   e. Repeat step :ref:`3.a <en-us_topic_0128466510__li1022162832914>` to :ref:`3.d <en-us_topic_0128466510__li13735165074810>` to create the other virtual interface.
