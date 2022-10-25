:original_name: en-us_topic_0034301493.html

.. _en-us_topic_0034301493:

Creating a Direct Connection
============================

Scenarios
---------

Apply for a direct connection to enable ECSs in your VPC to communicate with your data center or private network.

Procedure
---------

#. Collect the information listed in :ref:`Table 1 <en-us_topic_0034301493__table27593495173236>`.

   .. _en-us_topic_0034301493__table27593495173236:

   .. table:: **Table 1** Parameters required for creating a direct connection

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Parameter             | Description                                                                                                                                                     | Example Value                        |
      +=======================+=================================================================================================================================================================+======================================+
      | Domain Name           | Specifies the domain name. For details about how to obtain the domain name, see :ref:`Obtaining the Domain Name <en-us_topic_0047786739>`.                      | abc123                               |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Region                | Specifies the region where the direct connect is created. For details about how to obtain the region, see :ref:`Obtaining the Region <en-us_topic_0037026650>`. | eu-de                                |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | VPC ID                | Specifies the VPC ID. For details about how to obtain the VPC ID, see :ref:`Obtaining the VPC ID <en-us_topic_0037026651>`.                                     | 13e2e8cb-5894-496c-8688-7b08c485e70b |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Project Name          | Specifies the name of the project to which the direct connection belongs, which can be obtained by performing the following steps:                              | DeC_001                              |
      |                       |                                                                                                                                                                 |                                      |
      |                       | Click the username in the upper right corner and select **My Credential** from the drop-down list.                                                              |                                      |
      |                       |                                                                                                                                                                 |                                      |
      |                       | Under the **Projects** tab, view the project names.                                                                                                             |                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Port Type             | Specifies the port type.                                                                                                                                        | 1GE or 10GE                          |
      |                       |                                                                                                                                                                 |                                      |
      |                       | The value can be **1GE** or **10GE**.                                                                                                                           |                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Local Subnet          | Specifies the subnet segment of the local VPC connected to the direct connection.                                                                               | 192.168.1.0/24,192.168.51.0/24       |
      |                       |                                                                                                                                                                 |                                      |
      |                       | A maximum of 25 local subnets can be configured.                                                                                                                |                                      |
      |                       |                                                                                                                                                                 |                                      |
      |                       | The local subnet and remote subnet cannot be in the same network segment.                                                                                       |                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Remote Subnet         | Specifies the tenant subnet.                                                                                                                                    | 192.168.10.0/24,192.168.52.0/24      |
      |                       |                                                                                                                                                                 |                                      |
      |                       | The value must be a private IP address with a subnet mask. Multiple subnets are separated with commas (,).                                                      |                                      |
      |                       |                                                                                                                                                                 |                                      |
      |                       | A maximum of 50 remote subnets can be configured.                                                                                                               |                                      |
      |                       |                                                                                                                                                                 |                                      |
      |                       | The local subnet and remote subnet cannot be in the same network segment.                                                                                       |                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Bandwidth             | Specifies the bandwidth size.                                                                                                                                   | 10240 Mbit/s                         |
      |                       |                                                                                                                                                                 |                                      |
      |                       | The maximum value is **10240** **Mbit/s.**                                                                                                                      |                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Name                  | Specifies the direct connection name.                                                                                                                           | directconnect-001                    |
      |                       |                                                                                                                                                                 |                                      |
      |                       | The value is a string of no more than 64 characters that can contain letters, digits, underscores (_), and hyphens (-).                                         |                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+

#. Creating a direct connection based on the parameters in :ref:`Table 1 <en-us_topic_0034301493__table27593495173236>` using either of the following methods:

   -  `Send us an email <https://docs.otc.t-systems.com/en-us/public/learnmore.html>`__ with the title "Applying for Creating a Direct Connection".
   -  `Call us <https://docs.otc.t-systems.com/en-us/public/learnmore.html>`__ and provide the collected information to our customer service personnel.
   -  Contact our sales personnel to send the collected information.

#. Wait for the notification of the result from the email, our customer service personnel, or sales personnel.
