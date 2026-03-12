---
title: Inspect production output
description: Learn how to set up and use automatic quality inspection tests for production output.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416,
ms.date: 03/10/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Inspect the quality of production output

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains how to set up quality management to automatically create quality inspections for production output when you post manufacturing operations. For example, these inspections enable:

- Finished goods inspection
- In-process quality checks
- Work center-specific inspections
- Routing operation validation

## Get started

To automate the process of creating inspections for production output, there are a few things to set up.

- You must prepare items for production output testing by filling in a couple of fields on the **Item Card** page:

   - You must set up an **Item Tracking Code** (for example, "LOT ALL") and assign it to the item. Learn more at [Set up item tracking with serial, lot, and package numbers](inventory-how-setup-item-tracking.md).
   - Fill in the **Lot Nos.** field with the number series to use for automatic lot assignment.
   - Make sure a routing is created for the item.

- You must set up a global trigger for production output. On the **Quality Management Setup** page, in the **Production - Create Inspection** field, choose **When Output is Posted**.
- You must create inspection generation rules for production output testing. Learn more at [Create a production rule](qms-test-generation-rules.md#create-a-production-rule).


## Create production output inspections

Production output inspections are automatically created when you post production orders. When you create the order, be sure to fill in the following fields:

- **Item**: Use a lot-tracked production item.
- **Quantity**: Specify a production quantity.
- **Location**: Match the inspection generation rule filters.
- **Routing**: Verify that routing operations exist.

Use an output journal or a production journal to post output.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Output Journal** or **Production journal**, and then choose the related link.
1. Enter the output to post, as follows:

   - **Item No.**: Production item
   - **Operation No.**: Final routing operation
   - **Output Quantity**: Quantity being output
   
1. Choose **Post** to post the production output.

   After you post production output, a quality inspection is created automatically. The inspection includes:

     - **Item Number**: The production item.
     - **Lot Number**: The assigned lot number for item tracking.
     - **Quantity**: The output quantity.
     - **Source**: The production order and operation reference.

## Work with production inspections

Production output inspections contain:

- **Control Information**: Source production order details
- **Item Tracking**: Lot/serial number information
- **Template Fields**: Quality measurements to complete
- **Quantity**: Specific to output posting

You can access related information in several ways:

- The **Navigate** action in the inspection shows:

   - Item ledger entries
   - Production order details
   - Warehouse entries
   - Related documents

- **Control Information** shows:
   - Source production order
   - Operation details
   - Posting information

### Complete production inspections

The following steps give an overview of how to complete a production inspection.

1. Open a quality inspection.
2. Enter the measurement values.
3. Review the calculated results that the template configuration and measurements determine.
4. Choose the **Finish** action when the inspection is complete.

## Advanced configuration

### Location-specific rules

You can create multiple rules for different locations. Set up a filter for each specific location, and select the template that you created for that location.

### Operation-specific inspections

Configure inspections for specific routing operations:

- **Routing No. Filter**: Specify a routing.
- **Work Center Filter**: Specify a work center.
- **Operation Filter**: Specify an operation number.

## Production setup considerations

### Posting setup requirements

Ensure that you have an **Inventory Posting Setup** for item transactions. Learn more at [Specific posting groups](finance-posting-groups.md#specific-posting-groups).

### Item tracking integration

Production output with item tracking:

- **Lot numbers** can be automatically assigned or manually entered.
- **Serial numbers** are supported for serialized items.
- **Package numbers** are supported for package tracking.

### Backflushing considerations

If you use backflushing, there are a few things to consider:

- Material consumption posts automatically.
- Component lot tracking might affect inspection creation.
- Review backflushing setup for quality integration.

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Manual Inspection Creation](qms-manual-test-creation.md)  
[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Quality Management Overview](qms-overview.md)