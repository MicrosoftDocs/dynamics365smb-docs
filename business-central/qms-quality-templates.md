---
title: Create quality inspection templates
description: Learn how to create and configure quality inspection templates to streamline quality testing processes and ensure compliance with quality standards.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 01/08/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Create quality inspection templates

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

Quality inspection templates define the measurements and attributes you want to collect during quality testing. Templates serve as the foundation for all quality tests, and contain:

- A **Template Code**, which is the unique identifier for the template.
- A **Description** that provides an idea of the purpose of the template.
- Fields and measurements, which are the individual quality measurements to collect.
- Pass/fail criteria, which are the acceptable ranges for each measurement.

You can create templates from scratch, or you can copy an existing template and then change the settings to suit your inspection needs. Learn more at [Create a new template](#create-a-new-template) or [Copy a template](#copy-a-template).

## Typical scenarios where templates help

One typical use is to inspect purchased materials. Some examples of tests in these inspections are dimension measurements, visual appearance checks, and material compliance verification.

Other examples are production output inspections, where you inspect the finished goods that you produce. Some examples of tests are functional performance tests, assembly quality checks, and final dimension verification.

Templates are also useful for inspections when production is in-process. Some examples of tests are intermediate measurements, process parameter verification, and work-in-progress quality gates.

## Create a new template

To set up a quality inspection template, follow these steps.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Templates**, and then choose the related link.
1. Choose **New** to create a new template.
1. Fill in the **Template Code** field with a short name that indicates the purpose of the inspection. For example, enter **EXAMPLE** or **INCOMING-PARTS**.
1. Fill in the **Description** field. This field often contains an elaboration of the code. For example, **Example Template** or **Incoming Parts Inspection**.
1. In the **Sample Source** field, specify the size of the sample the test includes. Depending on your choice, the **Sample Amount** or **Sample %** fields display, so you can add those values. If you leave the **Sample Source** field blank, the amount or percentage fields don't display.
1. To add the tests that represent what the inspection measures, choose the **Add Test(s) To This Template** action to start the **Quality Test Wizard**.
1. Depending on whether you want to add an existing test or create a new test, turn on or turn off the **New test** or **Existing tests** toggles.

   If you're adding an existing test, choose the test and then choose **Finish** to close the guide. If you're creating a new test, choose **Next** and continue to the next step. 
1. In the **Description** field, enter a short description of the measurement. For example, **Example Measurement**, **Weight**, or **Dimension**.
1. Choose the **Choose the type of data this will hold** link, and then enter a short name for the test and the type of data it contains.

   Depending on the type of data, the next steps in the guide differ. The following list describes the purpose of each option.

   - **A number** - Base the test on allowed numerical values. There are two ways to use this option. You can configure a range of numbers where you specify the upper and lower limits and pass or fail values, or an advanced configuration where you specify syntax and field conditions.
   - **A choice from a list** - Base the test on a simple list of values that you define, or on a table where you specify the fields to include.
   - **Free text** or **Date** - The inspector enters results as free text or a date. These options don't require extra configuration.
   - **Advanced Configuration** - Base the test on a type of value that you choose in the **Test Value Type** field. Depending on your choice, the information you must enter differs. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

1. Choose **Finish** to add the test and close the guide.

<!--### Field Configuration Example

The following are sample settings for a measurement field:

- **Description**: "Example Measurement"
- **Allowed Values**: 5 to 90 (the system accepts any value in this range)
- **Pass Values**: 10..20 - values between 10 and 20 result in a passing grade.

The following are the results of the sample settings:

- No value entered: "In Progress" grade (default).
- Values 5-9: "Fail" grade. The value is outside the pass range but within the allowed values.
- Values 10-20: "Pass" grade (meets pass criteria).
- Values 21-90: "Fail" grade because the value is outside the pass range but within the allowed values.
- Values outside 5-90: [!INCLUDE [prod_short](includes/prod_short.md)] rejects the entry because it's outside the allowed values. -->

## Copy a template

You can copy templates to create new templates based on their settings. Select a template, and then choose the **Copy Template** action to create a duplicate. You can modify the fields on the new template to suit your needs.

> [!NOTE]
> Before you activate a template and use it in production, validate its setup and results.

## Assign a test generation rule

If you're automating the creation of inspections, the next step is to use the **Inspection Generation Rules** action to create a generation rule for your template. Templates connect to automated inspection creation through inspection generation rules. Learn more at [Set up inspection generation rules](qms-test-generation-rules.md).

## Related information

[Configuring Quality Inspection Results](qms-configuring-grades.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Manual Inspection Creation](qms-manual-test-creation.md)  
[Quality Management Setup and Configuration](qms-setup.md)  
[Quality Management Overview](qms-overview.md)