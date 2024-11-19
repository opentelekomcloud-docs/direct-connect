:original_name: dc_04_1621.html

.. _dc_04_1621:

Creating a Hosted Connection
============================

Scenarios
---------

If you are a partner, you can create a hosted connection for your user.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Connections**.

#. On the **Connections** page, click **Create Hosted Connection**.

#. Configure the parameters.

   .. _dc_04_1621__dc_04_0621_table27593495173236:

   .. table:: **Table 1** Parameters for creating a hosted connection

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Parameter             | Description                                                                                                                                         | Example Value                    |
      +=======================+=====================================================================================================================================================+==================================+
      | Name                  | Specifies the connection name. The name can contain a maximum of 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed. | directconnect-001                |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Project ID            | Specifies the project ID.                                                                                                                           | f9578ed9f9b1496da3ddf4ad29ccd891 |
      |                       |                                                                                                                                                     |                                  |
      |                       | Specifies the ID of the project to which the hosted connection to be created belongs. The value is provided by the tenant for the partner.          |                                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Operations Connection | Specifies the operations connection on which the hosted connection is created.                                                                      | Operations_connection_test       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Bandwidth             | Specifies the bandwidth of the connection, in Mbit/s.                                                                                               | 2 Mbit/s                         |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Peering Position      | Specifies the physical location of the hosted connection. This address is an identifier.                                                            | "Marderbug-DC01"                 |
      |                       |                                                                                                                                                     |                                  |
      |                       | -  Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                              |                                  |
      |                       | -  It can contain 0 to 64 characters.                                                                                                               |                                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | VLAN                  | Specifies the VLAN of the hosted connection.                                                                                                        | 100                              |
      |                       |                                                                                                                                                     |                                  |
      |                       | The partner allocates the VLAN to the tenant.                                                                                                       |                                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
      | Description           | Provides supplementary information about the hosted connection.                                                                                     | test                             |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0070860784.png
