---
title: Create quality inspection templates
description: Learn how to create and configure quality inspection templates to streamline quality testing processes and ensure compliance with quality standards.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 20400, 20408, 20404, 20402, 20416,
ms.date: 01/08/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Create quality inspection templates

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

Quality inspection templates define the measurements and attributes you want to collect during quality testing. Templates serve as the foundation for all quality tests, and contain:

- A **Template Code**, which is the unique identifier for the template.
- A **Description** that provides an idea of the purpose of the template.
- Tests and measurements, which are the individual quality measurements to collect.
- Pass/fail criteria, which are the acceptable ranges for each measurement.
- **Inspection Generation Rule** that define when the questions in the template are asked. 

You can create templates from scratch, or you can copy an existing template and then change the settings to suit your inspection needs. Learn more at [Create a new template](#create-a-new-template) or [Copy a template](#copy-a-template).

## Typical scenarios where templates help

One typical use is to inspect purchased materials. Some examples of tests in these inspections are dimension measurements, visual appearance checks, and material compliance verification.

Other examples are production output inspections, where you inspect the finished goods that you produce. Some examples of tests are functional performance tests, assembly quality checks, and final dimension verification.

Templates are also useful for inspections when production is in-process. Some examples of tests are intermediate measurements, process parameter verification, and work-in-progress quality gates.

## Create quality test

To set up a quality tests, follow these steps.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Tests**, and then choose the related link.
1. Choose **New** to create a new template.
1. In the **Description** field, enter a short description of the measurement. For example, **Example Measurement**, **Weight**, or **Dimension**. This description will be visible when recording inspections and will show up on the Certificate of Analysis and other reports. 
1. In the **Test Value Type** you can choose the value type collected for this test, such as entering numbers, selecting from a list of options, or choosing values from another table. The following list describes the purpose of each option.

   - **Decimal** or **Integer** for tests that allow numerical values.
   - **Boolean** if you want to record simples *Yes* or *No*.
   - **Text**, **Date**, or **Date and Time** - The inspector enters results as free text or a date. 
   - **Option** - Inspector select one of the values from a simple list you defined in the **Allowable Values** field.
   - **Lookup** - List of values is build dynamically based on **Lookup Table No.**, **Lookup Field No.** with respect of **Lookup Table Filter**. For example if you want to show a list of available reason codes from the **Reason code** table, then you would use table *231* with field *1* which represents the **Code** field on that table. You can also use table *20408* **Quality Test Lookup Value** and populate it with your own values. **Allowable Values** do not affect 
   - **Label** - you cannot enter value in this field, it is used for splitting lines when printing report.
  
1. In the **Allowed Values** you can specify what values inspection can enter. The format depends on the **Test Value Type**. Pass, fail or acceptance conditions are configured separately. For integer or decimal, you might enter something like '5..90' and the system accepts any value in this range. For the **Test Value Type** set to *Lookup* the **Allowable Values** field is ignored, though it is convenient to use for populateing values in the **Quality Test Lookup Value** page.
2. The **Result conditions** part inlcude pairs **Condition** and **Description** fields for each quality result where **Result Visibility** is set to *Priority*. The value in the **Condition** field depends on the **Test Value Type**. The following are examples for different types:
   - For integer or decimal, it can be '10..20' (range), '>=20' (greater than or equal), '<>0' (not equal to zero), '10|20|30' (equals 10, 20 or 30).
   - For text: 'A*' (starts with "A").
   - For date: 'TODAY..TODAY+30D' (Today through 30 days from today), '>=01/01/2026'(on or after specific date).


## Create a new template

To set up a quality inspection template, follow these steps.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Templates**, and then choose the related link.
1. Choose **New** to create a new template.
1. Fill in the **Template Code** field with a short name that indicates the purpose of the inspection. For example, enter **EXAMPLE** or **INCOMING-PARTS**.
1. Fill in the **Description** field. This field often contains an elaboration of the code. For example, **Example Template** or **Incoming Parts Inspection**.
1. In the **Sample Source** field, specify the size of the sample the test includes. Depending on your choice, the **Sample Amount** or **Sample %** fields display, so you can add those values. The **Sample quantity** in the created inspection cannot exceed the **Quantity (Base)** and if necessary it will be changed automatically on the inspection to be equal to the the source quantity. If you leave the **Sample Source** field blank, the amount or percentage fields don't display. 
1. Add the tests that represent what the inspection measures.
2. If necessary you can override conditions frorm tests for specific inspection template requirements.

## Assign a test generation rule

The next step is to use the **Inspection Generation Rules** action to create a generation rule for your template. Templates connect to automated inspection creation through inspection generation rules. Learn more at [Set up inspection generation rules](qms-test-generation-rules.md).

## Copy a template

You can copy templates to create new templates based on their settings. Select a template, and then choose the **Copy Template** action to create a duplicate. You can modify the fields on the new template to suit your needs.

## Related information

[Configuring Quality Inspection Results](qms-configuring-grades.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Manual Inspection Creation](qms-manual-test-creation.md)  
[Quality Management Setup and Configuration](qms-setup.md)  
[Quality Management Overview](qms-overview.md)
