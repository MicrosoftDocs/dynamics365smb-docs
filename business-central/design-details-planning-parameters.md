---
title: Design Details - Planning Parameters
description: This article describes the different planning parameters that you can use and how they affect the planning system.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 04/26/2023
ms.custom: bap-template
---
# Design Details: Planning Parameters

This article describes the planning parameters that you can use in [!INCLUDE[prod_short](includes/prod_short.md)].  

How the planning system controls item supply is determined by various settings on the **Item Card**, **SKU**, and **Manufacturing Setup** pages. The following table explains how planning uses these settings.  

|Purpose|Settings|
|-------------|---------------|
|Define whether the item is planned|Reordering Policy = Blank|
|Define when to reorder|Time Bucket<br /><br /> Reorder Point<br /><br /> Safety Lead Time|
|Define how much to reorder|Safety Stock Quantity<br /><br /> Reordering Policy:<br /><br /> -   Fixed Reorder Qty. plus Reorder Quantity<br />-   Maximum Qty. plus Maximum Inventory<br />-   Order<br />-   Lot-for-Lot|
|Optimize when and how much to reorder|Rescheduling Period<br /><br /> Lot Accumulation Period<br /><br /> Dampener Period|
|Modify the supply orders|Minimum Order Quantity<br /><br /> Maximum Order Quantity<br /><br /> Order Multiple|
|Delimit the planned item|Manufacturing Policy:<br /><br /> -  Make-to-Stock<br />- Make-to-Order|

## Define whether the item is planned  

To include an item or SKU in the planning process, you must assign it a reordering policy. Otherwise, it must be planned manually, for example, by using the Order Planning feature.  

## Define when to reorder  

Reorder proposals are generally released only when the projected available quantity has fallen to or below a given quantity. The reorder point defines the quantity. Otherwise, it will be zero. Zero can be adjusted by entering a safety stock quantity. If you define a safety lead time, the proposal will be delivered in the period prior to the required due date.  

The **Time Bucket** field is used by reorder point policies (**Fixed Reorder Qty.** and **Maximum Qty.**). The inventory level is checked after each time bucket. The first time bucket begins on the planning start date.  

> [!NOTE]  
> When calculating time buckets, the planning system ignores working calendars that are defined in the **Base Calendar Code** field on the **Company Information** and **Location Card** pages.  

On the **Manufacturing Setup** page, you should set the default safety lead time to at least one day. The due date of the demand might be known, but not the due time. The planning schedules backward to meet gross demand. If you don't define a safety lead time, the goods might arrive too late to meet the demand.  

