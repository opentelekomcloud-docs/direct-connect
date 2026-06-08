:original_name: dc_03_0804.html

.. _dc_03_0804:

Managing Virtual Interface Tags
===============================

Scenarios
---------

After a virtual interface is created, you can add tags to it, or edit, view or delete its tags.

A tag is the identifier of a virtual interface and consists of a key and a value. You can add 20 tags to a virtual interface.

.. note::

   If a predefined tag has been created in TMS, you can select the corresponding tag key and value.

   For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.

Adding a Tag
------------

You can follow this section to add a tag to an existing virtual interface.

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. Click the name of the virtual interface and click the **Tags** tab.

#. Click **Edit Tag**.

#. On the **Edit Tag** page, click **Add Tag** and enter the tag key and value.

   :ref:`Table 1 <dc_03_0804__table539113432713>` describes the tag key and value requirements.


   .. figure:: /_static/images/en-us_image_0000002429253408.png
      :alt: **Figure 1** Adding a tag to a virtual interface

      **Figure 1** Adding a tag to a virtual interface

   .. _dc_03_0804__table539113432713:

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

You can follow this section to modify the value of a tag added to a virtual interface.

#. Log in to the management console.

#. Click |image2| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. Click the name of the virtual interface and click the **Tags** tab.

#. Click **Edit Tag**.

#. On the **Edit Tag** page, modify the tag key and value of the tag.


   .. figure:: /_static/images/en-us_image_0000002462872773.png
      :alt: **Figure 2** Editing a tag of a virtual interface

      **Figure 2** Editing a tag of a virtual interface

#. Click **OK**.

Deleting a Tag
--------------

You can follow this section to delete a tag from a virtual interface.

.. caution::

   Deleted tags cannot be recovered.

#. Log in to the management console.

#. Click |image3| in the upper left corner and select a region and a project.

#. In the service list in the upper left corner of the page, choose **Network** > **Direct Connect**.

#. In the navigation pane on the left, choose **Direct Connect** > **Virtual Interfaces**.

#. Click the name of the virtual interface and click the **Tags** tab.

#. Click **Edit Tag**.

#. On the **Edit Tag** page, locate the tag to be deleted and click **Delete**.


   .. figure:: /_static/images/en-us_image_0000002463058861.png
      :alt: **Figure 3** Deleting a tag from a virtual interface

      **Figure 3** Deleting a tag from a virtual interface

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002429106732.png
.. |image2| image:: /_static/images/en-us_image_0000002429106732.png
.. |image3| image:: /_static/images/en-us_image_0000002429106732.png
