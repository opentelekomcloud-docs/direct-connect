:original_name: dc_03_0504.html

.. _dc_03_0504:

Managing Connection Tags
========================

Scenarios
---------

After a connection is created, you can view its tags or add, edit or delete a tag.

A tag is the identifier of a connection and consists of a key and a value. You can add a maximum of 20 tags to a connection.

.. note::

   If a predefined tag has been created in TMS, you can select the corresponding tag key and value.

   For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.

Adding a Tag
------------

You can follow this section to add a tag to an existing connection.

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Connections**.

#. Click the name of the connection and click the **Tags** tab.

#. Click **Edit Tag**.

#. On the **Edit Tag** page, click **Add Tag** and enter the tag key and value.

   :ref:`Table 1 <dc_03_0504__table539113432713>` describes the tag key and value requirements.

   .. _dc_03_0504__fig1384381811283:

   .. figure:: /_static/images/en-us_image_0000002571752560.png
      :alt: **Figure 1** Adding a tag to a connection

      **Figure 1** Adding a tag to a connection

   .. _dc_03_0504__table539113432713:

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

You can follow this section to modify the value of a tag added to a connection.

#. Log in to the management console.

#. Click |image2| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Connections**.

#. Click the name of the connection and click the **Tags** tab.

#. Click **Edit Tag**.

#. On the **Edit Tag** page, locate the tag to be modified and enter the new tag key and value.


   .. figure:: /_static/images/en-us_image_0000002556465705.png
      :alt: **Figure 2** Editing a tag of a connection

      **Figure 2** Editing a tag of a connection

#. Click **OK**.

Deleting a Tag
--------------

You can follow this section to delete a tag from a connection.

.. caution::

   Deleted tags cannot be recovered.

#. Log in to the management console.

#. Click |image3| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Connections**.

#. Click the name of the connection and click the **Tags** tab.

#. Click **Edit Tag**.

#. In the tag list, locate the tag you want to delete and click **Delete**.


   .. figure:: /_static/images/en-us_image_0000002556305743.png
      :alt: **Figure 3** Deleting a connection tag

      **Figure 3** Deleting a connection tag

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002429106732.png
.. |image2| image:: /_static/images/en-us_image_0000002429106732.png
.. |image3| image:: /_static/images/en-us_image_0000002429106732.png
