---
title: Integrate with Microsoft Dynamics 365 Field Service
description: Integrate Business Central with Field Service.
ms.date: 02/21/2024
ms.topic: article
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Integrate with Microsoft Dynamics 365 Field Service

Service organizations require a front-to-back application in which finance, inventory, and procurement are tightly coupled with service delivery. They generate financial data with every transaction. Every work order represents cost and revenue, and every resource generates profit and loss. Customer interactions add entries on the general ledger. The integration between [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [field-service-short](includes/field-service-short.md)] streamlines the end-to-end process of managing service operations and ensures a smooth flow of information between the two systems.  

You can easily create and manage work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)], track the progress of service tasks, assign resources, and capture consumption details. When you complete a work order in [!INCLUDE [field-service-short](includes/field-service-short.md)], the integration enables the smooth transfer of data to [!INCLUDE [prod_short](includes/prod_short.md)] for further processing.  

The integration also facilitates the invoicing and fulfillment of work orders in [!INCLUDE [prod_short](includes/prod_short.md)]. You can generate accurate invoices based on the service activities and the consumption recorded in [!INCLUDE [field-service-short](includes/field-service-short.md)].  

By integrating [!INCLUDE [prod_short](includes/prod_short.md)] with [!INCLUDE [field-service-short](includes/field-service-short.md)], you don't have to enter data manually or duplicate efforts. Integration also provides a comprehensive view of service operations and finances, enabling better decision-making and operational efficiency.

## Prerequisites

