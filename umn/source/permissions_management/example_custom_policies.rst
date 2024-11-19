:original_name: dc_04_0902.html

.. _dc_04_0902:

Example Custom Policies
=======================

Custom policies can be created to supplement the system-defined policies of Direct Connect.

You can create custom policies in either of the following ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Edit JSON policies from scratch or based on an existing policy.

For details about how to create custom policies, see `Creating a Custom Policy <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0016.html>`__. The following section contains examples of common Direct Connect custom policies.


Example Custom Policies
-----------------------

-  Example 1: Allowing users to update a virtual gateway

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "dcaas:vgw:update"
                  ]
              }
          ]
      }

-  Example 2: Denying users to modify a connection

   A policy with only Deny permissions must be used in conjunction with other policies to take effect. If permissions assigned to a user contain both Allow and Deny actions, the Deny action takes precedence over the Allow action.

   The following method can be used if you need to assign permissions of the **DCAAS FullAccess** policy to a user but also forbid the user from modifying connections. Create a custom policy for denying connection modification, and assign both policies to the group the user belongs to. Then the user can perform all operations on Direct Connect except modifying connections.

   The following is an example of a deny policy:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Deny",
                  "Action": [
                      "dcaas:directConnect:update"
                  ]
              }
          ]
      }

-  Example 3: Defining permissions for multiple services in a policy

   A custom policy can contain the actions of multiple services that are of the global or project-level type.

   The following is an example policy containing actions of multiple services:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "vpc:vpcs:list",
                      "vpc:subnets:get",
                      "vpc:routes:list"
                  ]
              },
              {
                  "Effect": "Allow",
                  "Action": [
                      "dcaas:vif:list",
                      "dcaas:vgw:list",
                      "dcaas:directConnect:list"
                  ]
              }
          ]
      }
