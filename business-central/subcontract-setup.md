---
title: Set up subcontracting
description: Learn how to configure subcontracting settings, work center groups, and purchase provisions for manufacturing operations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, setup, work center group, purchase provisions
ms.search.form: 99000886
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Set up subcontracting

To use subcontracting, you must configure several settings. This article describes how to configure the basic subcontracting settings and work center groups.

## Configure general settings

You can specify which information from a subcontracting order to transfer to your purchase documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Setup**, and then choose the related link.
2. On the **General** FastTab, fill in the fields as described in the following table. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

|Field|Description|
|-----|----------|
|**Additional Information Line**|Specifies whether to create an additional information line in the subcontracting order.|
|**Operation Comment**|Specifies whether to transfer the operation comment to the purchase order.|
|**Subcontracting Inbound Whse. Handling Time**|Specifies the time for calculating the receipt date in the transfer line.|

## Configure subcontracting settings

On the **Subcontracting** FastTab, fill in the fields as described in the following table.

|Field|Description|
|-----|----------|
|**Subcontracting Suggestion Journal Template Name**|Specifies the name of the subcontracting journal template to use for direct creation of subcontracting from a released operation.|
|**Components Purchase Price**|Specifies which purchase price of a subcontracting component to use in the subcontracting order. The following options are available:<br><br>**Standard** - Standard price finding is used when procuring the component.<br><br>**Subcontracting Component** - The calculated purchase price of the subcontracting component is transferred to the subcontracting order.|
|**Item Charge to Subcontracting Purch. Receipt Lines**|Specifies whether to activate item charge assignment for purchase receipt lines with subcontracting. When you turn on this toggle, an additional option becomes available in the charge assignment in purchasing.|

For detailed configuration of purchase provisions and the provision setup guide, learn more in [Set up purchase provisions and use the provision setup guide](subcontract-setup-configurator.md).

## Set up work center groups for subcontracting

To use a work center group for subcontracting, you must assign it to a vendor number.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Center Groups**, and then choose the related link.
2. Open the work center group.
3. On the **Posting** FastTab, in the **Subcontractor No.** field, enter the vendor number. Learn more in [Set up work and machine centers](production-how-to-set-up-work-and-machine-centers.md).
4. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
5. Open the vendor card.
6. On the **Shipping** FastTab, in the **Subcontracting Location Code** field, specify the subcontracting location.

   This specifies the subcontracting location. Component items provided to the vendor are posted from this location by default after execution of the subcontracting. The **Linked to Work Center Group No.** field shows whether a vendor is connected to a work center group.

> [!NOTE]
> We recommend that you define a separate location for each vendor.

## About advanced setup options

The following sections describe advanced setup options.

### Transfer operation comments

If you turn on the **Operation Comment** toggle, comments from the production order routing lines are automatically transferred to the purchase order. This enables better communication with the subcontractor about special requirements or notes.

### Components purchase price configuration

The **Components Purchase Price** field determines which unit cost is used for components in subcontracting purchase orders:

- **Standard** - Uses normal price finding based on purchase prices and discounts.
- **Subcontracting Component** - Uses the calculated unit cost directly from the production order component.

This setting influences cost calculation and should be chosen according to your calculation strategy.

### Subcontracting inbound warehouse handling time

The **Subcontracting Inbound Whse. Handling Time** field defines the time used for calculating the receipt date in transfer lines. The calculation follows the formula:

**Receipt Date = Due Date of Subcontracting Component - Whse. Handling Time**

This enables realistic planning of material provision at the subcontractor.

## Related information

[Set up purchase provisions and provision wizard](subcontract-setup-configurator.md)  
[Set up work and machine centers](production-how-to-set-up-work-and-machine-centers.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]