---
title: Integrate with Microsoft Dynamics 365 Field Service
description: Learn how to integrate Business Central with Field Service.
ms.date: 02/21/2024
ms.topic: article
author: brentholtorf
ms.author: bholtorf
ms.reviewer: ivkoleti
ms.custom: bap-template
---

# Integrate with Microsoft Dynamics 365 Field Service

Service organizations require a front-to-back application in which financials, inventory, and procurement are tightly coupled with service delivery. They generate financial data with every transaction. Every work order represents cost and revenue, and every resource generates profit and loss. Customer interactions add entries on the general ledger. The integration between [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [field-service-short](includes/field-service-short.md)] streamlines the end-to-end process of managing service operations and ensures a smooth flow of information between the two systems.  

You can easily create and manage work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)], track the progress of service tasks, assign resources, and capture consumption details. When you complete a work order in [!INCLUDE [field-service-short](includes/field-service-short.md)], the integration enables the smooth transfer of data to [!INCLUDE [prod_short](includes/prod_short.md)] for further processing.  

The integration also facilitates the invoicing and fulfillment of work orders in [!INCLUDE [prod_short](includes/prod_short.md)]. You can generate accurate invoices based on the service activities and the consumption recorded in [!INCLUDE [field-service-short](includes/field-service-short.md)]. This ensures timely and accurate billing to improve financial management and ultimately customer satisfaction.  

By integrating [!INCLUDE [prod_short](includes/prod_short.md)] with [!INCLUDE [field-service-short](includes/field-service-short.md)], you eliminate the need for manual data entry or duplication. Integration also provides a comprehensive view of service operations and financials, enabling better decision-making and operational efficiency.

## Integrate through Dataverse and Sales

Because [!INCLUDE [field-service-short](includes/field-service-short.md)] is built on top of Dynamics 365 Sales, you'll need to [set up a connection to Dataverse](/dynamics365/business-central/admin-how-to-set-up-a-dynamics-crm-connection#to-use-the-dataverse-connection-setup-assisted-setup-guide) and [enable integration to Dynamics 365 Sales](https://learn.microsoft.com/dynamics365/business-central/admin-prepare-dynamics-365-for-sales-for-integration#connection-settings-in-the-setup-guide).

## Any prerequisites, like permissions or security requirements?

We should list any prerequisites

## Set up the integration in Business Central

After you have a connection to Dataverse and Sales, you can set up your integration to [!INCLUDE [field-service-short](includes/field-service-short.md)]. On the **Assisted Setup** page in [!INCLUDE [prod_short](includes/prod_short.md)], choose **Set up integration to Dynamics 365 Field Service** to run the assisted setup guide. This section describes the key steps in the guide.

When you run the guide, you can choose to **Import Dynamics 365 Field Service Solution** and **Enable Dynamics 365 Field Service Connection**. To enable people to post the consumption of items and services in [!INCLUDE [field-service-short](includes/field-service-short.md)] work orders, specify the **Project Journal Template** and **Project Journal Batch** that will post consumption of products and services. 

Because services are expressed in duration in [!INCLUDE [field-service-short](includes/field-service-short.md)], specify the **Hours Unit of Measure** that will convert durations to quantities in [!INCLUDE [prod_short](includes/prod_short.md)].

You can also specify when work order products and service lines synchronize to [!INCLUDE [prod_short](includes/prod_short.md)]. For example, they might synchronize when work order lines are used, or a when work order is completed. Choose the appropriate option in **Synchronize work order products/services** field.

After work order products and services synchronize to project journals in [!INCLUDE [prod_short](includes/prod_short.md)], you can choose whether to post the project journals manually, when work order status is complete, or when work order products or services get used. Choose the appropriate option in the **Automatically post project journals lines** field.

## Standard Field Service entity mapping for synchronization

The basis of synchronizing data is mapping the tables and fields in [!INCLUDE [prod_short](includes/prod_short.md)] with tables and columns in Dataverse, so they can exchange the data. Mapping happens through integration tables. To learn more about table mappings, go to [Mapping the Tables and Fields to Synchronize](/dynamics365/business-central/admin-how-to-modify-table-mappings-for-synchronization).

Integration with [!INCLUDE [field-service-short](includes/field-service-short.md)] introduces the following standard integration table mappings.

* **PJLINE-WORDERPRODUCT** - Maps work order products in [!INCLUDE [field-service-short](includes/field-service-short.md)] to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)]. 
* **PJLINE-WORDERSERVICE** - Maps work order services in [!INCLUDE [field-service-short](includes/field-service-short.md)] to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)].
* **PROJECTTASK** - Maps projects and project tasks in [!INCLUDE [prod_short](includes/prod_short.md)] to products in external projects in Field Service. 
* **RESOURCE-BOOKABLERSC** - Maps resources in [!INCLUDE [prod_short](includes/prod_short.md)] to bookable resources in [!INCLUDE [field-service-short](includes/field-service-short.md)].
* **SVCITEM-CUSTASSET** - Maps service items in [!INCLUDE [prod_short](includes/prod_short.md)] to customer assets in [!INCLUDE [field-service-short](includes/field-service-short.md)].

## Synchronization jobs for a Field Service integration

Need the names of the jobs

## Use data in both applications

The following sections describe the features where people often use the data that's exchanged between [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [field-service-short](includes/field-service-short.md)].

### Field Service

You can [create **Work Order** in Field Service](https://learn.microsoft.com/dynamics365/field-service/create-work-order) using the **Service Account** and **Billing Account** from [!INCLUDE [prod_short](includes/prod_short.md)]. On work orders, you can select the **Business Central Project** and **Project Task Work Order** in the **External Project** field.

You can add inventory and non-inventory items as **Work Order Products** and get the **Quantity on Hand** together with costs and prices from [!INCLUDE [prod_short](includes/prod_short.md)].

You can add service items as **Work Order Services**, and get costs and prices from [!INCLUDE [prod_short](includes/prod_short.md)]. 

You can book a resource and relate the **Bookings** to work order services using a **Bookable Resource** from [!INCLUDE [prod_short](includes/prod_short.md)].

### Business Central

Depending on your settings on the **Field Service Integration Setup** page, when work orders include products and services, consumption information is transferred and posted using a **Project Journal** in [!INCLUDE [prod_short](includes/prod_short.md)]. 

You can use the **Project Planning Lines** page track posting and invoicing of consumption on work orders.

The **Quantity To Bill** and **Duration To Bill** values are copied to the **Qty- to Transfer to Invoice** field. Based on that, you can create and post sales invoices in [!INCLUDE [prod_short](includes/prod_short.md)] to invoice the customer.  

## See also

[Integrate with Microsoft Dataverse via data sync](admin-common-data-service.md)  
[Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md)