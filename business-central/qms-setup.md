---
title: Quality management setup and configuration 
description: Learn how to set up and configure quality management features, including prerequisites, initial setup steps, and common scenarios.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416,
ms.date: 03/10/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management setup and configuration

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains the initial setup and configuration of quality management features.

## Typical setup scenarios

If you're setting up the app for purchase receipt inspections only, focus on purchase trigger configuration. Create templates for inspecting incoming goods, and set up rules for vendor-specific or item-specific testing.

For production output testing only, you should focus on production trigger configuration. Create templates for finished goods inspection, and set up rules for routing-specific or work center-specific testing.

> [!NOTE]
> The **Premium** experience is required for production capabilities. If you don't need those, you can use the **Essential** experience.

If you need a comprehensive quality system, configure both purchase and production triggers. Create multiple templates for different types of inspections, and set up workflows to automatically block and unblock lots.

### Configure general base data

Ensure you have the base data described in the following table before you start to set up quality management. Your quality management setup uses this data.

|Data  |Description  |
|---------|---------|
|Locations     |- Configure the locations where you do quality inspections.<br>- Set up warehouse handling, if necessary. For example, receipts, put-aways, and so on.<br>- Define bins for your quality inspection areas.         |
|Items     |- Configure item tracking codes for lots, serials, or packages, as needed.<br>- Set up lot number series for automatic lot assignments.<br>- Ensure that the correct inventory posting groups are assigned to items. |
|Vendors and customers     |- Configure vendors for purchase receipt inspections.<br>- If quality inspections affect sales processes, set up customers.       |

<!--### Run the assisted setup guide