Because [!INCLUDE [field-service-short](includes/field-service-short.md)] is built on top of Dynamics 365 Sales, you must [set up a connection to Dataverse](/dynamics365/business-central/admin-how-to-set-up-a-dynamics-crm-connection#to-use-the-dataverse-connection-setup-assisted-setup-guide) and [enable integration to Dynamics 365 Sales](/dynamics365/business-central/admin-prepare-dynamics-365-for-sales-for-integration#connection-settings-in-the-setup-guide).

You must download the Field Service Integration app from [AppSource](https://go.microsoft.com/fwlink/?linkid=2277917), and install it in [!INCLUDE [prod_short](includes/prod_short.md)].

### Permissions and security roles for user accounts

When you install the Integration Solution, permissions for the integration user account are configured. If those permissions change, you might need to reset them. To do that, reinstall the Integration Solution from the **Dynamics 365 Connection Setup** page by choosing **Redeploy Integration Solution**. The following sections list the permissions and security roles that the solution deploys for each app.

#### Sales

* Dynamics 365 [!INCLUDE [prod_short](includes/prod_short.md)] Integration Administrator
* Dynamics 365 [!INCLUDE [prod_short](includes/prod_short.md)] Integration User
* Dynamics 365 [!INCLUDE [prod_short](includes/prod_short.md)] Product Availability User

#### Business Central

Users who post project journals must have the following permission set:

* Dynamics 365 Sales Integration

#### Field Service

To use the integrated data, users must have the following security role:

* Business Central Field Service Integration

For example, users must have this role to connect work orders to [!INCLUDE [prod_short](includes/prod_short.md)] for processing.

> [!NOTE]
> Ensure that users are assigned to the standard security roles and profiles in [!INCLUDE [field-service-short](includes/field-service-short.md)].  
>
> To learn more about column security profiles in [!INCLUDE [field-service-short](includes/field-service-short.md)], go to [Field Service security roles](/dynamics365/field-service/users-licenses-permissions#field-service-security-roles).
>
> Administrators must add one of the appropriate column security profiles to users in Power Platform. To learn more, go to [Add teams or users to a column security profile to control access](/power-platform/admin/add-teams-users-field-security-profile).

> [!NOTE]
> To use the **Open in Business Central** action in Sales, you must have the following privileges for the following tables:
>
> * You must have **Read** permissions for the **Dynamics 365 Business Central Connection** (nav_connection) table.
> * You must have **Read**, **Write**, and **Delete** permissions for the **Default Dynamics 365 Business Central Connection** (nav_defaultconnection) table.

### Other settings in Field Service

On the **Field Service Setting** page, make the following changes:

* On the **Purchase** tab, clear the **Use of Products Out of Stock** field. Otherwise, you might get an "out of stock" warning when you choose a product that's out of stock in [!INCLUDE [field-service-short](includes/field-service-short.md)], but is in stock in [!INCLUDE [prod_short](includes/prod_short.md)].
* On the **Work Order / Booking** tab, turn off the **Calculate Price** and **Calculate Cost** toggles. In the **Work Order Invoice Creation** field, choose **Never**.

> [!NOTE]
> Setting up a connection to [!INCLUDE [field-service-short](includes/field-service-short.md)] removes the coupling between resources and products. To make [!INCLUDE [prod_short](includes/prod_short.md)] items available in [!INCLUDE [field-service-short](includes/field-service-short.md)], update the **Field Service Product Type** field to match the **Type** field on the items in [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Create a product or service](/dynamics365/field-service/create-product-or-service#create-a-product-or-service).

## Set up the integration in Business Central

After you have a connection to Dataverse and Sales, you can set up your integration to [!INCLUDE [field-service-short](includes/field-service-short.md)].

* Download and install the Field Service Integration app from [AppSource](https://go.microsoft.com/fwlink/?linkid=2277917). Afterward, on the **Extension Management** page, find the Field Service Integration app, and choose the **Set up** action to run the assisted setup guide.
* On the **Assisted Setup** page in [!INCLUDE [prod_short](includes/prod_short.md)], choose **Set up integration to Dynamics 365 Field Service** to run the assisted setup guide.

This section describes the key settings in the guide.

To let people post consumption of items and services in [!INCLUDE [field-service-short](includes/field-service-short.md)] work orders, specify the **Project Journal Template** and **Project Journal Batch** to use to post consumption of products and services.

Because services are expressed in duration in [!INCLUDE [field-service-short](includes/field-service-short.md)], specify the **Hours Unit of Measure** to use to convert durations to quantities in [!INCLUDE [prod_short](includes/prod_short.md)].

You can also specify when work order products and service lines synchronize to [!INCLUDE [prod_short](includes/prod_short.md)]. For example, they might synchronize when work order lines are used, or when someone completes a work order. Choose the appropriate option in the **Synchronize work order products/services** field.

After work order products and services synchronize to project journals in [!INCLUDE [prod_short](includes/prod_short.md)], you can choose whether to post the project journals manually. Choose the appropriate option in the **Automatically post project journals lines** field:

* When a work order is complete.
* When work order products or services are used.

After you finish the setup, run a full synchronization from the **Dynamics 365 Field Service Integration Setup** page. This action synchronizes table mappings for things like:

* Project tasks for projects with the **Apply Usage Link** set. This synchronization makes [!INCLUDE [prod_short](includes/prod_short.md)] projects available for selection in [!INCLUDE [field-service-short](includes/field-service-short.md)].
* Resources that aren't blocked, don't have **Use Time Sheet** selected, and do have **Hours** specified as the unit of measure on the **Dynamics 365 Field Service Integration Setup** page.
* Service items (requires that you're using the Premium experience in [!INCLUDE [prod_short](includes/prod_short.md)]).

## Standard Field Service entity mapping for synchronization

The basis of synchronizing data is mapping the tables and fields in [!INCLUDE [prod_short](includes/prod_short.md)] with tables and columns in Dataverse, so they can exchange the data. Mapping happens through integration tables. To learn more about table mappings, go to [Mapping the Tables and Fields to Synchronize](/dynamics365/business-central/admin-how-to-modify-table-mappings-for-synchronization).

Integration with [!INCLUDE [field-service-short](includes/field-service-short.md)] introduces the following standard integration table mappings:

* **PJLINE-WORDERPRODUCT** - Maps work order products in [!INCLUDE [field-service-short](includes/field-service-short.md)] to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)].
* **PJLINE-WORDERSERVICE** - Maps work order services in [!INCLUDE [field-service-short](includes/field-service-short.md)] to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)].
* **PROJECTTASK** - Maps projects and project tasks in [!INCLUDE [prod_short](includes/prod_short.md)] to products in external projects in [!INCLUDE [field-service-short](includes/field-service-short.md)].
* **RESOURCE-BOOKABLERSC** - Maps resources in [!INCLUDE [prod_short](includes/prod_short.md)] to bookable resources in [!INCLUDE [field-service-short](includes/field-service-short.md)].
* **SVCITEM-CUSTASSET** - (Premium Experience only) Maps service items in [!INCLUDE [prod_short](includes/prod_short.md)] to customer assets in [!INCLUDE [field-service-short](includes/field-service-short.md)].

## Use data in both applications

The following sections describe the features where you can use the data that comes from [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [field-service-short](includes/field-service-short.md)].

### Field Service

You can [create work orders](/dynamics365/field-service/create-work-order) using the **Service Account** and **Billing Account** from [!INCLUDE [prod_short](includes/prod_short.md)]. On work orders, you must select the **Business Central Project Task** in the **External Project** field. Selecting a project lets you synchronize work order products and services to the appropriate project task in [!INCLUDE [prod_short](includes/prod_short.md)].

You can add inventory and noninventory items as **Work Order Products** on work orders and get the quantity on hand and costs and prices from [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Create a work order from the work order form and record list](/dynamics365/field-service/create-work-order#create-a-work-order-from-the-work-order-form-and-record-list).

You can add items of the type service as **Work Order Services**, and get costs and prices from [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Products and services tab](/dynamics365/field-service/work-order-experience#products-and-services-tab).

> [!NOTE]
> When a product or service's status on a work order changes from **Estimated** to **Used** in [!INCLUDE [field-service-short](includes/field-service-short.md)], they'll synchronize to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)].

You can book a resource and relate the **Bookings** to work order services using a **Bookable Resource** from [!INCLUDE [prod_short](includes/prod_short.md)].

You can integrate [field-service-short](includes/field-service-short.md)] warehouses with locations in [!INCLUDE [prod_short](includes/prod_short.md)]. The integration gives technicians information about the availability of a product or item at a specific location. The data synchronizes through a unidirectional (from [!INCLUDE [prod_short](includes/prod_short.md)]) integration table mapping between locations in [!INCLUDE [prod_short](includes/prod_short.md)] and warehouses in [!INCLUDE [field-service-short](includes/field-service-short.md)]. To use the integration table mapping, in [!INCLUDE [prod_short](includes/prod_short.md)] you must turn on the **Location Mandatory** toggle on the **Inventory Setup** page.

[!INCLUDE [prod_short](includes/prod_short.md)] synchronizes locations with the following settings on the **Location Card** page:

* The **Use as In-Transit** toggle is turned off.
* **Project Consump. Whse. Handling** is different from Warehouse Pick (mandatory)
* **Assm. Consump. Whse. Handling** is different from Warehouse Pick (mandatory)

You can use **Open in Business Central** in [!INCLUDE [field-service-short](includes/field-service-short.md)] to open a location in [!INCLUDE [prod_short](includes/prod_short.md)] that's coupled to a warehouse in [!INCLUDE [field-service-short](includes/field-service-short.md)].

### Business Central

Depending on your settings on the **Field Service Integration Setup** page, when work orders include products and services, consumption information is transferred and posted using a **Project Journal** in [!INCLUDE [prod_short](includes/prod_short.md)].

The **Quantity To Bill** and **Duration To Bill** values are copied to the **Qty- to Transfer to Invoice** field. Based on those values, you can create and post sales invoices in [!INCLUDE [prod_short](includes/prod_short.md)] to invoice the customer. After the invoice is posted, or consumption is processed in [!INCLUDE [prod_short](includes/prod_short.md)], the quantity invoiced and quantity consumed display on the [!INCLUDE [prod_short](includes/prod_short.md)] tab on the **Work Order Product** and **Work Order Service** pages.  

Use the **Project Planning Lines** page to track posting and invoicing of consumption on work orders. From the **Project Planning Lines** page, you can create and post sales invoices in [!INCLUDE [prod_short](includes/prod_short.md)]. Afterward, you can synchronize them with [!INCLUDE [field-service-short](includes/field-service-short.md)] and keep track of the status of the invoices.

> [!NOTE]
> Work order services with a booking that uses a bookable resource that's coupled to a [!INCLUDE [prod_short](includes/prod_short.md)] resource synchronize to two project journal lines: one line of type **Budget** for the coupled resource, and another line of type **Billable** for the item being serviced.
>
> The product that's chosen on the work order service must be coupled to an item of the type **Service** in [!INCLUDE [prod_short](includes/prod_short.md)]. Also, the base unit of measure for the item must be set to the **Hours Unit of Measure** that's chosen on the **Dynamics 365 Field Service Integration Setup** page.
>
> You can create an invoice for an item of the type **Service** from the billable project planning line, and use the budget project planning line to register cost with the resource.

Use the **Locations in Field Service** action on the **Locations** and **Location Card** pages to open a coupled location in [!INCLUDE [field-service-short](includes/field-service-short.md)], synchronize it, set up and delete couplings, and view synchronization logs. You can view the allocated product quantity from work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] as part of the gross requirements in Business Central's inventory availability calculation. Demand generated by orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] automatically become an input for planning.

## See also

[Integrate with Microsoft Dataverse via data sync](admin-common-data-service.md)  
[Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md)