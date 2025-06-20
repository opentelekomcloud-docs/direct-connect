:original_name: dc_08_3001.html

.. _dc_08_3001:

Introduction
============

This topic describes fine-grained permissions management for Direct Connect. If your cloud account does not need individual Identity and Access Management (IAM) users, you can skip over this chapter.

By default, new IAM users do not have permissions assigned. You need to add a user to one or more groups, and attach permissions policies or roles to these groups. Users inherit permissions from the groups to which they are added and can perform specified operations on cloud services based on the permissions.

You can grant users permissions by using roles and policies. Roles are a type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   Policy-based authorization is useful if you want to allow or deny the access to an API.

An account has all the permissions required to call all APIs, but IAM users must be assigned the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully. For example, if an IAM user wants to query the connections using an API, the user must have been granted permissions that allow the **dcaas:directConnect:list** action.

Supported Actions
-----------------

IAM provides system-defined policies that can be directly used. You can also create custom policies to work with system-defined policies for more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: Statements in a policy that allow or deny certain operations.
-  APIs: REST APIs that can be called by a user who has been granted specific permissions.
-  Actions: Specific operations that are allowed or denied.
-  IAM or enterprise projects: Type of projects for which an action will take effect. Policies that contain actions for both IAM and enterprise projects can be used and take effect for both IAM and Enterprise Management. Policies that only contain actions for IAM projects can be used and only take effect for IAM. For details about the differences between IAM projects and enterprise projects, see "What Are the Differences Between IAM and Enterprise Management?" in the *Identity and Access Management User Guide*.

   .. note::

      The check mark (Y) and cross symbol (x) indicate that an action takes effect or does not take effect for the corresponding type of projects.

Direct Connect supports the following actions that can be defined in custom policies:

-  :ref:`Connections <dc_08_3002>`: contains actions supported by the APIs of Direct Connect connections, for example, creating a connection.
-  :ref:`Virtual Gateways <dc_08_3003>`: contains actions supported by the APIs of Direct Connect virtual gateway, such as creating a virtual gateway.
-  :ref:`Virtual Interfaces <dc_08_3004>`: contains actions supported by the APIs of Direct Connect virtual interfaces, for example, creating a virtual interface.