You can set up quality management from scratch on the **Quality Management Setup** page. Learn more at [Set up quality management manually](#set-up-quality-management-manually).

However, [!INCLUDE [prod_short](includes/prod_short.md)] offers the **Quality Management Setup Guide** to help you quickly configure basic settings. This section describes the settings in the setup guide.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Management Setup Guide**, and then choose the related link.
1. On the first step, choose **Next**.

   > [!TIP]
   > The first step offers a link to open the **Quality Manager** role center, which gives access to all quality management features. If you want a guided tour of what's available in the role center, choose **Show demo tours**.

1. Choose whether to apply demonstration and sample data, and then choose **Next**:

   - **Apply Getting Started Data**: Downloads and applies basic setup data with useful examples and demonstration data. Getting started data helps you get going quickly or, if you're just exploring, evaluate whether the application fits your needs.
   - **Do Not Apply Configuration**: Skips sample data installation. However, some basic setup data for common integration scenarios is applied.

1. Specify where you plan to use quality inspections, and then choose **Next**.

   - **Production**: Create inspections when you record production output. Typical scenarios are when inventory is posted from the output journal, but could also be for intermediate steps or other triggers.
   - **Receiving**: Create inspections when you receive inventory from purchase orders, transfer orders, warehouse receipts, or sales returns.
   - **Something Else**: Use quality inspection to create manual tests for other areas in [!INCLUDE [prod_short](includes/prod_short.md)], or if you want to manually configure them later.

   > [!TIP]
   > The steps in the guide differ, based on your selection.

1. If you chose **Production**, specify how to create production inspections, and then choose **Next**.:

   - **I want inspections created automatically when output is recorded**: [!INCLUDE [prod_short](includes/prod_short.md)] creates inspections automatically when you record output. Use this option when inspections must exist when production output occurs.
   - **I want a person to make an inspection**: You manually create inspections. Use this option when your process requires a person to create inspections, or for ad-hoc inspection scenarios like nonconformance reports or tracking rework.

1. If you chose **Receiving**, configure automatic inspection creation for receiving scenarios, and then choose **Next**.

   - **Purchase Receipts**: Automatically create inspections when you receive goods via purchase orders.
   - **Transfer Receipts**: Automatically create inspections when you receive goods via transfer orders.
   - **Warehouse Receipts**: Automatically create inspections when you receive goods via warehouse receipts.
   - **Sales Return Receipts**: Automatically create inspections when you receive goods via sales returns.
   - **I only want people to make inspections**: Choose this option if you only want people to manually create inspections. For example, this option is useful for ad-hoc inspections or tracking damage for received goods.

1. Specify when to display inspections to users, and then choose **Next**.
<!--
- **Show automatic and manually created inspections**: Inspections show immediately when created. Use this option when the person doing the activity (like posting) is also the person who collects the inspection results.
- **Show only manually created tests**: Inspections created automatically don't show immediately, but manually created inspections do. Use this option when different people handle posting versus data collection.
- **Never show immediately**: Inspections are always created in the background. Use this option when the person who creates inspections shouldn't be able to edit them. This option ensures separation of inspection creation and completion.
- **Business Consideration**: Events that trigger inspections without direct interaction (background posting, pr web service integrations like Power Automate) create inspections but doesn't immediately show them.
1. Choose **Finish**.-->

### Set up quality management

The following steps describe settings you can use to get started with quality management, and manage features on an ongoing basis.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Management Setup**, and then choose the related link.
1. On the **General** FastTab, configure settings as described in the following table.

   |Field  |Description  |
   |---------|---------|
   |**Quality Inspection Nos.** | Specify the default number series to use for quality inspection documents when there isn't a number series defined on a quality inspection template. The number series defined on a template takes precedence.  |
   |**Inspection Creation Option** | Specify when to create a new inspection:<br><br>- **Always create new inspection** creates a new inspection every time, and doesn't search for existing inspections.<br>- **Create a reinspection if matching inspection is finished** searches for an existing, completed inspection that matches. If it finds one, it creates a reinspection. If it doesn't find one, it creates a new inspection.<br>- **Always create a reinspection** searches for an existing inspection. If it finds one, it creates a reinspection. If it doesn't find one, it creates a new inspection.<br>- **Use existing open inspection if available** searches for an existing, open inspection. If it finds an open inspection, it reuses it without any changes. If it finds an inspection that matches but is completed, or doesn't find a matching inspection, it creates a new inspection.<br>- **Use any existing inspection if available** searches for an existing inspection. If it finds one, it reuses it regardless of its status. If it doesn't fine one, it creates a new inspection.<br><br>**Important:** When an existing inspection is reused, the test data (status, results, measurements) remains unchanged.<br><br>**Tip:** If you automate inspection creation but manually create an inspection, for example, for the first receipt of a lot that you'll receive in multiple shipments, and you want automation to reuse that inspection for subsequent receipts, choose **Use existing open inspection if available** or **Use any existing inspection if available**. Then, in the **Inspection Search Criteria** field, choose **By Item Tracking** to find inspections by lot or serial numbers.  |
   |**Inspection Search Criteria** | Specify the search criteria to use to find existing inspections. All of the options in the **Create Inspection Behavior** field use this setting, with the exception of **Always create a new inspection**, which skips the search entirely.<br><br>- **By Standard Source Fields** searches by template, source table, document number, item, variant, and lot, serial, and package numbers. Use this option for the most comprehensive matching.<br>- **By Source Record** searches by the specific source record ID that triggered the inspection. Use this option when you want to find inspections linked to a specific document line.<br>- **By Item Tracking** searches primarily by item number, variant, and lot, serial, an package numbers. This option ignores the source document. Use this option to find inspections for a specific lot or serial number across different documents.<br>- **By Document and Item only** searches by document number and item only, and ignores lot, serial, and package numbers. Use this option to find inspections for an item on a document, regardless of tracking information.<br><br>**Note:** The search always returns the most recent inspection (highest retest number) that matches the criteria.    |
   |**Certificate of Analysis Contact** | Specify the contact details that appear on the **Certificate of Analysis** report when supplied.        |
   |**Maximum Rows To Fetch in Lookups** | Specify the maximum number of rows to fetch on data lookups. Keep the number as low as possible to increase usability and performance.        |
   |**Additional Picture Handling** | Specify what to do with pictures.<br><br>- **None** means not to take an action with pictures.<br>- **Save as attachment** attaches the picture as a document.<br>- **Save as attachment and upload to OneDrive** attaches the picture and uploads it to OneDrive.        |
   
1. On the **Generation Rule Trigger Defaults** FastTab, configure default trigger values for different types of documents, as described in the following table.

   |Field  |Options  |
   |---------|---------|
   |**Warehouse Receipts Trigger** | - **Never** means no automatic inspection creation.<br>- **When Warehouse Receipt is created** creates an inspection when you create a warehouse receipt.<br>- **When Warehouse Receipt is posted** creates an inspection when you post a warehouse receipt.        |
   |**Purchase Orders Trigger** | - **Never** means no automatic inspection creation.<br>- **When Purchase Order is received** creates an inspection when you post a purchase order receipt.<br>- **When Purchase Order is released** creates an inspection when you release a purchase order.        |
   |**Sales Returns Trigger** | - **Never** means no automatic inspection creation.<br>- **When Sales Return is received** creates an inspection when you post a sales return order receipt.        |
   |**Transfer Orders Trigger** | - **Never** means no automatic inspection creation.<br>- **When Transfer Order is received** creates an inspection when you post a transfer order receipt.        |
   |**Production Order Trigger**| - **Never** means no automatic inspection creation.<br>- **When Production Output is posted** creates an inspection when you post production output.<br>- **When Production Order is released** creates an inspection when you release a production order.<br>- **When a Released Production Order is refreshed** creates an inspection when you refresh a production order that is already released.|
   |**Prod. trigger output condition**|- **Any Output Entry** creates an inspection when you enter any output.- **Any Quantity Output** creates an inspection when you post a quantity.<br>- **Only with Quantity** creates an inspection only when you post an output quantity.<br>- **Only with Scrap** creates an inspection only when you post output with scrap.|
   |**Assembly Trigger**|- **Never** means no automatic inspection creation.<br>- **When Output is posted** creates an inspection when you post assembly output.|
   |**Warehouse Movement Trigger**|- **Never** means no automatic inspection creation.<br>- **When Warehouse Movement is registered** creates an inspection when you register the movement of goods.|

1. On the **Bin Movements and Reclassifications** FastTab, specify the batches to use when you move inventory from one bin to another or change item tracking information. Your choice depends on whether your warehouse is set up to use directed put-away and pick. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
1. On the **Inventory Adjustments** FastTab, specify the item journal batch or warehouse item journal batch to use to reduce inventory quantities. Your choice depends on whether your warehouse is set up to use directed put-away and pick. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
<!--1. On the **Item Tracking** FastTab, in the **Tracking Before Finishing** field, specify whether to require item tracking before finishing an inspection:

   - **Allow without item tracking** allows inspections without lot or serial numbers.
   - **Allow only posted item tracking** requires you to post lot or serial numbers.
   - **Allow reserved or posted item tracking** allows lot or serial numbers that exist but aren't posted yet.
   - **Allow any non-empty value** allows any lot or serial value, even if they aren't in inventory.-->

1. In the **Quality inspection selection criteria** field, specify the inspections to consider when evaluating whether to block a document-specific transaction.
   
   - **Any inspection that matches** considers any inspection.
   - **Only the most recently modified inspection** uses the most recently modified inspection.
   - **Only the newest inspection/reinspection** uses the inspection with the highest reinspection number.
   - **Any finished inspection that matches** considers any finished inspection.
   - **Only the most recently modified finished inspection** uses the most recently modified finished inspection.
   - **Only the newest finished inspection/reinspection** uses the finished inspection with the highest reinspection number.

## Set up quality management notifications

The settings described in this article apply to everyone who uses quality management features. However, each user can decide whether they want to be notified every time an inspection is created. Their selections apply only to themselves.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **My Notifications**, and then choose the related link.
1. The following notifications are available for quality management:

   - **Quality Inspection created** notifies you when an inspection is created either manually or automatically.
   - **Assign Quality Inspection to yourself** does the same, but gives you the chance to assign the inspection to yourself.

## Next steps

After you create the base data and complete the initial setup this article describes, there are still a few things to do. To learn more, go to:

- [Create Quality Inspection Templates](qms-quality-templates.md)
- [Set Up Inspection Generation Rules](qms-test-generation-rules.md)
- [Configure Quality Management Workflows (Optional)](qms-quality-workflows.md)

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Quality Management Overview](qms-overview.md)