---
title: Integrate with Microsoft Dynamics 365 Field Service
description: Integrate Business Central with Field Service.
ms.date: 05/08/2025
ms.topic: how-to
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Integrate with Microsoft Dynamics 365 Field Service

Service organizations require a front-to-back application in which finance, inventory, and procurement are tightly coupled with service delivery. Every work order represents cost or revenue, and every resource generates profit or loss in the general ledger. The integration between [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [field-service-short](includes/field-service-short.md)] streamlines the end-to-end process of managing service operations and ensures a smooth flow of information between the two applications.  

You can easily create and manage work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)], track the progress of service tasks, assign resources, and capture consumption details. When you complete a work order in [!INCLUDE [field-service-short](includes/field-service-short.md)], the integration enables the smooth transfer of data to [!INCLUDE [prod_short](includes/prod_short.md)] for further processing.  

The integration also lets you invoice and fulfill work orders in [!INCLUDE [prod_short](includes/prod_short.md)]. You can generate accurate invoices based on the service activities and the consumption recorded in [!INCLUDE [field-service-short](includes/field-service-short.md)].  

By integrating [!INCLUDE [prod_short](includes/prod_short.md)] with [!INCLUDE [field-service-short](includes/field-service-short.md)], you don't have to enter data manually or duplicate efforts. Integration also provides a comprehensive view of service operations and finances, enabling better decision-making and operational efficiency.

## Types of integrations

Depending on the business processes you need, you can integrate [!INCLUDE [field-service-short](includes/field-service-short.md)] with project management features only, or project management and service management features in [!INCLUDE [prod_short](includes/prod_short.md)].

> [!NOTE]
> The project and service management integration requires that you're using the Premium experience. Service management features aren't available in the Essential experience.
>
> The option to integrate with project management and service management is a package deal. That is, you can't integrate with service management features only. The option always integrates both sets of features.

For example, integrating [!INCLUDE [field-service-short](includes/field-service-short.md)] with project management lets you sync work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] with project journals in [!INCLUDE [prod_short](includes/prod_short.md)]. You can then use the project journal to post, for example, resource usage from the work order to the general ledger.

In addition to that, integrating [!INCLUDE [field-service-short](includes/field-service-short.md)] with both project and service management also gives you:

- Better scheduling and dispatching of service technicians based on their skills and ability.
- Improved tracking of repair parts and supplies for services.
- Accurate service estimates and invoices.

## Prerequisites

