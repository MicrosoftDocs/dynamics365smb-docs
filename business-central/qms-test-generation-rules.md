---
title: Set up quality inspection generation rules
description: Learn how to configure inspection generation rules to automate quality inspections based on business transactions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up quality inspection generation rules

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

Quality inspection generation rules define when and how to automatically create quality inspections in response to business transactions. These rules connect your quality inspection templates to specific business processes.

An inspection generation rule defines when you want to ask a set of questions or collect the data you want. You define the questions and data, such as measurements, in your quality inspection template. You connect a template to a source table, and set the criteria to use that template with the table filter. When a template meets the filter criteria, that template is used. If multiple templates meet the criteria, the template with the lowest sort order is used.

Inspection generation rules control:

- When to create inspections (triggers).
- Which templates to use for inspections.
- Which items, locations, or documents create inspections.
- How to create inspections, that is, either automatically or manually.

When you have multiple rules, avoid overlaps. Design your rules to minimize unintended creation of multiple inspections. Use specific filters for special cases, and maintain documentation of rule interactions.

## Types of source documents

You can create inspection generation rules for various types of source documents.

- **Purchase** documents create inspections based on purchase order transactions, and trigger when you post purchase receipts. They support filters for vendors and items.
- **Production** creates inspections based on production output or assembly orders, and trigger when you post output. They support filters for routes, work centers, and operations.
- You can also create rules for **Sales Return**, **Warehouse Receipt**, **Warehouse Movement**, **Transfer**, and **Assembly** documents.

## Set up a quality inspection generation rule manually

You might want to create an inspection generation rule manually when you have custom or complex filtering requirements.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
1. In the **Sort Order** field, specify how early you want [!INCLUDE [prod_short](includes/prod_short.md)] to find this template based on the rule. Lower sort order numbers are chosen first.
1. In the **Intent** field, specify the type of source document that the rule applies to.
1. In the **Table** field, choose a table that's relevant for the type of source document you chose in the **Intent** field. For example, if you chose **Warehouse**, you should probably choose the **Warehouse Receipt Line** table.
1. Optionally, in the **Condition Filter**, **Item Filter**, and **Attribute Filter** fields, choose one or more fields to use as the filter that determines when to use this template.
1. In the **Activation Trigger** field, choose one of the following options:

   - **Manual or Automatic**: Both methods are enabled.
   - **Manual Only**: Only allow manual inspection creation.
   - - **Automatic Only**: Automatic creation when the corresponding event is triggered, for example, when you post a receipt or purchase transaction.
   - **Disabled**: No automatic inspection creation.

1. Depending on your selection in the **Intent** field, specify when to trigger the creation of inspections for assembly, production, purchase, and warehouse receipts. 

   > [!TIP]
   > You can only select an option for the trigger that corresponds to your selection in the **Intent** field.

1. In the **Schedule Group** field, specify a group that allows a schedule to refer to multiple inspection generation rules. The schedule group creates a job queue entry for quality management.

## Use assisted setup guides to create inspection generation rules

[!INCLUDE [prod_short](includes/prod_short.md)] provides assisted setup guides that can speed up the process of creating inspection generation rules. Guides are available for receiving goods and materials, moving inventory between bins, and inspecting production. 

### Create a receiving rule (purchases)

This rule is best for inspecting goods for purchase receipts.

1. [!INCLUDE [prod_short](includes/prod_short.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
1. Choose the **Create Receiving Rule** action.
1. In the **Choose Template field, select the template you're creating the rule for.
1. Turn on the toggle for the type of receiving rule to create. You can only choose one type.
1. Choose **Next**.
1. In the **Location**, **Vendor No.**, and **Purchasing Code**, fields specify the location, vendor, or purchasing code can create inspections according to the rule.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Choose **Next**.
1. Optionally, specify a specific item, category, or inventory posting group that creates inspections according to the rule.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Choose **Next**.
1. Review the filters you set, and add more if needed. 
1. In the **Automatically Create Test** field, specify a trigger to automatically create an inspection when you receive a product for a purchase order.

### Create a bin movement rule

For example, this rule is typically used to move noncompliant goods to a quarantine bin.

1. [!INCLUDE [prod_short](includes/prod_short.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
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
1. In the **Automatically Create Test** field, specify a trigger to automatically create an inspection when you put goods in the bins you specified.

### Create a production rule

This rule is often used for inspecting production output.

1. [!INCLUDE [prod_short](includes/prod_short.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
1. Choose the **Create Production Rule** action.
1. In the **Choose template** field, choose the template you're creating the rule for.
1. Choose **Next**.
1. Depending on whether you're creating the rule for production or assembly orders, turn on the appropriate toggle. You can choose only one.
1. Choose **Next**.
1. Choose the filters that determine when to create an inspection for the production routing lines.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Choose **Next**.
1. Optionally, specify a specific item, category, or inventory posting group that creates inspections according to the rule.
1. Optionally, you can choose the **Click here to choose advanced fields** link to add more filters.
1. Review the filters you set, and add more if needed. 
1. In the **Automatically Create Test** field, specify a trigger to automatically create an inspection for production.

<!--

CONSIDER WHETHER THESE EXAMPLES ARE USEFUL ELSEWHERE

### Examples of filters and rules

The following sections provide examples of inspection generation rules.

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

#### Create a vendor-specific rule

Use a vendor-specific rule for enhanced inspecting items from a specific vendor.

- **Source Type**: **Purchase Line**
- **Vendor No. Filter**: <\vendor number>
- **Purchase Trigger**: **When Purchase Order is Received**
- **Template**: Enhanced inspection template -->

<!--

MOVE THIS CONTENT TO A DEDICATED TROUBLESHOOTING ARTICLE

### Troubleshooting test generation rules

The following sections describe typical issues and suggest solutions.

#### No inspections are created

- Double-check you filter configuration.
- Verify your trigger settings.
- Confirm that you assigned the correct template.

#### Too many inspections are created

- Look for rules that overlap.
- Make your filters more specific.
- Double-check the order of your rules.

#### The wrong template is applied

- Verify the template assignment in the rule.
- Double-check your rule priority and order.
- Review your filter logic. -->

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Purchase Receipt Inspections without Warehouse Handling](qms-purchase-receipt-testing-simple.md)  
[Production Output Quality Inspections](qms-production-output-testing.md)  
[Manual Inspection Creation](qms-manual-test-creation.md)  
[Quality Management Overview](qms-overview.md)