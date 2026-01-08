---
title: Quality management setup and configuration 
description: Learn how to set up and configure quality management features, including prerequisites, initial setup steps, and common scenarios.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management setup and configuration

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article takes you through the initial setup and configuration of quality management features.

## Prerequisites

Before you set up quality management, ensure that you have:

- The Quality Management app installed.
- Administrative permissions in [!INCLUDE [prod_short](includes/prod_short.md)].
- Understood your quality control requirements.
- Microsoft Dynamics 365 Business Central (on-premises or cloud)

   > [!NOTE]
   > The Premium experience is required for production capabilities. If you don't need those, you can use the Essential experience.

## Initial setup steps

### Run the assisted setup guide

Quality management includes an assisted setup guide that can help you configure basic settings.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Set up Quality Management**, and then choose the related link.
1. Follow the steps in the guide. Learn more at [Assisted Setup Wizard](qms-assisted-setup.md).

### Configure base data

Ensure you configured base data in [!INCLUDE [prod_short](includes/prod_short.md)] as described in the following table.

|Data  |Description  |
|---------|---------|
|Locations     |- Configure the locations where you do quality inspections.<br>- Set up warehouse handling, if necessary. For example, receipts, put-aways, and so on.<br>- Define bins for your quality inspection areas.         |
|Items     |- Configure item tracking codes for lots, serials, or packages, as needed.<br>- Set up lot number series for automatic lot assignments.<br>- Ensure that the correct inventory posting groups are assigned to items. |
|Vendors and customers     |- Configure vendors for purchase receipt inspections.<br>- If quality inspections affect sales processes, set up customers.       |

### Set up quality management

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Management Setup**, and then choose the related link.
1. Configure general settings, as described in the following table.

   |Field  |Description  |
   |---------|---------|
   |**Quality Inspection Nos.** | Specify the default number series to use for quality inspection documents when there isn't a number series defined on a quality inspection template. The number series defined on a template takes precedence.  |
   |**Create Test Behavior** | Specify when to create a new inspection:<br><br>- **Always create new inspection** creates a new inspection every time, and doesn't search for existing inspections.<br>- **Create reinspection if matching inspection is finished** searches for an existing, completed inspection that matches. If it finds one, it creates a reinspection. If it doesn't find one, it creates a new inspection.<br>- **Always create reinspection** searches for an existing inspection. If it finds one, it creates a reinspection. If it doesn't find one, it creates a new inspection.<br>- **Use existing open inspection if available** searches for an existing, open inspection. If it finds an open inspection, it reuses it without any changes. If it finds an inspection that matches but is completed, or doesn't find a matching inspection, it creates a new inspection.<br>- **Use any existing inspection if available** searches for an existing inspection. If it finds one, it reuses it regardless of its status. If it doesn't fine one, it creates a new inspection.<br><br>**Important:** When an existing inspection is reused, the test data (status, results, measurements) remains unchanged.<br><br>**Tip:** If you automate inspection creation but manually create an inspection, for example, for the first receipt of a lot that you'll receive in multiple shipments, and you want automation to reuse that inspection for subsequent receipts, choose **Use existing open inspection if available** or **Use any existing inspection if available**. Then, in the **Find Existing Behavior** field, choose **By Item Tracking** to find inspections by lot or serial numbers.  |
   |**Find Existing Behavior** | Specifies the search criteria to use to find existing inspections. All of the options in the **Create Inspection Behavior** field use this setting, with the exception of **Always Create New Inspection**, which skips the search entirely.<br><br>- **By Standard Source Fields** searches by template, source table, document number, item, variant, and lot, serial, and package numbers. Use this option for the most comprehensive matching.<br>- **By Source Record** searches by the specific source record ID that triggered the inspection. Use this option when you want to find inspections linked to a specific document line.<br>- **By Item Tracking** searches primarily by item number, variant, and lot, serial, an package numbers. This option ignores the source document. Use this option to find inspections for a specific lot or serial number across different documents.<br>- **By Document and Item only** searches by document number and item only, and ignores lot, serial, and package numbers. Use this option to find inspections for an item on a document, regardless of tracking information.<br><br>**Note:** The search always returns the most recent inspection (highest retest number) that matches the criteria.    |
   |**Conditional Lot Find Behavior**| Specifies the inspections to consider when evaluating whether a document-specific transaction is blocked.<br><br>- **Any inspection that matches** considers any inspection.<br>- **Only the most recently modified test** uses the most recently modified inspection.<br>- **Only the newest inspection/reinspection** uses the inspection with the highest reinspection number.<br>- **Any finished inspection that matches** considers any finished inspection.<br>- **Only the most recently modified finished inspection** uses the most recently modified finished inspection.<br>- **Only the newest finished inspection/reinspection** uses the finished inspection with the highest reinspection number.        |
   |**COA Contact No.** | Specifies the contact details that appear on the **Certificate of Analysis** report when supplied.        |
   |**Maximum Rows To Fetch on Field Lookups** | Specifies the maximum number of rows to fetch on data lookups. Keep the number as low as possible to increase usability and performance.        |
   |**Show Test Behavior** | Specifies whether to open the **Quality Inspection** page after an inspection is created.<br><br>- **Automatic and manually created inspections** opens inspections created both automatically and manually.<br>- **Only manually created inspections** opens only inspections created manually.<br>- **Do not show created inspections** never automatically opens created inspections.    |
   |**Picture Upload Behavior** | Specifies what to do with pictures.<br><br>- **Do nothing** means not to take an action with pictures.<br>- **Attach document** attaches the picture as a document.<br>- **Attach and upload to OneDrive** attaches the picture and uploads it to OneDrive.        |
   |**Workflow Integration Enabled** | When enabled, this option provides the events and responses for quality management that you need to work with workflows and approvals.        |

