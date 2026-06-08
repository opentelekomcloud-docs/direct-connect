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
         | Provider              | Specifies the carrier that provides the connection.                                                                                                         | Others                           |
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
         | Bandwidth             | Specifies the bandwidth of the connection, in Mbit/s.                                                                                                       | 100 Mbit/s                       |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
         | Name                  | Specifies the connection name. The name can contain a maximum of 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.         | directconnect-001                |
         +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+

   b. .. _en-us_topic_0128466510__en-us_topic_0000001466100244_li13212641144613:

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

      .. _en-us_topic_0128466510__table128947911279:

      .. table:: **Table 2** Parameters for creating a virtual gateway

         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Parameter             | Description                                                                                                              | Example Value              |
         +=======================+==========================================================================================================================+============================+
         | Name                  | Specifies the virtual gateway name.                                                                                      | vgw-123                    |
         |                       |                                                                                                                          |                            |
         |                       | The name can contain 1 to 64 characters.                                                                                 |                            |
         |                       |                                                                                                                          |                            |
         |                       | Only digits, letters, underscores (_), hyphens (-), and periods (.) are allowed.                                         |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Enterprise Project    | Specifies the enterprise project by which virtual gateways are centrally managed. Select an existing enterprise project. | default                    |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Attach To             | Specifies whether the virtual gateway is associated with a VPC or attached to an enterprise router.                      | VPC                        |
         |                       |                                                                                                                          |                            |
         |                       | In this practice, select **VPC**.                                                                                        |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | VPC                   | Specifies the VPC that you need to access.                                                                               | VPC-001                    |
         |                       |                                                                                                                          |                            |
         |                       | This parameter is mandatory when you set **Attach To** to **VPC**.                                                       |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Local Subnet          | Specifies the VPC CIDR blocks that can be accessed using Direct Connect.                                                 | 192.168.0.0/16             |
         |                       |                                                                                                                          |                            |
         |                       | This parameter is mandatory when you set **Attach To** to **VPC**.                                                       |                            |
         |                       |                                                                                                                          |                            |
         |                       | You can add one or more CIDR blocks. Separate every entry with a comma (,) if there are multiple CIDR blocks.            |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | BGP ASN               | Specifies the BGP ASN used on the cloud.                                                                                 | eu-de region: 65146        |
         |                       |                                                                                                                          |                            |
         |                       | Enter the BGP ASN based on your region.                                                                                  | eu-nl region: 64512        |
         |                       |                                                                                                                          |                            |
         |                       | -  BGP ASN in the **eu-de** region: 65146                                                                                |                            |
         |                       | -  BGP ASN in the **eu-nl** region: 64512                                                                                |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Tag                   | Adds tags to help you identify your virtual gateways. A tag consists of a tag key and a tag value.                       | example_key1               |
         |                       |                                                                                                                          |                            |
         |                       | A maximum of 20 tag key-value pairs are supported.                                                                       | example_value1             |
         |                       |                                                                                                                          |                            |
         |                       | Each tag key:                                                                                                            |                            |
         |                       |                                                                                                                          |                            |
         |                       | -  Cannot be left blank.                                                                                                 |                            |
         |                       | -  Must be unique for each resource.                                                                                     |                            |
         |                       | -  Can contain a maximum of 128 Unicode characters.                                                                      |                            |
         |                       | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.).                        |                            |
         |                       |                                                                                                                          |                            |
         |                       | Each tag value:                                                                                                          |                            |
         |                       |                                                                                                                          |                            |
         |                       | -  Can be left blank.                                                                                                    |                            |
         |                       | -  Can contain a maximum of 255 Unicode characters.                                                                      |                            |
         |                       | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.).                        |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+
         | Description           | Provides supplementary information about the virtual gateway.                                                            | This is a virtual gateway. |
         |                       |                                                                                                                          |                            |
         |                       | You can enter 0 to 128 characters.                                                                                       |                            |
         +-----------------------+--------------------------------------------------------------------------------------------------------------------------+----------------------------+

   d. Click **OK**.

