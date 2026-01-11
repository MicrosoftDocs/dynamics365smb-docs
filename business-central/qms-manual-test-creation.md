---
title: Manual test creation
description: Learn how to manually create quality inspections for reactive testing, investigations, and spot checks.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 
ms.date: 01/11/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Manual inspection creation

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains various ways to manually create quality inspections. Manual inspection creation provides flexibility for:

- Reactive inspections, where you create inspections in response to discovered quality issues.
- Investigating specific lots or items due to concerns.
- Spot-checking, where you do random quality verification.
- Investigating customer complaints, where your inspections are related to external feedback.

Manual inspections use the same templates and configurations as automatic inspections.
<!--
## Prerequisites

There are a few things to set up before you can manually create inspections.

- Set up quality inspection templates. Learn more at [Create quality inspection templates](qms-quality-templates.md).
- Set up inspection generation rules with manual triggers. Learn more at [Set up inspection generation rules](qms-test-generation-rules.md).
- Make items available for inspections.
- Assign the **Quality Inspection** permission sets to users.

## Configure inspection generation rules

You can set up rules for generating inspections manually, or manually and automatically. This section describes how.

### Manual-only rules

Create rules specifically for manual inspection creation:

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Inspection Generation Rules**, and then choose the related link.
2. Create or modify rules, as follows:

   - **Purchase Trigger**: "Manual Only"
   - **Production Trigger**: "Manual Only"  
   - **Template Assignment**: Appropriate template
   - **Source Type**: Purchase line, production order routing line, and so on.

### Manual rules versus automatic rules

**Manual only rules**:

- Inspections are created only when you choose the **Create Inspections** action.
- Inspections aren't automatically created when you post.
- Manual inspections are ideal for reactive scenarios.

**Manual and automatic rules**:

- You can create inspections automatically and manually.
- Provide flexibility for both proactive and reactive inspections.
- Represents the most comprehensive approach to inspections.
-->

## Create tests manually

The following sections describe ways to manually create quality inspections.

### Create an inspection from item tracking lines

This method is best for lot-specific inspections when item tracking is already configured. It offers several advantages:

- Lot numbers automatically populated.
- Quantities automatically assigned.
- Direct connection to source document.

1. Open a source document, such as a purchase order, production order, and so on.
2. Choose the **Item Tracking Lines** action.
3. Select specific lot/serial number lines.
4. Choose the **Create Inspection** action.

### Create an inspection from purchase or production lines

This method is best for inspecting untracked items without specific lot requirements. Information from the source document is prefilled, but you might have to enter lot numbers manually.

1. Open a source document, and select a line.
2. Choose the **Create Inspection** action from the line.
3. Select the appropriate template, if you're prompted to.
4. Specify a lot number.

### Create an inspection from quality inspection templates

This method is best for creating inspections that are independent of specific documents. It has several advantages:

- Complete flexibility in inspection configuration
- Not tied to specific business transactions
- Ideal for investigation and spot-checking

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Templates**, and then choose the related link.
2. Select the template to use.
3. Choose the **Create Inspection** action.
4. Set up parameters for your inspection, as follows:

   - **Source**: Optionally, enter the source document reference.
   - **Item Number**: Select the item to inspect.
   - **Lot/Serial Number**: Enter a lot or serial number, if needed.
   - **Quantity**: Specify the quantity to inspect.

<!--
## Scenarios where you might create inspections manually

The following sections offer high-level, sample scenarios in which you might manually create quality inspections.

### Reactive inspections from a purchase

Reactive inspections are typically done in situations where you discover a quality issue after you receive goods from a purchase. In this case, you create the inspection from item tracking lines.

1. **Locate the purchase order**: Find the original purchase receipt.
2. **Access item tracking details**: Open item tracking lines.
3. **Select the problematic lots**: Choose the specific lots that have quality issues.
4. **Create inspection**: Generate an inspections for investigation.
5. **Complete the inspection**: Perform a detailed quality evaluation.

### Production quality investigations

For example, if a customer complains about a finished good you produced, you might want to inspect the quality of your production output. In this case, you create the inspection from a quality inspection template.

1. Choose the appropriate quality template.
2. Choose the **Create Inspection** action.
3. Configure the details:

   - **Item**: Select the finished item.
   - **Lot**: Specify the customer-reported lot number.
   - **Quantity**: Specify a quantity that gives a representative sample size.
4. Perform a detailed quality evaluation.

### Spot check inspections

Some businesses do spot-checks to verify quality at random times. In this case, you create inspections from purchase lines.

1. Select the items for spot checking.
2. Open the relevant purchase order.
3. Select the line, and then choose the **Create Inspection** action.
4. Add lot information, if needed.
5. Perform a detailed quality evaluation.

## Configuration options for inspections

The following sections describe the options for configuring inspections.

### Template selection

When you create inspections manually:

- **Automatic**: Inspection generation rules determine the template.
- **Manual selection**: Choose a template that suits the situation.
- **Multiple templates**: Create multiple inspections with different templates.

### Link to source documents

With a source document:

- The inspection links to the originating transaction.
- You maintain traceability.
- The source information is prepopulated.

Without a source document:

- You do an independent quality inspection that isn't linked to a specific transaction.
- You must manually configure the inspection.

### Item tracking specifications

For lot-tracked items:

- Specify the lot number when you create the test.
- [!INCLUDE [prod_short](includes/prod_short.md)] verifies that the lot exists.
- The lot information displays in the test.

For items you track with serial numbers:

- Enter the specific serial numbers.
- Run an individual inspection per serial number.
- Maintain detailed traceability.

For nontracked items:

- Create the inspection without tracking information.
- Run a quantity-based inspection that's suitable for bulk materials.

## Best practices for manual inspections

The following sections offer tips and best practices for doing manual inspections.

### Documentation requirements

Record the reason that you chose to create inspections manually, and document the quality concerns or triggers. It's a good idea to maintain an audit trail.

It's also important to document the results. Fill in all fields on the template, add notes about unusual findings, and link to corrective actions, if needed.

### Process integration

The workflow for reactive inspections might look as follows:

1. Identify a quality issue.
2. Manually create an inspection.
3. Do your investigation and analysis.
4. Take corrective actions.
5. Verify the inspection.

The following are some recommendations for inspection protocol:

- Use consistent inspection methods.
- Inspect appropriate sample sizes.
- Create good documentation.
- Use follow-up procedures.
-->
## Related information

[Purchase Receipt Inspection without Warehouse Handling](qms-purchase-receipt-testing-simple.md)  
[Production Output Quality Inspections](qms-production-output-testing.md)  
[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Quality Management Overview](qms-overview.md)