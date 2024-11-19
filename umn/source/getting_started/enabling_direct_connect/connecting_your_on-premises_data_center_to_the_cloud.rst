:original_name: dc_02_0202.html

.. _dc_02_0202:

Connecting Your On-Premises Data Center to the Cloud
====================================================

**Scenarios**
-------------

Establish network connectivity using Direct Connect if cloud servers in your VPC need to communicate with your on-premises data center.

Restrictions and Limitations
----------------------------

100.64.0.0/10 is used in VPCs. Plan the CIDR blocks used in your on-premises data center and on the cloud in advance to ensure that IP addresses of the cloud gateway and your on-premises gateway do not overlap.

.. _dc_02_0202__section22771322171016:

**Procedure**
-------------

#. Collect the information listed in :ref:`Table 1 <dc_02_0202__table27593495173236>`.

   .. _dc_02_0202__table27593495173236:

   .. table:: **Table 1** Information required for requesting a connection

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Parameter             | Description                                                                                                                                         | Example Value                                            |
      +=======================+=====================================================================================================================================================+==========================================================+
      | Domain Name           | Specifies the account name.                                                                                                                         | abc123                                                   |
      |                       |                                                                                                                                                     |                                                          |
      |                       | For details about how to obtain the domain name, see :ref:`Obtaining the Domain Name <dc_02_0203>`.                                                 |                                                          |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Project ID            | Specifies the project ID. Perform the following operations to obtain the project ID.                                                                | f9578ed9f9b1496da3ddf4ad29ccd891                         |
      |                       |                                                                                                                                                     |                                                          |
      |                       | a. Hover the cursor over the username in the upper right corner and select **My Credentials** from the drop-down list.                              |                                                          |
      |                       | b. In the lower part of the **My Credentials** page, locate the project.                                                                            |                                                          |
      |                       | c. View the project ID.                                                                                                                             |                                                          |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Provider              | Specifies the carrier that provides the connection.                                                                                                 | others                                                   |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Region                | Specifies the region where the connection resides.                                                                                                  | eu-nl                                                    |
      |                       |                                                                                                                                                     |                                                          |
      |                       | For details about how to obtain the region, see :ref:`Obtaining the Region <dc_02_0204>`.                                                           |                                                          |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Location              | Specifies the location where the connection will be terminated.                                                                                     | Example location in the eu-de region: Biere              |
      |                       |                                                                                                                                                     |                                                          |
      |                       | Select a location based on the region you have selected.                                                                                            | Example location in the eu-nl region: Amsterdam-Aalsmeer |
      |                       |                                                                                                                                                     |                                                          |
      |                       | -  If you have selected **eu-de**, you can select **Biere** or **Magdeburg** here.                                                                  |                                                          |
      |                       | -  If you have selected **eu-nl**, you can select **Amsterdam-Aalsmeer** or **Amsterdam-Almere** here.                                              |                                                          |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Port Type             | Specifies the port type. The value can be **1GE**, **10GE**, **40GE**, or **100GE**.                                                                | 40GE                                                     |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Bandwidth             | Specifies the bandwidth of the connection, in Mbit/s.                                                                                               | 100 Mbit/s                                               |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Name                  | Specifies the connection name. The name can contain a maximum of 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed. | directconnect-001                                        |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+

#. .. _dc_02_0202__li65995768153645:

   Request a connection using any of the following methods:

   -  `Email us <https://open-telekom-cloud.com/en/contact>`__ with the title "Applying for Enabling Direct Connect".
   -  `Call us <https://open-telekom-cloud.com/en/contact>`__ and provide the collected information to our customer service.
   -  Contact our sales personnel. Send the collected information to our sales personnel.

#. Wait for the notification from your account manager or customer service.

#. Log in to the management console.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Gateways**.

#. In the upper right corner of the **Virtual Gateways** page, click **Create Virtual Gateway**.

