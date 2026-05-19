---
title: Set up subcontracting
description: Learn how to configure subcontracting settings, work center groups, and purchase provisions for manufacturing operations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, setup, work center group, purchase provisions
ms.search.form: 99000080
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

# Set up subcontracting

To use subcontracting, you must configure several settings. This article describes how to configure the basic subcontracting settings and work center groups.

## Configure general settings

You can specify which information from a subcontracting order to transfer to your purchase documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manufacturing Setup**, and then choose the related link.
2. On the **Subcontracting** FastTab, in the **General** section, fill in the fields as described in the following table. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

|Field|Description|
|-----|----------|
|**Create Prod. Order Info Line**|Specifies whether to create an additional information line with the production order description in the subcontracting purchase order.|
|**Subcontracting Inbound Whse. Handling Time**|Specifies the time for calculating the receipt date in the transfer line.|

## Configure additional subcontracting settings

On the **Subcontracting** FastTab, in the **General** section, you can also configure the following fields.

|Field|Description|
|-----|----------|
|**Subcontracting Journal Template Name**|Specifies the name of the subcontracting journal template to use for direct creation of subcontracting from a released operation.|
|**Component Direct Unit Cost**|Specifies which direct unit cost of a production order component to use in the subcontracting purchase order. The following options are available:<br><br>**Standard** - Standard price finding is used when procuring the component.<br><br>**Prod. Order Component** - The calculated direct unit cost from the production order component line is transferred to the subcontracting purchase order.|
|**Item Charge to Subcontracting Purch. Receipt Lines**|Specifies whether to activate item charge assignment for purchase receipt lines with subcontracting. When you turn on this toggle, an additional option becomes available in the charge assignment in purchasing.|

<!-- For detailed configuration of purchase provisions and the provision setup guide, learn more in [Set up purchase provisions and use the provision setup guide](subcontract-setup-configurator.md). -->

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

## Set up subcontract work center fields

Subcontract work centers are set up the same as regular work centers, with additional fields. They're assigned to routings in the same manner as other work centers.

The **Subcontractor No.** field designates the work center as a subcontract work center. Enter the number of a subcontractor who supplies the work center. You can use this field to administer work centers that aren't in-house but perform processing under contract.

If you subcontract with the vendor for a different rate for each process, select the **Specific Unit Cost** field. This setting lets you set up a cost on each routing line and saves the time of reentering each purchase order. The cost on the routing line is used in processing instead of the cost on the work center cost fields. When you select **Specific Unit Cost**, costs are calculated for the vendor by the routing operation.

If you subcontract at a single rate per vendor, leave the **Specific Unit Cost** field blank. Instead, set up costs by filling in the **Direct Unit Cost**, **Indirect Cost %**, and **Overhead Rate** fields.

### Routings that use subcontract work centers

You can use subcontract work centers for operations on routings in the same way as regular work centers. You can set up a routing that uses a subcontract work center as a standard operational step, or modify the routing for a particular production order to include a subcontracted operation. Learn more in [Create Routings](production-how-to-create-routings.md).

## About advanced setup options

The following sections describe advanced setup options.

### Production order information line

If you turn on the **Create Prod. Order Info Line** toggle, the description from the production order line is automatically added as an additional text line in the subcontracting purchase order. This helps identify which production order item the subcontracting work relates to.

### Component direct unit cost configuration

The **Component Direct Unit Cost** field determines which unit cost is used for components in subcontracting purchase orders:

- **Standard** - Uses normal price finding based on purchase prices and discounts.
- **Prod. Order Component** - Uses the calculated direct unit cost from the production order component line.

This setting influences cost calculation and should be chosen according to your calculation strategy.

### Subcontracting inbound warehouse handling time

The **Subcontracting Inbound Whse. Handling Time** field defines the time used for calculating the receipt date in transfer lines. The calculation follows the formula:

**Receipt Date = Due Date of Subcontracting Component - Whse. Handling Time**

This enables realistic planning of material provision at the subcontractor.

## Related information

[Subcontracting overview](production-how-to-subcontract-manufacturing.md)  
<!-- [Set up purchase provisions and provision wizard](subcontract-setup-configurator.md)   -->
[Set up work and machine centers](production-how-to-set-up-work-and-machine-centers.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]