The **Rescheduling Period**, **Lot Accumulation Period**, and **Dampener Period** fields also play a role in defining when to reorder. For more information, see [Optimize When and How Much to Reorder](design-details-planning-parameters.md#optimize-when-and-how-much-to-reorder).  

## Define how much to reorder

If the planning system detects the need to reorder, the reordering policy determines when, and how much, to order.  

Independent of the reordering policy, the planning system usually follows this logic:  

1. Calculate the quantity of the order proposal to meet the minimum inventory level of the item, usually the safety stock quantity. If nothing is specified, the minimum inventory level is zero.  
2. If the projected available inventory is below the safety stock quantity, a backward-scheduled supply order is suggested. The order quantity will at least fill the safety stock quantity, and can be increased by gross demand within the time bucket, by the reordering policy, and by the order modifiers.  
3. If the projected inventory is on or below the reorder point (calculated from aggregated changes within the time bucket) and above the safety stock quantity, a forward-scheduled exception order is suggested. Both the gross demand to be met and the reordering policy will determine the order quantity. At minimum, the order quantity will meet the reorder point.  
4. If there's more gross demand due before the ending date of the forward-scheduled order proposal, and this demand brings the currently calculated projected available inventory below the safety stock quantity, the order quantity is increased to make up the deficit. The suggested supply order is then scheduled backward from the due date of the gross demand that would have violated the safety stock quantity.  
5. If the **Time Bucket** field isn't filled in, only the gross demand on the same due date is added.  

### Reordering policies  

The following reordering policies affect the quantity that's reordered. To learn more about reordering policies, go to [Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md).  

|Reordering policy|Description|  
|-----------------------|---------------------------------------|  
|**Fixed Reorder Qty.**|At a minimum, the order quantity will be equal to the reorder quantity. You can increase the quantity to meet the demand or the desired inventory level. This reordering policy is usually used with a reorder point.|  
|**Maximum Qty.**|The order quantity is calculated to meet the maximum inventory. If quantity modifiers are used, then maximum inventory can be violated. We do not recommend that you use the time bucket together with maximum quantity. The time bucket will usually be overruled. This reordering policy is usually used with a reorder point.|  
|**Order**|The order quantity will be calculated to meet each single demand event and the demand-supply set will remain linked until execution. No planning parameters are considered.|  
|**Lot-for-Lot**|The quantity is calculated to meet the sum of the demand that comes due in the time bucket.|  

## Optimize when and how much to reorder  

A planner can fine-tune planning parameters to limit rescheduling suggestions, accumulate demand (dynamic reorder quantity), or to avoid insignificant planning actions. The following fields help optimize when and how much to reorder.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Rescheduling Period**|This field determines whether the action message should reschedule an existing order or cancel it and create a new order. The existing order will be rescheduled within one rescheduling period before the current supply and until one rescheduling period after the current supply.<br><br>**Note:** This parameter only works with the **Lot-for-Lot** reordering policy.|  
|**Lot Accumulation Period**|With the reordering policy Lot-for-Lot, this field is used to accumulate multiple supply needs into one supply order. From the first planned supply, the system accumulates all supply needs in the following lot accumulation period into one supply, which is placed on the date of the first supply. Demand outside the lot accumulation period is not covered by this supply.|  
|**Dampener Period**|This field is used to avoid minor rescheduling of existing supply out in time. Changes from the supply date until one dampener period from the supply date will not generate any action messages.<br /><br /> The dampener period specifies a period of time during which you don't want the planning system to propose to reschedule existing supply orders forward. This limits the number of insignificant rescheduling of existing supply to a later date if the rescheduled date is within the dampener period.<br /><br /> As a result, a positive delta between the suggested new supply date and the original supply date will always be larger than the dampener period.|  

> [!NOTE]
> With the reordering policy Lot-for-Lot, the value of the **Lot Accumulation Period** field must be equal to or larger than the value of the **Dampener Period** field. Otherwise, the dampener period is reduced during the planning routine to match the lot accumulation period.  

The timing of rescheduling period, dampener period, and lot accumulation period is based on a supply date. The time bucket is based on the planning start date, as shown in the following illustration.  

:::image type="content" source="media/supply_planning_5_time_bucket_elements.png" alt-text="Time bucket elements.":::

In the following examples, the black arrows represent existing supply (up) and demand (down). Red, green, and orange arrows are planning suggestions.  

**Example 1**: The changed date is outside the rescheduling period, which causes the existing supply to be canceled. A new supply is suggested to cover the demand in the lot accumulation period.  

:::image type="content" source="media/supply_planning_5_recheduling_period_lot_accumulation_period.png" alt-text="Rescheduling and lot accumulation periods.":::

**Example 2**: The changed date is in the rescheduling period, which causes the existing supply to be rescheduled. A new supply is suggested to cover the demand outside the lot accumulation period.  

:::image type="content" source="media/supply_planning_5_recheduling_period_lot_accum_period_reschedule.png" alt-text="Rescheduling period, lot accumulation period, and reschedule.":::

**Example 3**: There's a demand in the dampener period and the supply quantity in the lot accumulation period matches the supply quantity. The next demand is uncovered and a new supply is suggested.  

:::image type="content" source="media/supply_planning_5_dampener_period_lot_accumulation_period.png" alt-text="Dampener period and lot accumulation period.":::

**Example 4**: There's a demand in the dampener period and the supply remains on the same date. However, the current supply quantity doesn't cover the demand in the lot accumulation period. A change quantity action for the existing supply order is suggested.  

:::image type="content" source="media/supply_planning_5_dampener_period_lot_accum_period_change_qty.png" alt-text="Dampener period, lot accumulation period, and change quantity.":::

**Default values:** The default value of the **Time Bucket** field and the three reorder period fields is blank. For all fields, except the **Dampener Period** field, this means 0D (zero days). If the **Dampener Period** field is blank, the global value in the **Default Dampener Period** field on the **Manufacturing Setup** page will be used.  

## Modify the supply orders  

When the quantity of the order proposal has been calculated, one or more of the order modifiers can adjust it. For example, the maximum order quantity is larger than or equal to the minimum order quantity, which is larger than or equal to the order multiple.  

The quantity is decreased if it exceeds the maximum order quantity. Then, it is increased if it is below the minimum order quantity. Finally, it is rounded up so that it matches a specified order multiple. Any remaining quantity uses the same adjustments until the total demand has been converted into order proposals.  

## Delimit the item  

The **Manufacturing Policy** field on the **Item Card** page defines which other orders the MRP calculation proposes.  

If the **Make-to-Stock** option is used, the orders concern only the item.  

If the **Make-to-Order** option is used, the planning system analyzes the production BOM of the item and creates linked order proposals for those lower-level items that are also defined as make-to-order. This continues as long as there are make-to-order items in the descending BOM structures.

## Use low-level codes to manage derived demand

Use low-level codes to make derived demand for components progress through to the lower levels of the BOM. To learn more about low-level codes, go to [Item Priority / Low-Level Code](design-details-central-concepts-of-the-planning-system.md#item-priority--low-level-code).

You can assign a low-level code to each part in the product structure or the indented BOM. The top final assembly level is denoted as level 0 - the end item. The higher the low-level code number, the lower the item is in the hierarchy. For example, end items have low-level code 0, and the item parts that go into the assembly of the end item have low-level codes 1, 2, 3, and so on. The result is the planning of component parts coordinated with the requirements of all higher-level part numbers. When you calculate a plan, the BOM is exploded in the planning worksheet, and the gross requirements for level 0 are passed down the planning levels as gross requirements for the next planning level.

On the **Manufacturing Setup** page, use the **Dynamic Low-Level Code** toggle to specify whether to immediately assign and calculate low-level codes for each component in the product structure. If you have large amounts of data, this function can have negative effects on the program's performance, for example during automatic cost adjustment. Note that this is not a retroactive function, so it is a good idea to consider the use of this facility beforehand.

As an alternative to the automatic calculation that occurs dynamically if the field is selected, you can run the **Calculate Low-Level Code** batch job from the **Manufacturing** menu by clicking **Product Design**, **Calculate Low-Level Code**.

> [!IMPORTANT]
> If you don't turn on the **Dynamic Low-Level Code** toggle, you must run the **Calculate Low-Level Code** batch job before you calculate a supply plan (the **Calculate Plan** batch job).  

> [!NOTE]
> Although you turn on the **Dynamic Low-Level Code** field selected, the low-level codes of component items aren't changed dynamically if a parent BOM is deleted or set to non-certified. This case might make it difficult to add new items to the end of the product structure because it might exceed the maximum number of low-level codes. Therefore, for large product structures that reach the low-level code limit, you can run the **Calculate Low Level Code** batch job frequently to maintain the structure.  

## See also  

[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)  
[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]