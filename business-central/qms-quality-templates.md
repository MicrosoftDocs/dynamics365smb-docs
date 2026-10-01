---
title: Create quality inspection templates
description: Learn how to create and configure quality inspection templates to streamline quality testing processes and ensure compliance with quality standards.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416,
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Create quality inspection templates

Quality inspection templates define the measurements and attributes you want to collect during quality testing. Templates serve as the foundation for all quality tests, and contain:

- A **Template Code**, which is the unique identifier for the template.
- A **Description** that provides an idea of the purpose of the template.
- Tests and measurements, which are the individual quality measurements to collect.
- Pass/fail criteria, which are the acceptable ranges for each measurement.

You can create templates from scratch, or you can copy an existing template and then change the settings to suit your inspection needs. Learn more at [Create a new template](#create-a-new-template) or [Copy a template](#copy-a-template).

## Typical scenarios where templates help

One typical use is to inspect purchased materials. Some examples of tests in these inspections are dimension measurements, visual appearance checks, and material compliance verification.

Other examples are production output inspections, where you inspect the finished goods that you produce. Some examples of tests are functional performance tests, assembly quality checks, and final dimension verification.

Templates are also useful for inspections when production is in-process. Some examples of tests are intermediate measurements, process parameter verification, and work-in-progress quality gates.

## Create a quality test

To set up a quality test, follow these steps:

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Tests**, and then choose the related link.
1. Select **New** to create a quality test.
1. In the **Code** field, enter a unique identifier for the test.
1. In the **Description** field, enter a short description of the measurement. For example, **Example Measurement**, **Weight**, or **Dimension**. This description is visible when recording inspections and appears on the Certificate of Analysis and other reports.
1. In the **Test Value Type** field, choose the type of value that the inspector enters or selects. The following list describes the options.

   - **Decimal** or **Integer** for tests that allow numerical values.
   - **Boolean** for tests that record **Yes** or **No**.
   - **Text**, **Date**, or **Date and Time** for free text, a date, or a date and time.
   - **Option** to let the inspector select from a list that you define in the **Allowable Values** field.
   - **Table Lookup** to build a list from the **Lookup Table No.**, **Lookup Field No.**, and **Lookup Table Filter** fields. For example, to show reason codes, use table 231 and field 1, which is the **Code** field. You can also add your own values to the **Quality Test Lookup Values** page, which uses table 20408.
   - **Label** to add a noneditable heading that separates lines on inspection reports.
   - **Text Expression** to calculate text by using the **Expression Formula** field.
  
1. In the **Allowable Values** field, specify the values that an inspector can enter. The format depends on the **Test Value Type**. Configure pass, fail, and acceptance conditions separately. For an integer or decimal test, enter `5..90` to allow any value in that range. The field doesn't restrict a **Table Lookup** test because its values come from the configured lookup table.
1. The **Result conditions** section includes pairs of **Condition** and **Description** fields for each quality result where **Result Visibility** is set to **Promoted**. The value in the **Condition** field depends on the **Test Value Type**. The following are examples for different types:
   - For integer or decimal, it can be '10..20' (range), '>=20' (greater than or equal), '<>0' (not equal to zero), '10|20|30' (equals 10, 20 or 30).
   - For text: 'A*' (starts with "A").
   - For date: 'TODAY..TODAY+30D' (Today through 30 days from today), '>=01/01/2026'(on or after specific date).

> [!NOTE]
> You can't delete a quality test that is used by a quality inspection or inspection template.

## Create a new template

To set up a quality inspection template, follow these steps.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Templates**, and then choose the related link.
1. Choose **New** to create a new template.
1. Fill in the **Template Code** field with a short name that indicates the purpose of the inspection. For example, enter **EXAMPLE** or **INCOMING-PARTS**.
1. Fill in the **Description** field. This field often contains an elaboration of the code. For example, **Example Template** or **Incoming Parts Inspection**.
1. In the **Sample Source** field, specify the size of the sample the test includes. Depending on your choice, the **Sample Amount** or **Sample %** fields display, so you can add those values. The **Sample quantity** in the created inspection can't exceed the **Quantity (Base)** and if necessary it's changed automatically on the inspection to equal the source quantity. If you leave the **Sample Source** field blank, the amount or percentage fields don't display. 
1. Add the tests that represent what the inspection measures.
1. If necessary, you can override conditions from tests for specific inspection template requirements.

## Assign an inspection generation rule

The next step is to use the **Inspection Generation Rules** action to create a generation rule for your template. Templates connect to automated inspection creation through inspection generation rules. Learn more at [Set up inspection generation rules](qms-test-generation-rules.md).

## Copy a template

You can copy templates to create new templates based on their settings. Select a template, and then choose the **Copy Template** action to create a duplicate. You can modify the fields on the new template to suit your needs.

## Related information

[Configuring Quality Inspection Results](qms-configuring-grades.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Work with quality inspections](qms-manual-test-creation.md)  
[Quality Management Setup and Configuration](qms-setup.md)  
[Quality Management Overview](qms-overview.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