#. Configure the parameters.

   .. _dc_02_0202__fig20556163316146:

   .. figure:: /_static/images/en-us_image_0000001662676706.png
      :alt: **Figure 1** Create Virtual Gateway

      **Figure 1** Create Virtual Gateway

   .. _dc_02_0202__table886674631511:

   .. table:: **Table 2** Parameters for creating a virtual gateway

      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+
      | Parameter             | Description                                                                                                   | Example Value              |
      +=======================+===============================================================================================================+============================+
      | Name                  | Specifies the virtual gateway name.                                                                           | vgw-123                    |
      |                       |                                                                                                               |                            |
      |                       | The name can contain 1 to 64 characters.                                                                      |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+
      | Attachment            | Specifies whether the virtual gateway is associated with a VPC or attached to an enterprise router.           | VPC                        |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+
      | VPC                   | Specifies the VPC that the virtual gateway is attached to.                                                    | VPC-001                    |
      |                       |                                                                                                               |                            |
      |                       | This parameter is mandatory when you set **Attachment** to **VPC**.                                           |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+
      | Enterprise Router     | Specifies the enterprise router that the virtual gateway is attached to.                                      | ER-001                     |
      |                       |                                                                                                               |                            |
      |                       | This parameter is mandatory when you set **Attachment** to **Enterprise Router**.                             |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+
      | Local Subnet          | Specifies the VPC CIDR blocks that can be accessed using Direct Connect.                                      | 192.168.x.x/24             |
      |                       |                                                                                                               |                            |
      |                       | This parameter is mandatory when you set **Attachment** to **VPC**.                                           |                            |
      |                       |                                                                                                               |                            |
      |                       | You can add one or more CIDR blocks. Separate every entry with a comma (,) if there are multiple CIDR blocks. |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+
      | BGP ASN               | Specifies the BGP ASN used on the cloud.                                                                      | eu-de region: 65146        |
      |                       |                                                                                                               |                            |
      |                       | Enter the BGP ASN based on your region.                                                                       | eu-nl region: 64512        |
      |                       |                                                                                                               |                            |
      |                       | -  BGP ASN in the **eu-de** region: 65146                                                                     |                            |
      |                       | -  BGP ASN in the **eu-nl** region: 64512                                                                     |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+
      | Description           | Provides supplementary information about the virtual gateway.                                                 | This is a virtual gateway. |
      |                       |                                                                                                               |                            |
      |                       | You can enter 0 to 128 characters.                                                                            |                            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------+

#. Click **OK**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. In the upper right corner of the **Virtual Interfaces** page, click **Create Virtual Interface**.

#. Configure the parameters.


   .. figure:: /_static/images/en-us_image_0000001123249800.png
      :alt: **Figure 2** Create Virtual Interface

      **Figure 2** Create Virtual Interface

   .. _dc_02_0202__d0e975:

   .. table:: **Table 3** Parameters for creating a virtual interface

      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                  | Description                                                                                                                                                      | Example Value         |
      +============================+==================================================================================================================================================================+=======================+
      | Region                     | Specifies the region where the connection resides. You can also change the region in the upper left corner of the console.                                       | eu-nl                 |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                       | Specifies the virtual interface name.                                                                                                                            | vif-123               |
      |                            |                                                                                                                                                                  |                       |
      |                            | The name can contain 1 to 64 characters.                                                                                                                         |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Connection                 | Specifies the connection you use to connect your on-premises data center to the cloud.                                                                           | dc-123                |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Virtual Gateway            | Select an available virtual gateway.                                                                                                                             | vgw-123               |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | VLAN                       | Specifies the virtual interface VLAN ID.                                                                                                                         | 30                    |
      |                            |                                                                                                                                                                  |                       |
      |                            | You need to configure the VLAN if you create a standard connection.                                                                                              |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Bandwidth                  | Specifies the bandwidth that can be used by the virtual interface, in Mbit/s. The maximum bandwidth of a virtual interface cannot exceed that of the connection. | 50                    |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Local Gateway              | Specifies the IP address for connecting to the cloud network.                                                                                                    | 10.0.x.1/30           |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Gateway             | Specifies the IP address for connecting to the on-premises network.                                                                                              | 10.0.x.2/30           |
      |                            |                                                                                                                                                                  |                       |
      |                            | The IP addresses of the remote gateway and local gateway must be in the same network segment. Generally, a 30-bit mask is used.                                  |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Subnet              | Specifies the subnets and masks of your network. If multiple remote subnets are available, use commas (,) to separate them.                                      | 192.168.x.x/24        |
      |                            |                                                                                                                                                                  |                       |
      |                            | .. caution::                                                                                                                                                     | 10.1.x.x/24           |
      |                            |                                                                                                                                                                  |                       |
      |                            |    CAUTION:                                                                                                                                                      |                       |
      |                            |                                                                                                                                                                  |                       |
      |                            |    -  Remote subnets cannot overlap with local subnets.                                                                                                          |                       |
      |                            |    -  Using 100.64.0.0/10 as the remote subnet may cause services such as OBS, DNS, and API Gateway to become unavailable.                                       |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Routing Mode               | Specifies the routing mode. Two options are available, **Static** and **BGP**.                                                                                   | BGP                   |
      |                            |                                                                                                                                                                  |                       |
      |                            | If there are two or more connections, select BGP routing.                                                                                                        |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | BGP ASN                    | Specifies the BGP ASN used on your on-premises network.                                                                                                          | 12345                 |
      |                            |                                                                                                                                                                  |                       |
      |                            | This parameter is required when **Routing Mode** is set to **BGP**.                                                                                              |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | BGP MD5 Authentication Key | Specifies the password used to authenticate the BGP peer using MD5. The value is case sensitive and cannot contain spaces.                                       | 12345678              |
      |                            |                                                                                                                                                                  |                       |
      |                            | This parameter is mandatory if you select BGP routing, and you must ensure that the parameter values on both gateways are the same.                              |                       |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description                | Provides supplementary information about the virtual interface.                                                                                                  | N/A                   |
      +----------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.