3. Create two virtual interfaces.

   a. .. _en-us_topic_0128466510__li1022162832914:

      In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

   b. On the displayed **Virtual Interfaces** page, click **Create Virtual Interface** in the upper right corner to create the first virtual interface.

   c. Configure the parameters.

      .. _en-us_topic_0128466510__table54552924110:

      .. table:: **Table 3** Parameters for creating a virtual interface

         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Parameter                  | Description                                                                                                                                                                                                                                   | Example Value                                                                     |
         +============================+===============================================================================================================================================================================================================================================+===================================================================================+
         | Region                     | Specifies the region in which the services will be handled.                                                                                                                                                                                   | Select **eu-de** for the Germany region and **eu-nl** for the Netherlands region. |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | If you already selected a region and a project on the management console, you do not need to select the region here.                                                                                                                          |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Name                       | Specifies the virtual interface name.                                                                                                                                                                                                         | vif-123                                                                           |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | The name can contain 1 to 64 characters.                                                                                                                                                                                                      |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                                                                                                           |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Connection                 | Specifies the connection to be associated.                                                                                                                                                                                                    | dc-123                                                                            |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | Select the connection that is connected to Biere or Magdeburg. The locations of the two connections must be different.                                                                                                                        |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Virtual Gateway            | Select the virtual gateway to be associated.                                                                                                                                                                                                  | vgw-123                                                                           |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | VLAN                       | Specifies the virtual interface VLAN ID.                                                                                                                                                                                                      | 30                                                                                |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | -  You need to configure the VLAN if you create a standard connection.                                                                                                                                                                        |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            |    Enter a value from 0 to 3999 based on your network plan. 0 indicates that the connection does not use a VLAN. In this case, only one virtual interface can be created. The VLAN IDs of the cloud and on-premises devices must be the same. |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | -  The VLAN for a hosted connection will be allocated by the carrier or partner. You do not need to configure the VLAN.                                                                                                                       |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Enterprise Project         | Specifies the enterprise project by which virtual interfaces are centrally managed. Select an existing enterprise project.                                                                                                                    | default                                                                           |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Tag                        | Adds tags to help you identify your virtual interfaces. A tag consists of a tag key and a tag value.                                                                                                                                          | example_key1                                                                      |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | A maximum of 20 tag key-value pairs are supported.                                                                                                                                                                                            | example_value1                                                                    |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | Each tag key:                                                                                                                                                                                                                                 |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | -  Cannot be left blank.                                                                                                                                                                                                                      |                                                                                   |
         |                            | -  Must be unique for each resource.                                                                                                                                                                                                          |                                                                                   |
         |                            | -  Can contain a maximum of 128 Unicode characters.                                                                                                                                                                                           |                                                                                   |
         |                            | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.).                                                                                                                                             |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | Each tag value:                                                                                                                                                                                                                               |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | -  Can be left blank.                                                                                                                                                                                                                         |                                                                                   |
         |                            | -  Can contain a maximum of 255 Unicode characters.                                                                                                                                                                                           |                                                                                   |
         |                            | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.).                                                                                                                                             |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Local Gateway              | Specifies the IP address for connecting to the cloud network.                                                                                                                                                                                 | 10.0.x.1/30                                                                       |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Remote Gateway             | Specifies the IP address for connecting to the on-premises network.                                                                                                                                                                           | 10.0.x.2/30                                                                       |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | The IP addresses of the remote gateway and local gateway must be in the same network segment. Generally, a 30-bit mask is used.                                                                                                               |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Remote Subnet              | Specifies the subnets and masks of your network. If multiple remote subnets are available, use commas (,) to separate them.                                                                                                                   | 192.168.51.0/24                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | .. caution::                                                                                                                                                                                                                                  |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            |    CAUTION:                                                                                                                                                                                                                                   |                                                                                   |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            |    -  Remote subnets cannot overlap with local subnets.                                                                                                                                                                                       |                                                                                   |
         |                            |    -  Using 100.64.0.0/10 as the remote subnet may cause services such as OBS, DNS, and API Gateway to become unavailable.                                                                                                                    |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Routing Mode               | Specifies the routing mode. Static routing and BGP routing are supported.                                                                                                                                                                     | BGP                                                                               |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | If there are two or more connections, select BGP routing.                                                                                                                                                                                     |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | BGP ASN                    | Specifies the BGP ASN used on your on-premises network.                                                                                                                                                                                       | 12345                                                                             |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | This parameter is required when BGP routing is selected.                                                                                                                                                                                      |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | BGP MD5 Authentication Key | Specifies the password used to authenticate the BGP peer using MD5. The value is case sensitive and cannot contain spaces.                                                                                                                    | Qaz12345678                                                                       |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | This parameter is mandatory if you select BGP routing, and you must ensure that the parameter values on both gateways are the same.                                                                                                           |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+
         | Description                | Provides supplementary information about the virtual interface.                                                                                                                                                                               | This is a virtual interface.                                                      |
         |                            |                                                                                                                                                                                                                                               |                                                                                   |
         |                            | You can enter 0 to 128 characters.                                                                                                                                                                                                            |                                                                                   |
         +----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------+

   d. .. _en-us_topic_0128466510__li13735165074810:

      Click **Create Now**.

   e. Repeat step :ref:`3.a <en-us_topic_0128466510__li1022162832914>` to :ref:`3.d <en-us_topic_0128466510__li13735165074810>` to create the other virtual interface.
