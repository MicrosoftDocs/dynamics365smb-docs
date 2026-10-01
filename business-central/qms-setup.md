---
title: Quality management setup and configuration 
description: Learn how to set up and configure quality management features, including prerequisites, initial setup steps, and common scenarios.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management setup and configuration

This article explains the initial setup and configuration of quality management features.

## Prerequisites

- Make sure that the **Quality Management** extension is installed.

  The extension is preinstalled for all new environments. For existing environments, install it from the **Extension Management** page or get it from [Microsoft Marketplace](https://marketplace.microsoft.com/product/PUBID.microsoftdynsmb%7CAID.bc_qualitymanagement%7CPAPPID.bc7b3891-f61b-4883-bbb3-384cdef88bec). Learn more about installing extensions at [Installing and Uninstalling Extensions](ui-extensions-install-uninstall.md#install).

- Ensure that users have the right permissions. Quality Management provides three role-based permission sets and one integration permission set:

  |Permission set  |Purpose  |
  |---------|---------|
  |**Quality Admin & Supervisor**     |Full access to all quality management configuration and data, including setup, templates, tests, generation rules, and inspections.        |
   |**Quality Inspector**     |Can take ownership of unassigned inspections, record test values, and finish inspections, but can't change setup, templates, generation rules, or assign inspections to other users. You must explicitly assign this permission set to users who perform inspections.         |
  |**Quality Auditor**     |Read-only access to all quality data for review and reporting.         |
   |**Quality Inspection - Create** |Provides the minimum quality management integration permissions for users whose transactions create inspections manually or automatically. Depending on a user's license and assigned permission sets, this access might already be included. |

  Learn more at [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

### Actions that require the Quality Admin & Supervisor role

Some actions on quality inspections are restricted to users who have the **Quality Admin & Supervisor** permission set (or SUPER permissions). Users who only have the **Quality Inspector** permission set can't perform these actions, even if they have general data modification permissions.

  |Action  |Description  |
  |--------- | --------- |
   | Assign an inspection to another user  | Inspectors can take ownership of unassigned inspections. Only an admin or supervisor can assign an inspection to another user or change another user's assignment.         |
  | Delete a finished inspection | Only an admin or supervisor can delete an inspection that has already been finished.         |
  | Change quantities on an inspection  | Only an admin or supervisor can change the values in the **Quantity**, **Passed Quantity**, **Failed Quantity**, or **Sample Size** fields on an inspection.         |
  | Reopen a finished inspection     | Only an admin or supervisor can reopen an inspection that is finished.         |

  If a user without the required role attempts one of these actions, [!INCLUDE [prod_short](includes/prod_short.md)] displays an error message that indicates that the user doesn't have the necessary permissions.

## Typical setup scenarios

To explore quality management with sample configuration and transactions, select **Install Demo Data** on the **Quality Management Setup** page. If the supporting extension isn't installed, the action opens Microsoft Marketplace so you can install the **Quality Management Contoso Coffee Demo Dataset**. Run the action again to choose and generate the required Contoso Coffee modules. For detailed instructions, see [Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md).

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

### Run the assisted setup

The assisted setup helps each user open the Quality Manager role center and review the quality management features available to them.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Assisted Setup**, and then select the related link.
2. Select **Quality Management**.
3. Select **Open My Settings**.
4. In **Role**, select **Quality Manager**, and then close the **My Settings** page.
5. Return to the assisted setup and select **Done**.

The assisted setup doesn't create quality tests, templates, generation rules, or demo data. Configure those records on their respective pages, or install the Contoso Coffee demo data.

### Set up quality management

The following steps describe settings you can use to get started with quality management, and manage features on an ongoing basis.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Management Setup**, and then choose the related link.
1. On the **General** FastTab, configure settings as described in the following table.

   |Field  |Description  |
   |---------|---------|
   |**Quality Inspection Nos.** | Specify the default number series to use for quality inspection documents when there isn't a number series defined on a quality inspection template. The number series defined on a template takes precedence.  |
   |**Inspection Creation Option** | Specify when to create a new inspection:<br><br>- **Always create new inspection** creates a new inspection every time, and doesn't search for existing inspections.<br>- **Create a reinspection if matching inspection is finished** searches for an existing, finished inspection that matches. If it finds one, it creates a reinspection. If it doesn't find one, it creates a new inspection.<br>- **Always create a reinspection** searches for an existing inspection. If it finds one, it creates a reinspection. If it doesn't find one, it creates a new inspection.<br>- **Use existing open inspection if available** searches for an existing, open inspection. If it finds an open inspection, it reuses it without any changes. If it finds an inspection that matches but is finished, or doesn't find a matching inspection, it creates a new inspection.<br>- **Use any existing inspection if available** searches for an existing inspection. If it finds one, it reuses it regardless of its status. If it doesn't find one, it creates a new inspection.<br><br>**Important:** When an existing inspection is reused, the test data (status, results, measurements) remains unchanged.<br><br>**Tip:** If you automate inspection creation but manually create an inspection, for example, for the first receipt of a lot that you'll receive in multiple shipments, and you want automation to reuse that inspection for subsequent receipts, choose **Use existing open inspection if available** or **Use any existing inspection if available**. Then, in the **Inspection Search Criteria** field, choose **By Item Tracking** to find inspections by lot or serial numbers.  |
   |**Inspection Search Criteria** | Specify the search criteria to use to find existing inspections. All of the options in the **Inspection Creation Option** field use this setting, with the exception of **Always create a new inspection**, which skips the search entirely.<br><br>- **By Standard Source Fields** searches by template, source table, document number, item, variant, and lot, serial, and package numbers. Use this option for the most comprehensive matching.<br>- **By Source Record** searches by the specific source record ID that triggered the inspection. Use this option when you want to find inspections linked to a specific document line.<br>- **By Item Tracking** searches primarily by item number, variant, and lot, serial, and package numbers. This option ignores the source document. Use this option to find inspections for a specific lot or serial number across different documents.<br>- **By Document and Item only** searches by document number and item only, and ignores lot, serial, and package numbers. Use this option to find inspections for an item on a document, regardless of tracking information.<br><br>**Note:** The search always returns the most recent inspection with the highest **Re-inspection No.** that matches the criteria.    |
   |**Certificate of Analysis Contact** | Specify the contact who appears in the signature block on the **Certificate of Analysis** report. This contact is typically your quality manager, lab director, or the person authorized to certify that a batch meets specifications. When set, the report shows the contact's name, job title, and address. When left blank, the signature block is empty. To set this field, you need a contact record for the person in [!INCLUDE [prod_short](includes/prod_short.md)].        |
   |**Maximum Rows To Fetch in Lookups** | Specify the maximum number of rows to fetch on data lookups. Keep the number as low as possible to increase usability and performance.        |
   |**Additional Picture Handling** | Specify what to do with pictures.<br><br>- **None** means not to take an action with pictures.<br>- **Save as attachment** attaches the picture as a document.<br>- **Save as attachment and upload to OneDrive** attaches the picture and uploads it to OneDrive.        |

1. On the **Generation Rule Trigger Defaults** FastTab, configure default trigger values for different types of documents, as described in the following table.

   |Field  |Options  |
   |---------|---------|
   |**Warehouse Receipts Trigger** | - **Never** means no automatic inspection creation.<br>- **When Warehouse Receipt is created** creates an inspection when you create a warehouse receipt.<br>- **When Warehouse Receipt is posted** creates an inspection when you post a warehouse receipt.        |
   |**Purchase Orders Trigger** | - **Never** means no automatic inspection creation.<br>- **When Purchase Order is received** creates an inspection when you post a purchase order receipt.<br>- **When Purchase Order is released** creates an inspection when you release a purchase order.<br><br>**Note:** Posting an open purchase order automatically releases it and triggers inspection creation. If posting fails, the order returns to **Open**, but the inspection remains, so another posting attempt might create another inspection depending on the **Inspection Creation Option** setting.        |
   |**Sales Returns Trigger** | - **Never** means no automatic inspection creation.<br>- **When Sales Return is received** creates an inspection when you post a sales return order receipt.        |
   |**Transfer Orders Trigger** | - **Never** means no automatic inspection creation.<br>- **When Transfer Order is received** creates an inspection when you post a transfer order receipt.        |
   |**Production Order Trigger**| - **Never** means no automatic inspection creation.<br>- **When Production Output is posted** creates an inspection when you post production output.<br>- **When Production Order is released** creates an inspection when you release a production order.<br>- **When a Released Production Order is refreshed** creates an inspection when you refresh a production order that is already released.|
   |**Prod. trigger output condition**|- **Any Output Entry** creates an inspection when you enter any output.<br>- **Any Quantity Output** creates an inspection when you post a quantity.<br>- **Only with Quantity** creates an inspection only when you post an output quantity.<br>- **Only with Scrap** creates an inspection only when you post output with scrap.|
   |**Assembly Trigger**|- **Never** means no automatic inspection creation.<br>- **When Output is posted** creates an inspection when you post assembly output.|
   |**Warehouse Movement Trigger**|- **Never** means no automatic inspection creation.<br>- **When Warehouse Movement is registered** creates an inspection when you register the movement of goods.|

1. On the **Bin Movements and Reclassifications** FastTab, specify the batches to use when you move inventory from one bin to another or change item tracking information. Your choice depends on whether your warehouse is set up to use directed put-away and pick. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
1. On the **Inventory Adjustments** FastTab, specify the item journal batch or warehouse item journal batch to use to reduce inventory quantities. Your choice depends on whether your warehouse is set up to use directed put-away and pick. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
1. On the **Item Tracking** FastTab, in the **Item Tracking Before Finishing** field, specify whether to require item tracking before finishing an inspection:

   - **Allow without item tracking**: Use this option if you don't use lot or serial numbers, or if you have processes where inspections won't have known lot or serial numbers. For example, inspections created during production that prevent the product from being produced might not have a lot or serial number yet. Inspections without lot or serial numbers are permitted.
   - **Allow only posted item tracking**: Use this option if all lot or serial numbers must be posted before you can finish an inspection. For example, if you inspect finished goods the lot or serial number should exist. If you inspect lots when they're moved to a bin, the lot or serial number must exist.
   - **Allow reserved or posted item tracking**: Use this option if lot or serial numbers need to be in the system but might not yet be posted. For example, lots that are being received or produced might not yet be received or produced, but do exist on your item tracking lines.
   - **Allow any non-empty value**: Use this option if you want to track lot or serial numbers that don't enter the system but need inspections to document why they didn't. For example, if you reject a lot during the receiving process and the failed lot is never put away. Or, if you're producing and know the intended lot or serial number but the in-progress item is discarded before it's posted to inventory. Inspections with lot or serial numbers that aren't in your inventory are permitted.

1. In the **Quality Inspection Selection Criteria** field, specify the inspections to consider when evaluating whether to block a document-specific transaction.

   - **Any inspection that matches** considers any inspection.
   - **Only the most recently modified inspection** uses the most recently modified inspection.
   - **Only the newest inspection/reinspection** uses the inspection with the highest reinspection number.
   - **Any finished inspection that matches** considers any finished inspection.
   - **Only the most recently modified finished inspection** uses the most recently modified finished inspection.
   - **Only the newest finished inspection/reinspection** uses the finished inspection with the highest reinspection number.

## Set up quality management notifications

Each user can enable or disable quality management notifications. Their selections apply only to themselves.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **My Notifications**, and then choose the related link.
1. The following notifications are available for quality management:

   - **Quality Inspection created** controls notifications for newly created inspections.
   - **Assign Quality Inspection to yourself** controls assignment prompts for eligible unassigned inspections.

For information about taking ownership of and unassigning inspections, see [Work with quality inspections](qms-manual-test-creation.md#assign-and-perform-an-inspection).

## Next steps

After you create the base data and complete the initial setup this article describes, there are still a few things to do. To learn more, go to:

- [Create Quality Inspection Templates](qms-quality-templates.md)
- [Set Up Inspection Generation Rules](qms-test-generation-rules.md)
- [Configure Quality Management Workflows (Optional)](qms-quality-workflows.md)

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)

[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)

[Quality Management Overview](qms-overview.md)
