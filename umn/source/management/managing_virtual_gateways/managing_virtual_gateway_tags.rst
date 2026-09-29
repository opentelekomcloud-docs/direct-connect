:original_name: dc_03_0704.html

.. _dc_03_0704:

Managing Virtual Gateway Tags
=============================

Scenarios
---------

After a virtual gateway is created, you can add tags to it, or edit, view or delete its tags.

A tag is the identifier of a virtual gateway and consists of a key and a value. You can add 20 tags to a virtual gateway.

.. note::

   If a predefined tag has been created in TMS, you can select the corresponding tag key and value.

   For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.

Adding a Tag
------------

You can follow this section to add a tag to an existing virtual gateway.

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Gateways**.

#. Click the name of the virtual gateway to go to its details page.

#. In the **Tags** area in the lower part of the page, click **Edit Tag**.

#. On the **Edit Tag** page, click **Add Tag** and enter the tag key and value.

   :ref:`Table 1 <dc_03_0704__table539113432713>` describes the tag key and value requirements.


   .. figure:: /_static/images/en-us_image_0000002429392042.png
      :alt: **Figure 1** Adding a tag to a virtual gateway

      **Figure 1** Adding a tag to a virtual gateway

   .. _dc_03_0704__table539113432713:

   .. table:: **Table 1** Tag key and value requirements

      +-----------------------------------+---------------------------------------------------------------------------------------------------+
      | Parameter                         | Requirements                                                                                      |
      +===================================+===================================================================================================+
      | Tag key                           | -  Cannot be left blank.                                                                          |
      |                                   | -  Must be unique for each resource.                                                              |
      |                                   | -  Can contain a maximum of 128 Unicode characters.                                               |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.). |
      +-----------------------------------+---------------------------------------------------------------------------------------------------+
      | Tag value                         | -  Can be left blank.                                                                             |
      |                                   | -  Can contain a maximum of 255 Unicode characters.                                               |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), at signs (@), and periods (.). |
      +-----------------------------------+---------------------------------------------------------------------------------------------------+

#. Click **OK**.

Editing a Tag
-------------

You can follow this section to modify the value of a tag added to a virtual gateway.

#. Log in to the management console.

#. Click |image2| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Gateways**.

#. Click the name of the virtual gateway to go to its details page.

#. In the **Tags** area in the lower part of the page, click **Edit Tag**.

#. On the **Edit Tag** page, modify the tag key and value of the tag.


   .. figure:: /_static/images/en-us_image_0000002462722037.png
      :alt: **Figure 2** Editing a tag of a virtual gateway

      **Figure 2** Editing a tag of a virtual gateway

#. Click **OK**.

Deleting a Tag
--------------

You can follow this section to delete a tag from a virtual gateway.

.. caution::

   Deleted tags cannot be recovered.

#. Log in to the management console.

#. Click |image3| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Gateways**.

#. Click the name of the virtual gateway to go to its details page.

#. In the **Tags** area in the lower part of the page, click **Edit Tag**.

#. On the **Edit Tag** page, locate the tag to be deleted and click **Delete**.


   .. figure:: /_static/images/en-us_image_0000002462843981.png
      :alt: **Figure 3** Deleting a tag from a virtual gateway

      **Figure 3** Deleting a tag from a virtual gateway

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002429106732.png
.. |image2| image:: /_static/images/en-us_image_0000002429106732.png
.. |image3| image:: /_static/images/en-us_image_0000002429106732.png