> [!NOTE]
> Most of these prerequisites apply to both types of integrations. However, there are some extra settings to integrate with service management features. To learn more about the settings, go to [Set up the integration with service management features](#set-up-the-integration-with-service-management-features).

### Integrate with Dataverse and Dynamics 365 Sales

To integrate with [!INCLUDE [field-service-short](includes/field-service-short.md)], you must:

- [Set up a connection to Dataverse](/dynamics365/business-central/admin-how-to-set-up-a-dynamics-crm-connection#to-use-the-dataverse-connection-setup-assisted-setup-guide).
- [Enable integration to Dynamics 365 Sales](/dynamics365/business-central/admin-prepare-dynamics-365-for-sales-for-integration#connection-settings-in-the-setup-guide).

### Install required apps

You must download the following apps from AppSource, and install them in your [!INCLUDE [prod_short](includes/prod_short.md)] environment:

- [Field Service Integration](https://go.microsoft.com/fwlink/?linkid=2277917)
- [Business Central Virtual Table](https://go.microsoft.com/fwlink/?linkid=2304910)

> [!NOTE]
> The [!INCLUDE [prod_short](includes/prod_short.md)] Virtual Table app is optional. You only need it if you want to view information about item availability from [!INCLUDE [prod_short](includes/prod_short.md)] in [!INCLUDE [field-service-short](includes/field-service-short.md)]. To learn more, go to [Make item availability information in Business Central available in Field Service](#make-item-availability-information-in-business-central-available-in-field-service).

### Assign permissions and security roles to user accounts

When you install the Integration Solution, permissions for the integration user account are configured. The following sections list the permissions and security roles that the solution deploys for each app.

> [!TIP]
> If those permissions change, you might need to reset them. To do that, reinstall the Integration Solution from the **Dynamics 365 Connection Setup** page by choosing **Redeploy Integration Solution**.

#### Sales

- Dynamics 365 [!INCLUDE [prod_short](includes/prod_short.md)] Integration Administrator
- Dynamics 365 [!INCLUDE [prod_short](includes/prod_short.md)] Integration User
- Dynamics 365 [!INCLUDE [prod_short](includes/prod_short.md)] Product Availability User

#### Business Central

Users who post project journals must have the following permission set:

- Dynamics 365 Sales Integration

> [!NOTE]
> To integrate with project and service management, you must be using the **Premium** experience, which requires a license. To learn more about the license, go to the [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544). When you have the license, on the **Company Information** page in [!INCLUDE [prod_short](includes/prod_short.md)], set the **User Experience** field to **Premium**.

#### Field Service

To use the integrated data, users must have the following security role:

- Business Central Field Service Integration

For example, users must have this role to connect work orders to [!INCLUDE [prod_short](includes/prod_short.md)] for processing.

> [!NOTE]
> Ensure that users are assigned to the standard security roles and profiles in [!INCLUDE [field-service-short](includes/field-service-short.md)].  
>
> To learn more about column security profiles in [!INCLUDE [field-service-short](includes/field-service-short.md)], go to [Field Service security roles](/dynamics365/field-service/users-licenses-permissions#field-service-security-roles).
>
> Administrators must add one of the appropriate column security profiles to users in Power Platform. To learn more, go to [Add teams or users to a column security profile to control access](/power-platform/admin/add-teams-users-field-security-profile).

> [!NOTE]
> To use the **Open in Business Central** action in Sales, you must have the following permissions for the following tables:
>
> - You must have **Read** permissions for the **Dynamics 365 Business Central Connection** (nav_connection) table.
> - You must have **Read**, **Write**, and **Delete** permissions for the **Default Dynamics 365 Business Central Connection** (nav_defaultconnection) table.

## Set up the integration in Business Central

After you have a connection to Dataverse and Sales, you can set up your integration to [!INCLUDE [field-service-short](includes/field-service-short.md)].

### Install the integration app, and run an assisted setup guide

1. Download and install the **Field Service Integration** app from [AppSource](https://go.microsoft.com/fwlink/?linkid=2277917). Afterward, on the **Extension Management** page, find the **Field Service Integration** app, and choose the **Set up** action to run the assisted setup guide.
2. On the **Assisted Setup** page in [!INCLUDE [prod_short](includes/prod_short.md)], choose **Set up integration to Dynamics 365 Field Service** to run the assisted setup guide.

The following list points out the key settings in the guide.

- To let people post consumption of items and services in [!INCLUDE [field-service-short](includes/field-service-short.md)] work orders, specify the **Project Journal Template** and **Project Journal Batch** to use to post consumption of products and services.
- Because services are expressed in duration in [!INCLUDE [field-service-short](includes/field-service-short.md)], specify the **Hours Unit of Measure** to use to convert durations to quantities in [!INCLUDE [prod_short](includes/prod_short.md)].
- You can also specify when work order products and service lines synchronize to [!INCLUDE [prod_short](includes/prod_short.md)]. For example, they might synchronize when work order lines are used, or when someone completes a work order. Choose the appropriate option in the **Synchronize work order products/services** field.
- After work order products and services synchronize to project journals in [!INCLUDE [prod_short](includes/prod_short.md)], you can choose whether to post the project journals manually. Choose the appropriate option in the **Automatically post project journals lines** field:

   - When a work order is complete
   - When work order products or services are used

- Specify the **Integration Type** to integrate with project features only, or both project management and service management. The latter requires that you're using the Premium experience. To learn more, go to [Types of integrations](#types-of-integrations).
- Optionally, if you want to enable technicians to view information about item availability from work orders, choose the **Install Business Central Virtual Table app** link.

### Run a full synchronization

After you finish the setup, run a full synchronization from the **Dynamics 365 Field Service Integration Setup** page. This action synchronizes table mappings for things like:

- Project tasks for projects with the **Apply Usage Link** set. This synchronization makes [!INCLUDE [prod_short](includes/prod_short.md)] projects available for selection in [!INCLUDE [field-service-short](includes/field-service-short.md)].
- Resources that aren't blocked, don't have **Use Time Sheet** selected, and do have **Hours** specified as the unit of measure on the **Dynamics 365 Field Service Integration Setup** page.
- Service-related documents, items, and entries (requires that you're using the Premium experience in [!INCLUDE [prod_short](includes/prod_short.md)]).

#### Integration table mappings for synchronization

The basis of synchronizing data is mapping the tables and fields in [!INCLUDE [prod_short](includes/prod_short.md)] with tables and columns in Dataverse so they can exchange the data. Mapping happens through integration tables. To learn more about table mappings, go to [Mapping the Tables and Fields to Synchronize](/dynamics365/business-central/admin-how-to-modify-table-mappings-for-synchronization).

When you finish the assisted setup guide, integration mappings are created. The following integration table mappings install if you choose the **Project (default)** integration type.

|Integration table mapping  |Data the mapping synchronizes  |
|---------|---------|
|**PJLINE-WORDERPRODUCT** | Maps work order products in [!INCLUDE [field-service-short](includes/field-service-short.md)] to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)].  |
|**PJLINE-WORDERSERVICE** |  Maps work order services in [!INCLUDE [field-service-short](includes/field-service-short.md)] to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)].  |
|**PROJECTTASK** |  Maps projects and project tasks in [!INCLUDE [prod_short](includes/prod_short.md)] to products in external projects in [!INCLUDE [field-service-short](includes/field-service-short.md)].  |
|**RESOURCE-BOOKABLERSC**  | Maps resources in [!INCLUDE [prod_short](includes/prod_short.md)] to bookable resources in [!INCLUDE [field-service-short](includes/field-service-short.md)]. This mapping can also include resources that are users, which requires a few settings. To learn more, go to [Synchronize resources that are people as bookable resources](#synchronize-resources-that-are-people-as-bookable-resources).   |
|**LOCATIONS**     |  Maps locations in [!INCLUDE [prod_short](includes/prod_short.md)] to warehouses in [!INCLUDE [field-service-short](includes/field-service-short.md)]. <br><br> **Note:** The **LOCATIONS** integration table mapping is available only if you turn on the **Location Mandatory** toggle on the **Inventory Setup** page.      |

The following integration table mappings install if you choose the **Project and Service** integration type.

|Integration table mapping  |Data the mapping synchronizes  |
|---------|---------|
|**SRVORDER**| Maps service orders in [!INCLUDE [prod_short](includes/prod_short.md)] to work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)], including the status of the orders. |
|**SRVORDERITEMLINE**| Maps service item lines in [!INCLUDE [prod_short](includes/prod_short.md)] to work order incidents in [!INCLUDE [field-service-short](includes/field-service-short.md)].|
|**SRVORDERLINE-ITEM**| Maps items on service order lines in [!INCLUDE [prod_short](includes/prod_short.md)] with work order products in [!INCLUDE [field-service-short](includes/field-service-short.md)]. |
|**SRVORDERLINE-RESOURCE**| Maps resources on service order lines in [!INCLUDE [prod_short](includes/prod_short.md)] with bookable resource booking in [!INCLUDE [field-service-short](includes/field-service-short.md)].|
|**SRVORDERLINE-SERVICE**|Maps service lines in [!INCLUDE [prod_short](includes/prod_short.md)] with work order services in [!INCLUDE [field-service-short](includes/field-service-short.md)]. |
|**SRVORDERTYPE**| Maps service order types in [!INCLUDE [prod_short](includes/prod_short.md)] to work order types in [!INCLUDE [field-service-short](includes/field-service-short.md)].|
|**SVCITEM-CUSTASSET**|Maps service items in [!INCLUDE [prod_short](includes/prod_short.md)] with customer assets in [!INCLUDE [field-service-short](includes/field-service-short.md)].|

> [!NOTE]
> The integration also maps fields that show item availability information in [!INCLUDE [prod_short](includes/prod_short.md)] on work orders and products in [!INCLUDE [field-service-short](includes/field-service-short.md)]. However, the mapping happens through a virtual table, and not an integration table. Some setup is required. To learn more about virtual tables and viewing item availability, go to [Optional: Make item availability information in Business Central available in Field Service](#optional-make-item-availability-information-in-business-central-available-in-field-service).

> [!TIP]
> To enable technicians who work with the data on mobile devices, you must synchronize resources of the type **Person** in [!INCLUDE [prod_short](includes/prod_short.md)] with a **User** resource type in [!INCLUDE [field-service-short](includes/field-service-short.md)]. To learn more, go to [Synchronize resources that are people with bookable resources](#synchronize-resources-that-are-people-with-bookable-resources).

## Set up the integration in Field Service

On the **Field Service Setting** page, make the following changes:

- On the **Purchase** tab, clear the **Use of Products Out of Stock** field. Otherwise, you might get an "out of stock" warning when you choose a product that's out of stock in [!INCLUDE [field-service-short](includes/field-service-short.md)], but is in stock in [!INCLUDE [prod_short](includes/prod_short.md)].
- On the **Work Order / Booking** tab, turn off the **Calculate Price** and **Calculate Cost** toggles. In the **Work Order Invoice Creation** field, choose **Never**.

## Synchronize resources that are people with bookable resources

You can synchronize resources of the type **Person** in [!INCLUDE [prod_short](includes/prod_short.md)] with bookable resources in [!INCLUDE [field-service-short](includes/field-service-short.md)] that are the **User** type. The synchronization is bi-directional.

> [!NOTE]
> On the **Integration Table Mapping** page, by default, for the **RESOURCE-BOOKABLESC** mapping the **Resource Type** field contains **Generic|Account|Equipment|User**. If you're upgrading your existing integration, you might have to add that value.

1. On the **User Setup** page, add an email address for the user that you want to link with the bookable resource. The address must match the address from the user on the tenant where your Dataverse environment is located.
1. On the **Resource Card** page, in the **Time Sheet Owner User ID** field, choose the user.
1. Synchronize the resource manually, or wait until the job queue synchronizes resources with bookable resources.
1. To verify the synchronization, in [!INCLUDE [field-service-short](includes/field-service-short.md)], open the **Bookable Resource** page and find the resource.

## Integrate project and service management features

Integrating [!INCLUDE [prod_short](includes/prod_short.md)] with [!INCLUDE [field-service-short](includes/field-service-short.md)] lets you manage service tasks, consumption, and financial transactions to benefit service technicians, service managers, and finance teams. It's a powerful solution for managing work orders and consumption in [!INCLUDE [field-service-short](includes/field-service-short.md)] and efficiently invoicing and fulfilling them in [!INCLUDE [prod_short](includes/prod_short.md)]. The integration is bi-directional, meaning that when you enter or change data in either app, the data updates in the other.

> [!NOTE]
> When you enable the integration with service management features, you also enable the integration with projects. You can't enable only the service management integration.

### Set up the integration with service management features

You can enable the integration in the **Integration Type** field by selecting **Project and Service** in the following places:

- In the **Set up integration to Dynamics 365 Field Service** assisted setup guide.
- On the **Dynamics 365 Field Service Integration Setup** page.

When the **Integration Type** field is set to **Project and Service**, the following things happen when you enable the integration:

- Creates a solution in Power Apps named **Microsoft Dynamics 365 Business Central Field Service Integration (service)**.
- Adds integration table mappings for service order types, service documents, service lines, and service item lines. To learn more about the table mappings, go to [Integration table mappings for synchronization](#integration-table-mappings-for-synchronization).
- Fields in the headers on service orders and work orders transfer information, such as the **Service Account**, **Billing Account**, and **Work Order Type**.
- **Service Item Lines** and **Work Order Incidents** in [!INCLUDE [field-service-short](includes/field-service-short.md)] transfer information about the customer assets being repaired.
- **Service Line** fields and **Work Order Products** and **Work Order Services** fields, such as **Qty. to Ship**, **Qty. to Invoice**, and **Qty. to Consume**.

In [!INCLUDE [prod_short](includes/prod_short.md)], make the following settings on the **Service Management Setup** page:

- Turn on the **Service Order Type Mandatory** toggle. This setting is required because [!INCLUDE [field-service-short](includes/field-service-short.md)] requires a work order type.
- Make sure that the number series you use for service orders is set up to allow manual numbering. On the **No. Series** page, select the **Manual Nos.** checkbox for the number series. Manual numbering lets you create work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] and synchronize them with service orders. [!INCLUDE [prod_short](includes/prod_short.md)] uses the order number from [!INCLUDE [field-service-short](includes/field-service-short.md)].
- Turn off the **One Service Item Line/Order** toggle. This setting lets you have more than one work item line.
- Turn on the **Archive Orders** toggle.
- Make the **Service Order Type** field on service orders mandatory because the **Work Order Type** is mandatory on [!INCLUDE [field-service-short](includes/field-service-short.md)] work orders.

If you choose **Enable Inventory Availability by Location** when you set up the integration, you can view the allocated product quantity from work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] as part of the gross requirements in [!INCLUDE [prod_short](includes/prod_short.md)]'s inventory availability calculation. Demand generated by orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] automatically becomes input for planning through synchronized service orders.

The status of service and work orders changes as they progress toward completion. The following table shows how the statues align in both apps.

|[!INCLUDE [prod_short](includes/prod_short.md)] status  |[!INCLUDE [field-service-short](includes/field-service-short.md)] status  | Alignment |
|---------|-----------|---------|
|Pending  |Unscheduled| Bidirectional per mapping to account for item demand. |
|Pending  |Scheduled  | [!INCLUDE [field-service-short](includes/field-service-short.md)] to [!INCLUDE [prod_short](includes/prod_short.md)]. Synchronizes the quantity to ship and the quantity to invoice.|
|In process | In progress | [!INCLUDE [field-service-short](includes/field-service-short.md)] to [!INCLUDE [prod_short](includes/prod_short.md)]. Synchronizes the quantity to ship and the quantity to invoice. |
|Finished | Completed     | [!INCLUDE [field-service-short](includes/field-service-short.md)] to [!INCLUDE [prod_short](includes/prod_short.md)]. Ready for posting in Business Central. |
|Finished | Posted        | [!INCLUDE [field-service-short](includes/field-service-short.md)] to [!INCLUDE [prod_short](includes/prod_short.md)]. When fully invoiced or deleted after partial invoicing in [!INCLUDE [prod_short](includes/prod_short.md)].|
|N/A     | Canceled      | Not synchronized. Manual alignment is needed for canceled work orders. |

### Upgrade your integration to include service management features

If you set up the integration to only include projects, but decide to add service management features later, that's easy to do in just a few steps. Remember that you must be using the Premium experience.

1. On the **Dynamics 365 Field Service Integration Setup** page, turn off the **Enabled** toggle.
1. In the **Integration Type** field, choose **Project and Service**.
1. Turn on the **Enabled** toggle.

## Optional: Make item availability information in Business Central available in Field Service

When technicians prepare work orders, it's helpful that they're sure that the items they need to do the work are available. This section describes how to set up things so people can view item availability information from [!INCLUDE [prod_short](includes/prod_short.md)] in [!INCLUDE [field-service-short](includes/field-service-short.md)].

### Synchronize location and warehouse data

You can integrate [!INCLUDE [field-service-short](includes/field-service-short.md)] warehouses with locations in [!INCLUDE [prod_short](includes/prod_short.md)]. The integration gives technicians information about the availability of a product or item at a specific location.

The data synchronizes from [!INCLUDE [prod_short](includes/prod_short.md)] through a unidirectional integration table mapping between locations in [!INCLUDE [prod_short](includes/prod_short.md)] and warehouses in [!INCLUDE [field-service-short](includes/field-service-short.md)]. To use the integration table mapping, you must turn on the **Location Mandatory** toggle on the **Inventory Setup** page in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [prod_short](includes/prod_short.md)] synchronizes locations with the following settings on the **Location Card** page:

- The **Use as In-Transit** toggle is turned off.
- **Project Consump. Whse. Handling** is different from Warehouse Pick (mandatory).
- **Assm. Consump. Whse. Handling** is different from Warehouse Pick (mandatory).

In [!INCLUDE [prod_short](includes/prod_short.md)], on the **Locations** and **Location Card** page, you can use the **Warehouse** action to open a coupled location in [!INCLUDE [field-service-short](includes/field-service-short.md)], synchronize it, set up and delete couplings, and view synchronization logs.

### Set up virtual tables

A virtual table is a custom table that has columns and rows that contain data from an external data source, such as [!INCLUDE [prod_short](includes/prod_short.md)]. The columns and rows in a virtual table look like a regular table, however, the data isn't stored in a physical table in the [!INCLUDE[prod_short](includes/cds_long_md.md)] database. Instead, the data is retrieved at runtime. To learn more about virtual tables, go to [Use virtual tables to get more data](admin-synchronizing-business-central-and-sales.md#use-virtual-tables-to-get-more-data).

To use virtual tables in your integration, the first thing to do is to install the [Business Central Virtual Table](https://go.microsoft.com/fwlink/?linkid=2277917) app from AppSource.

> [!NOTE]
> Your [!INCLUDE [field-service-short](includes/field-service-short.md)] and [!INCLUDE [prod_short](includes/prod_short.md)] must be in the same tenant. That's a requirement for using virtual tables.

Afterward, on the **Dynamics 365 Field Service Integration Setup** or **Set up integration to Dynamics 365 Field Service** pages in [!INCLUDE [prod_short](includes/prod_short.md)], turn on the **Enable Inventory Availability by Location** toggle. When you enable inventory availability by location, a **dyn365bc_availabilitybylocation_v2_0** virtual table becomes available. You must create a synthetic relation between the following tables:

- The native **Product** and **Work Order Product** tables in [!INCLUDE [field-service-short](includes/field-service-short.md)] and the **Item Availability** virtual table that shows item availability.

There's an assisted setup guide to help you create the synthetic relation. To create the synthetic relation, follow these steps:

1. In [!INCLUDE [prod_short](includes/prod_short.md)], on the **Dataverse Connection Setup** page, use the **Synthetic Relations** action.
1. On the **Synthetic Relations** page, choose the **New** action to start the **New Synthetic Relation** assisted setup guide.
1. In the **Native Dataverse Table** field, choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="The AssistEdit icon."::: button, and then choose **CRM Product**.
1. In the **Virtual Dataverse Table** field, choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="The AssistEdit icon."::: button, and then choose **Inventory Availability by Location**.
1. On the **Synthetic Relations** page, choose the **New** action to start the **New Synthetic Relation** assisted setup guide again.
1. In the **Native Dataverse Table** field, choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="The AssistEdit icon."::: button, and then choose **FS Work Order Product**.
1. In the **Virtual Dataverse Table** field, choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="The AssistEdit icon."::: button, and then choose **Inventory Availability by Location**.
1. Choose **Next**.
1. In the **Field in the FS Work Order Product table** field, choose **Product Id**.
1. In the **Field in the Item Availability by Location table** field, choose **itemNo**.
1. Choose **Finish** to complete the guide.
1. To make your setup available in [!INCLUDE [field-service-short](includes/field-service-short.md)], in the **Power Apps admin center**, choose the view, and then choose the **Save and Publish** action.

> [!NOTE]
> It can take a few moments to create the synthetic relations.

### Set up the view in Field Service

The next thing to do is to create and customize the view that people use in [!INCLUDE [field-service-short](includes/field-service-short.md)] to check the inventory of products.

To create the view in [!INCLUDE [field-service-short](includes/field-service-short.md)], follow these steps:

1. In **Power Apps admin center**, on the navigation pane, choose **Tables**.
1. Choose the **Item Availability by Location** table.
1. In the **Data experiences** part, choose **Views**.
1. Choose the **View column** action, and then choose the columns you want the view to include. The following columns are typical choices:

    - **Location Code** shows where the product is available.
    - **Item No.** confirms you're looking at the correct product.
    - **Item Description** provides information about the product.
    - **Unit of Measure Code** gives you an idea of the space you need.
    - **Remaining Quantity** shows how much of the product is available at each location.

## Related information

[Integrate with Microsoft Dataverse via data sync](admin-common-data-service.md)  
[Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md)
