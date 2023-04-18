:original_name: en-us_topic_0087378059.html

.. _en-us_topic_0087378059:

Using a Connection to Access Multiple VPCs
==========================================

Scenarios
---------

You can access multiple VPCs using one connection. If you have requested a connection between your on-premises data center (172.16.0.1/24) and VPC A (192.168.0.1/24) and want to access VPC B (192.168.0.1/24), you can create a VPC peering connection to connect the two VPCs, so that your data center can access VPC B. For details, see :ref:`Figure 1 <en-us_topic_0087378059__fig15720121517218>`.

.. _en-us_topic_0087378059__fig15720121517218:

.. figure:: /_static/images/en-us_image_0151999509.png
   :alt: **Figure 1** Accessing multiple VPCs over one connection

   **Figure 1** Accessing multiple VPCs over one connection

.. note::

   Before creating a VPC peering connection, if your connection is requested through email or call, you need to notify the customer manager of the network segments that are to be connected to VPC B. If your connection is created in self-service mode, you need to add the network segments that are to be connected to VPC B to the **CIDR Block** parameter of the virtual gateway.

Procedure
---------

#. Create the peering connection **peering-001** between VPC A and VPC B. If VPC A and VPC B belong to the same tenant, see **Creating a VPC Peering Connection** in `Creating a VPC Peering Connection with Another VPC in Your Account <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0046655037.html>`__. If VPC A and VPC B belong to different tenants, see **Creating a VPC Peering Connection** in `Creating a VPC Peering Connection with a VPC in Another Account <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0046655038.html>`__.

#. Add routes for the VPC peering connection. If VPC A and VPC B belong to the same tenant, see **Adding Routes for the VPC Peering Connection** in `Creating a VPC Peering Connection with Another VPC in Your Account <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0046655037.html>`__. If VPC A and VPC B belong to different tenants, see **Adding Routes for the VPC Peering Connection** in `Creating a VPC Peering Connection with a VPC in Another Account <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0046655038.html>`__.

#. Add a route that points to the remote subnet of the on-premises data center for the VPC peering connection.

   When VPC A and VPC B belong to the same tenant and VPC A is the peer VPC in **peering-001**, you need to add a local route for the peering connection.


   .. figure:: /_static/images/en-us_image_0153233720.png
      :alt: **Figure 2** VPC A being the peer VPC

      **Figure 2** VPC A being the peer VPC

   a. On the **VPC Peering** page, click **peering-001** to view the peering connection settings.
   b. On the displayed page, click the **Local Routes** tab.
   c. Click **Add Local Route**. Set **Destination** to the remote subnet of the connection, that is, **172.16.0.1/24**. The next hop address is the default value.
   d. Click **OK**.

   When VPC A and VPC B belong to the same tenant, and VPC A is the local VPC in **peering-001**, you need to add a peer route for the peer connection.


   .. figure:: /_static/images/en-us_image_0153233718.png
      :alt: **Figure 3** VPC A being the local VPC in the peering connection

      **Figure 3** VPC A being the local VPC in the peering connection

   a. On the **VPC Peering** page, click **peering-001** to view the peering connection settings.
   b. On the displayed page, click the **Peer Routes** tab.
   c. Click **Add Peer Route**. Set **Destination** to the remote subnet of the connection, that is, **172.16.0.1/24**. The next hop address is the default value.
   d. Click **OK**.

   When VPC A and VPC B belong to different tenants, the tenant that has VPC B needs to perform the following operations:

   a. On the **VPC Peering** page, click **peering-001** to view the peering connection settings.
   b. Click **Add Local Route** under the **Local Routes** tab. Set **Destination** to the remote subnet of the connection, that is, **172.16.0.1/24**. The next hop address is the default value.
   c. Click **OK**.
