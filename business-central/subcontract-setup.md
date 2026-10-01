---
title: Set up subcontracting
description: Learn how to connect outsourced production operations with vendors, work centers, comments, components, purchasing, locations, transfers, and costs.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, setup, work center, transfer routes, subcontracting comments
ms.search.form: 99000768, 99000754, 99000755
ms.date: 09/04/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up subcontracting

Subcontracting lets you outsource selected production routing operations to vendors while keeping the related production order, components, purchasing, transfers, and costs connected in [!INCLUDE [prod_short](includes/prod_short.md)]. This article explains how to configure subcontracting defaults, vendor work centers, reusable operation comments, locations, and transfer routes.

## Prerequisites

Make sure that the **Subcontracting** extension is installed. Install it from the **Extension Management** page or get it from [Microsoft Marketplace](https://go.microsoft.com/fwlink/?LinkId=2370676). Learn more about installing extensions in [Installing and Uninstalling Extensions](ui-extensions-install-uninstall.md#install).

## Use assisted setup

The **Subcontracting Setup** assisted setup guide provides a starting point for configuring subcontracting.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link.
2. Choose **Set up Subcontracting**.
3. Review the introduction, and then choose **Next**.
4. Specify the default journal template and batch, whether to add production order information lines, the component cost source, and the component transfer lead time.
5. Use the links in the guide to open the pages where you set up work centers, vendors, locations, subcontractor prices, component supply methods, and supporting documentation.
6. Choose **Finish** to save the defaults and mark the guide as complete.

> [!IMPORTANT]
> The guide provides links to the required setup areas, but it doesn't verify that every subcontractor, location, price, production BOM, or routing is ready to use.

## Configure general settings

You can specify which information from a subcontracting order to transfer to your purchase documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manufacturing Setup**, and then choose the related link.
2. On the **Subcontracting** FastTab, in the **General** section, fill in the fields as described in the following table. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

|Field|Description|
|-----|----------|
|**Create Prod. Order Info Line**|Specifies whether to create an additional information line with the production order description in the subcontracting purchase order.<br><br>When turned on, the description from the production order line is automatically added as an extra text line. This helps identify which production order item the subcontracting work relates to.|
|**Subcontracting Component Transfer Lead Time**|Specifies the lead time for transferring components to the subcontractor. This time is subtracted from the production component due date to calculate the transfer order receipt date.<br><br>The calculation follows the formula: **Receipt Date = Due Date of Production Order Component - Subcontracting Component Transfer Lead Time**. This formula enables realistic planning of material provision at the subcontractor.|
|**Subcontracting Journal Template Name**|Specifies the name of the subcontracting journal template to use for direct creation of subcontracting from a released production order routing line.|
|**Subcontracting Journal Batch Name**|Specifies the name of the subcontracting journal batch to use for direct creation of subcontracting from a released production order routing line.|
|**Component Direct Unit Cost**|Specifies which direct unit cost of a production order component to use in the subcontracting purchase order. The following options are available:<br><br>**Standard** - Uses normal price finding based on purchase prices and discounts.<br><br>**Prod. Order Component** - Uses the calculated direct unit cost from the production order component line.<br><br>This setting influences cost calculation and should be chosen according to your calculation strategy.|

<!-- For detailed configuration of purchase provisions and the provision setup guide, learn more in [Set up purchase provisions and use the provision setup guide](subcontract-setup-configurator.md). -->

## Set up subcontract work centers

To use a work center for subcontracting, you must assign it to a vendor and set up the vendor with a subcontracting location.

- To assign a vendor to a work center, set the **Subcontractor No.** field on the work center card. Learn more in the following section.
- To assign a subcontracting location to the vendor, go to [Set up locations for subcontracting](subcontract-location-management.md).

### Set up subcontract work center fields

Subcontract work centers are set up the same as regular work centers, but have more fields. They're assigned to routings in the same manner as other work centers.

The **Subcontractor No.** field designates the work center as a subcontract work center. Enter the number of a subcontractor who supplies the work center. You can use this field to administer work centers that aren't in-house but perform processing under contract.

If the vendor doesn't have a **Subc. Location Code**, a notification explains that a location is required to manage components and WIP items. Choose **Open Vendor Card** in the notification, and then assign the subcontracting location to the vendor.

If you subcontract with the vendor for a different rate for each process, select the **Specific Unit Cost** field. This setting lets you set up a cost on each routing line and saves the time of reentering each purchase order. The cost on the routing line is used in processing instead of the cost on the work center cost fields. When you select **Specific Unit Cost**, costs are calculated for the vendor by the routing operation.

If you subcontract at a single rate per vendor, leave the **Specific Unit Cost** field blank. Instead, set up costs by filling in the **Direct Unit Cost**, **Indirect Cost %**, and **Overhead Rate** fields.

The **Direct Unit Cost** represents what you pay the subcontractor. The **Indirect Cost %** and **Overhead Rate** represent your internal overhead costs (such as administration, logistics, or quality inspection). [!INCLUDE [prod_short](includes/prod_short.md)] combines them into a total **Unit Cost** on the work center card using the formula:

`Unit Cost = Direct Unit Cost × (1 + Indirect Cost % / 100) + Overhead Rate`

This total unit cost flows to the routing line as **Unit Cost per**. The indirect cost fields also flow to the subcontracting purchase order, where they're used to split the posted cost into separate direct cost and indirect cost value entries. To learn more about how these fields interact with subcontractor price lists, see [How indirect costs apply to subcontractor prices](subcontract-prices.md#how-indirect-costs-apply-to-subcontractor-prices).

### Routings that use subcontract work centers

You can use subcontract work centers for operations on routings in the same way as regular work centers. You can set up a routing that uses a subcontract work center as a standard operational step, or modify the routing for a particular production order to include a subcontracted operation. Learn more in [Create Routings](production-how-to-create-routings.md).

> [!IMPORTANT]
> On routing lines for subcontracting operations, the **Type** field must be set to **Work Center** (not **Machine Center**). Machine centers don't support subcontractor assignments, so automatic location changes, pricing, and purchase order creation don't work for machine center operations.

## Add comments to subcontracting operations

Use subcontracting comments to define instructions or notes on standard tasks or routing lines. When you select a value in the **Subc. Standard Task Code** field on the **Routing Lines** or **Routing Version Lines** pages, [!INCLUDE [prod_short](includes/prod_short.md)] copies the comments to that operation. You can update the copied comments manually if needed.

### Add reusable comments to a standard task

To add reusable comments to a standard task, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Standard Tasks**, and then choose the related link.
2. Select the standard task, and then choose the **Subcontracting Comments** action.
3. Enter each comment in the **Description** field. To add more text, personalize the page to show the **Description 2** field, which is hidden by default.

### Add or change comments on a routing operation

To add or change comments on a routing operation, follow these steps:

1. Open the routing or routing version that contains the subcontracting operation.
2. If the **Subc. Standard Task Code** field isn't shown, personalize the routing lines page to add it. Learn more at [Start personalizing by using the personalization mode](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).
3. On the routing line, select a **Subc. Standard Task Code** to copy its comments to the operation.
4. Choose the **Subcontracting Comments** action to review or change the comments for that operation.

The operation-specific comments transfer to the production order routing when you calculate or refresh the production order. To learn more about how to review comments for a production order and transfer them to a subcontracting purchase order, go to [Review comments for subcontracting orders](subcontract-order.md#review-comments-for-subcontracting-orders).

## Set up routing attachments for subcontracting purchase orders

You can attach files to a routing and have them follow the related subcontracting operation to the purchase order.

1. Open the routing, and then choose the **Attachments** action.
2. Add the attachment.
3. For the attachment, turn on the **Document Flow Production** and **Document Flow Purchase** toggles.

The attachment first transfers to the related production order line. When you create the subcontracting purchase order, it transfers to the related purchase line. The attachment settings on the production order line are read-only. Attachments that you add manually to the production order line don't transfer to the purchase line.

## Configure transfer settings

If you plan to transfer components or WIP items between your warehouse and subcontractor locations, review the following settings:

- **Transfer routes**: Set up transfer routes with an **In-Transit Code** between your warehouse locations and each subcontractor location. Without a configured route, [!INCLUDE [prod_short](includes/prod_short.md)] creates direct transfer orders, which have limitations when the source or destination location uses advanced warehouse handling. Learn more in [Set up transfer routes](subcontract-location-management.md#set-up-transfer-routes).
- **Inventory Setup**: Review the **Direct Transfer Posting** field on the **Inventory Setup** page. This field controls how direct transfers are posted and affects which warehouse configurations are supported. Learn more in [Transfer modes and warehouse handling](subcontract-wip-transfers.md#transfer-modes-and-warehouse-handling).

## Related information

[Subcontracting overview](production-how-to-subcontract-manufacturing.md)  
<!-- [Set up purchase provisions and provision wizard](subcontract-setup-configurator.md)   -->
[Set up work and machine centers](production-how-to-set-up-work-and-machine-centers.md)  
[Set up locations for subcontracting](subcontract-location-management.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
