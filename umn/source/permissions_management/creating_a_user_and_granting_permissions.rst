:original_name: dc_03_0901.html

.. _dc_03_0901:

Creating a User and Granting Permissions
========================================

Use `IAM <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__ for fine-grained permissions control over your resources. With IAM, you can:

-  Create IAM users for employees based on the organizational structure of your enterprise. Each IAM user has their own security credentials, providing access to cloud resources.
-  Grant only the permissions required for users to perform a specific task.
-  Entrust another account or cloud service to perform professional and efficient O&M on your cloud resources.

Skip this part if your account does not require individual IAM users.

The following is the procedure for granting permissions.

Prerequisites
-------------

Before assigning permissions to user groups, you should learn about Direct Connect system policies and select the policies based on service requirements. For details about system-defined permissions of Direct Connect, see :ref:`Permissions <dc_01_0008>`. For system-defined permissions of other cloud services, see `Permissions <https://docs.otc.t-systems.com/permissions/index.html>`__.

Process Flow
------------


.. figure:: /_static/images/en-us_image_0000001562084113.jpg
   :alt: **Figure 1** Process for granting Direct Connect permissions

   **Figure 1** Process for granting Direct Connect permissions

#. .. _dc_03_0901__li1140112579375:

   `Create a user group and assign permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__.

   Create a user group on the IAM console and assign the **DCAAS ReadOnlyAccess** policy to the group.

#. `Create a user and add the user to the user group <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0031.html>`__

   Create a user on the IAM console and add the user to the group created in :ref:`1 <dc_03_0901__li1140112579375>`.

#. `Log in to the management console as the created user <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0032.html>`__.

   Switch to the authorized region and verify the permissions.

   -  Choose **Service List** > **Network** > **Direct Connect**. On the **Connections** page, select a connection and click **Modify** in the **Operation** column to modify the connection. If the connection cannot be modified, **DCAAS ReadOnlyAccess** has taken effect.
   -  Choose any other service in **Service List**. If a message appears indicating that you have insufficient permissions to access the service, the **DCAAS ReadOnlyAccess** policy has already taken effect.