1. Configure settings for receiving, as described in the following table.

   |Field  |Description  |
   |---------|---------|
   |**Warehouse Receipts** | Specifies the default warehouse receipt trigger value for inspection generation rules.<br><br>- **Never** means no automatic inspection creation.<br>- **When Whse. Receipt is created** creates an inspection when you create a warehouse receipt.<br>- **When Whse. Receipt is posted** creates an inspection when you post a warehouse receipt.        |
   |**Purchase Orders** | Specify a default purchase trigger value for inspection generation rules.<br><br>- **Never** means no automatic inspection creation.<br>- **When Purchase Order is received** creates an inspection when you post a purchase order receipt.<br>- **When Purchase Order is posted** creates an inspection when you release a purchase order.        |
   |**Sales Returns** | Specifies a default sales return trigger value for inspection generation rules.<br><br>- **Never** means no automatic inspection creation.<br>- **When Sales Return is received** creates an inspection when you post a sales return order receipt.        |
   |**Transfer Orders** | Specifies a default transfer trigger value for inspection generation rules.<br><br>- **Never** means no automatic inspection creation.<br>- **When Transfer Order is received** creates an inspection when you post a transfer order receipt.        |

1. Configure settings for production, as described in the following table.

   |Column1  |Column2  |
   |---------|---------|
   |**Production - Create Test** | Specify a default production-related trigger value for inspection generation rules.<br><br>- **Never** means no automatic inspection creation.- **When Output is posted**: Creates an inspection when you post production output.<br- **When Order is released** creates an inspection when you release a production order.<br>- **When a released order is refreshed** creates an inspection when you refresh a released order.        |
   |**Auto Output Configuration** | Specify options for when to create an inspection automatically during the production process.<br><br>- **Any Output Entry**: Creates an inspection on any output.- **Any Quantity Output** creates an inspection when you post a quantity.<br>- **Only with Quantity** creates an inspection only when you post a quantity.<br>- **Only with Scrap** creates an inspection only when you post scrap.        |
   |**Assembly - Create Test**  | Specify a default assembly-related trigger value for inspection generation rules.<br><br>- **Never** means no automatic inspection creation.<br>- **When Output is posted** creates an inspection when you post assembly output.        |

1. Configure settings for inventory and warehousing, as described in the following table.

   | Field | Description   |
   |---------------------|-------|
   | **Create Inspection** | Specify a default warehousing-related trigger value for inspection generation rules.<br><br>- **Never** means no automatic inspection creation<br>- **Movement into Bin** creates an inspection when you register a warehouse movement. |
   | **Batch Name (Bin Movements)** | Specify the batch to use for bin movements and reclassifications for locations that don't use directed pick and putaway. |
   | **Whse. Batch Name (Bin Movements)** | Specify the batch to use for bin movements and reclassifications for locations that use directed pick and putaway. |
   | **Whse. Worksheet Name**| Specify the worksheet to use for warehouse movements for locations that use directed pick and putaway.            |
   | **Batch Name (Inventory Adjustments)** | Specify the batch to use for negative inventory adjustment item journals.                              |
   | **Whse. Batch Name (Inventory Adjustments)** | Specify the batch to use for negative inventory adjustment warehouse item journals.                  |

1. To configure settings for item tracking, in the **Tracking Before Finishing** field, specify whether to require item tracking before finishing an inspection:

   - **Allow missing item tracking** allows inspections without lot or serial numbers.
   - **Posted Item Tracking only** requires you to post lot or serial numbers.
   - **Reservation or posted** allows lot or serial numbers that exist but aren't posted yet.
   - **Any non-empty value** allows any nonempty lot or serial value, even if they aren't in inventory.

## Next steps

After you complete the initial setup, there are still a few things to do. To learn more, go to:

1. [Create Quality Inspection Templates](qms-quality-templates.md)
2. [Set Up Inspection Generation Rules](qms-test-generation-rules.md)
3. [Configure Workflows (Optional)](qms-quality-workflows.md)
<!--4. [Test Your Configuration](./testing-configuration.md)-->

## Typical setup scenarios

The following sections offer things to think about when you set up the app for certain scenarios.

### Purchase receipt inspections only

- Focus on purchase trigger configuration.
- Create templates for inspecting incoming goods.
- Set up rules for vendor-specific or item-specific testing.

### Production output testing only

- Focus on production trigger configuration.
- Create templates for finished goods inspection.
- Set up rules for routing-specific or work center-specific testing.

### Comprehensive quality system

- Configure both purchase and production triggers.
- Create multiple templates for different types of inspections.
- Set up workflows to automatically block and unblock lots.

## Troubleshooting setup issues

The following sections describe typical issues and suggest solutions.

### Quality inspections aren't created automatically

- Verify the trigger settings on the **Quality Management Setup** page.
- Double-check that you correctly configured your inspection generation rules.
- Ensure that you assigned templates to your inspection generation rules.

### Workflow events aren't available

- Verify that the **Enable Workflow Integration** is enabled on the **Quality Management Setup** page.
- Check that users are assigned the appropriate permissions.

## Related information

[Assisted Setup](qms-assisted-setup.md)  
[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Quality Management Overview](qms-overview.md)