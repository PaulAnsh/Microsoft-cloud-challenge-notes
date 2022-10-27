# Microsoft-cloud-challenge-notes
Documenting my cloud challenge notes. 


## Build a cloud governance strategy on Azure

Learning objectives:
 1. Make org decisions about your cloud environment by using the cloud adoption framework for azure.
 2. define who can access clpud resources by using axire role-based access control. 
 3. apply a resource lock to prevent accidental deletion of your azure resiurces.
 4. Apply tags to your azure resources to help descibe the purpose. 
 5. control and audit how your resource are created by using Azure Policy. 
 6. Enable governance at scale across multiple Azure susbcriptions bu using Azure blueprints. 
 \
 
## Control access to cloud resources by using Azure role-based access control. 

It's a good secuity practice to grant users only the rights they need to perform their job, and only to relevant resources. Instead of providing access to each indiividual and updating when new resources are crearted, Azure enables you to control access through Azure role-based access control (Azure RBAC).  [https://learn.microsoft.com/en-us/azure/role-based-access-control/overview] 
Azure provides built-in roles that describe common access rules for cloud resources. You can also define your own roles. Each role has an associated set of access permissions that relate to that role. When you assign individuals or groups to one or more roles, they receive all of the associated access permissions.

##How is role-based access control applied to resources?
Role-based access control is applied to a scope, which is a resource or set of resources that this access applies to.

Here's a diagram that shows the relationship between roles and scopes.
![image](https://user-images.githubusercontent.com/74669526/198342081-a94b0191-668d-41e3-977f-5e3777413f43.png)
![image](https://user-images.githubusercontent.com/74669526/198342377-2f76ca26-4b34-4b3f-8ed2-639f8fbed12e.png)


A diagram showing scopes along the Y axis and roles across the X axis. Role and scope combinations each map to a specific kind of user or account, such as an observer or an administrator.

Scopes include:

A management group (a collection of multiple subscriptions).
A single subscription.
A resource group.
A single resource.
Observers, Users managing resources, Admins, and Automated processes illustrate the kinds of users or accounts that would typically be assigned each of the various roles.

When you grant access at a parent scope, those permissions are inherited by all child scopes. For example:

When you assign the Owner role to a user at the management group scope, that user can manage everything in all subscriptions within the management group.
When you assign the Reader role to a group at the subscription scope, the members of that group can view every resource group and resource within the subscription.
When you assign the Contributor role to an application at the resource group scope, the application can manage resources of all types within that resource group, but not other resource groups within the subscription.

##How do I manage Azure RBAC permissions?
You manage access permissions on the Access control (IAM) pane in the Azure portal. This pane shows who has access to what scope and what roles apply. You can also grant or remove access from this pane.

The following screenshot shows an example of the Access control (IAM) pane for a resource group. In this example, Alain Charon has been assigned the Backup Operator role for this resource group.



































Resources: https://learn.microsoft.com/en-us/training/modules/build-cloud-governance-strategy-azure/2-control-access-azure-rbac
