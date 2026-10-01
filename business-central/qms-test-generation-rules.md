---
title: Set up quality inspection generation rules
description: Learn how to configure inspection generation rules to automate quality inspections based on business transactions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416,
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up quality inspection generation rules

Quality inspection generation rules define when and how to automatically create quality inspections in response to business transactions. These rules connect your quality inspection templates to specific business processes.

An inspection generation rule defines when you want to ask a set of questions or collect the data you want. You define the questions and data, such as measurements, in your quality inspection template. You connect a template to a source table, and set the criteria to use that template with the table filter.

For ordinary manual and automatic creation, [!INCLUDE [prod_short](includes/prod_short.md)] evaluates enabled rules in ascending **Sort Order**. It checks the source table and condition filter, followed by item and attribute filters when an item is available. The first matching rule supplies the template, and other matching rules aren't used for that creation attempt.

When you have multiple rules, avoid unintended overlaps. Give specific rules lower sort-order values and general fallback rules higher values.

## Types of source documents

You can create inspection generation rules for various types of source documents.

- **Purchase** rules can use purchase lines and item-tracking lines and can trigger when purchase orders are released or received.
- **Production** rules can use production routing lines and can trigger when production orders are released or refreshed, or when output is posted.
- **Assembly** rules can create inspections when assembly output is posted.
- **Warehouse** rules can use warehouse receipt or warehouse entry data and can trigger when receipts are created or posted or movements are registered.
- **Returns and transfers** can create inspections when sales return receipts or transfer receipts are posted.

## Set up a quality inspection generation rule manually

You might want to create an inspection generation rule manually when you have custom or complex filtering requirements.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
1. Choose **New**.
1. In the **Sort Order** field, specify how early you want [!INCLUDE [prod_short](includes/prod_short.md)] to find this template based on the rule. Lower sort order numbers are chosen first.
1. In the **Template Code** field, choose the template to use as the basis for the quality inspection.
1. In the **Intent** field, specify the type of source document that the rule applies to.
1. In the **Table** field, choose a table that's relevant for the type of source document you chose in the **Intent** field. For example, if you chose **Warehouse**, you should probably choose the **Warehouse Receipt Line** table.
1. In the **Condition Filter**, **Item Filter**, and **Attribute Filter** fields, choose one or more fields from the table you just selected to use as the filter that determines when to use this template.
1. In the **Activation Trigger** field, choose how source actions and automatic triggers can use the rule:

   - **Manual or Automatic**: Both the manual and automatic creation methods are enabled.
   - **Manual only**: Allow actions that users run, but not automatic triggers.
   - **Automatic only**: Allow automatic creation when the corresponding event is triggered, for example, when you post a receipt or purchase transaction.
   - **Disabled**: Prevent inspection creation from the rule.

   Scheduled processing can use any rule that isn't **Disabled**, regardless of the manual or automatic selection.

1. Depending on your selection in the **Intent** field, specify when to trigger the creation of inspections for assembly, production, purchase orders, sales returns, transfer orders, or warehouse receipts and movements. 

   > [!TIP]
   > You can only choose an option for the trigger that corresponds to your selection in the **Intent** field.

1. In the **Schedule Group** field, specify a group that allows a schedule to refer to multiple inspection generation rules. The schedule group creates a job queue entry for quality management.

## Use assisted setup guides to create inspection generation rules

[!INCLUDE [prod_short](includes/prod_short.md)] provides assisted setup guides that can speed up the process of creating inspection generation rules. Setup guides are available for:

- Receiving goods and materials
- Moving inventory between bins
- Inspecting production

### Create a receiving rule (purchases)

This rule is for inspecting goods for purchase receipts.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
1. Choose the **Create Receiving Rule** action.
1. In the **Choose template** field, choose the template you're creating the rule for.
1. Turn on the toggle for the type of receiving rule to create. You can only choose one type.
1. Choose **Next**.
1. In the **Location**, **Vendor No.**, and **Purchasing Code** fields, specify the purchase receipts that the rule applies to.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Choose **Next**.
1. Optionally, specify a specific item, category, or inventory posting group that creates inspections according to the rule.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Choose **Next**.
1. Review the filters you set, and add more if needed.
1. In the **Automatically Create Inspection** field, specify a trigger to automatically create an inspection when you receive a product for a purchase order.
1. Select **Finish**.

### Create a bin movement rule

For example, this rule is typically used to move noncompliant goods to a quarantine bin.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
1. Choose the **Create Bin Movement Rule** action.
1. In the **Choose template** field, choose the template you're creating the rule for.
1. Choose **Next**.
1. Specify the location, zone, and/or bin that creates an inspection when you put goods in them.
1. To create inspections only for put-aways, turn on the **Just put-aways** toggle.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Choose **Next**.
1. Optionally, specify a specific item, category, inventory posting group, or vendor that creates inspections according to the rule.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Choose **Next**.
1. Review the filters you set, and add more if needed.
1. In the **Automatically Create Inspection** field, specify a trigger to automatically create an inspection when you put goods in the bins you specified.
1. Select **Finish**.

### Create a production rule

This rule is often used for inspecting production output.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
1. Choose the **Create Production Rule** action.
1. In the **Choose template** field, choose the template you're creating the rule for.
1. Choose **Next**.
1. Optionally, specify **Location**, **From Bin**, **To Bin**, **Routing No.**, **Operation No.**, **Work Center No.**, **Machine No.**, or **Description** to filter the production routing lines that create inspections.
1. To filter on other production routing-line fields, select **Click here to choose advanced fields...**.
1. Choose **Next**.
1. Optionally, specify **Specific Item**, **Category**, or **Inventory Posting Group**.
1. To filter on other item fields, select **Click here to choose advanced fields...**.
1. Choose **Next**.
1. Review **Filters** and **Item Filter**, and change them if needed.
1. In the **Automatically Create Inspection** field, specify a trigger to automatically create an inspection for production.
1. Select **Finish**.

To create a rule for assembly output, use the separate **Create Assembly Rule** action.

<!--### Examples of filters and rules

The following are a few examples of inspection generation rules.

#### Example of a basic, item-based rule

Use an item-based rule to inspect all receipts of a specific item.

|Field  |Value  |
|---------|---------|
|Table     |  Purchase Line       |
|Item No. Filter     |  <\item number>       |
|Purchase Trigger     |  When Purchase Order is Received       |
|Other Filters     |  (blank for universal application)       |

#### Example of a location-specific rule

Use a location-specific rule to inspect all items at a specific location.

|Field  |Value  |
|---------|---------|
|Table     |  Purchase Line       |
|Location Code Filter     |  <\location code>       |
|Purchase Trigger     |  When Purchase Order is Received       |
|Item Filter     |  (blank for universal application)       |

#### Example of a vendor-specific rule

Use a vendor-specific rule for enhanced inspecting items from a specific vendor.

|Field  |Value  |
|---------|---------|
|Source Type     |  Purchase Line       |
|Vendor No. Filter     |  <\vendor number>       |
|Purchase Trigger     |  When Purchase Order is Received       |
|Template     |  Enhanced inspection template       | -->

## Create quality management workflows

If you're automating the process of creating quality inspections, the next step is to set up quality management workflows. Workflows can automatically run business actions when quality inspections are created, finished, or when specific conditions are met. Learn more in [Quality management workflows](qms-quality-workflows.md).

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Create an inspection manually from item tracking](qms-purchase-receipt-testing-simple.md)  
[Create a sampled inspection automatically from production output](qms-production-output-testing.md)  
[Work with quality inspections](qms-manual-test-creation.md)  
[Quality Management Overview](qms-overview.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]