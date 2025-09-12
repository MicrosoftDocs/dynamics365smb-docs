---
title: Handle External ESG reporting
description: Learn how to set up, run and export External ESG reports.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: Sustainability, ESG, emission, GHG, certificate, green
ms.search.form: 
ms.date: 09/11/2025
ms.service: dynamics-365-business-central

---

# Handle External ESG compliance reporting

The European Union's (EU) Corporate Sustainability Reporting Directive (CSRD) specifies how, and when, companies report on sustainability matters. To learn more about CSRD, go to [CSRD Directive](https://csrd-directive.eu/).

This article describes how to prepare your [!INCLUDE [prod_short](includes/prod_short.md)] to help your business meet CSRD requirements.

## Prerequisites

To use the features for External ESG reporting, you must have the following in place:

- A valid license for Power Apps.
- Deploy External ESG reporting. To learn more about how to deploy, go to [Deploy external reporting in Sustainability Manager](/industry/sustainability/external-reporting/deploy).

## Use External ESG reporting

External ESG reporting provides templates based on ESG standards or frameworks. The tool helps you create, complete, and manage approval of comprehensive reports across both quantitative and qualitative metrics.

If you're new to ESG reporting, the following articles can help you get started:

- To learn more about External ESG reporting, go to [Overview of external reporting in Sustainability Manager](/industry/sustainability/external-reporting/overview).
- To learn more about standard and framework reporting templates for ESG reporting, go to [Review standards](/industry/sustainability/external-reporting/standards#review-standards-1).

## Get started

The following sections describe each step in the process of setting up External ESG reporting.

### Integrate with Dataverse and enable data synchronization

Connect your [!INCLUDE [prod_short](includes/prod_short.md)] to [!INCLUDE [cds_long_md](includes/cds_long_md.md)], and enable data synchronization. To learn more, go to [Integrate with Microsoft Dataverse via data sync](admin-common-data-service.md).

For External ESG reporting, key parts of the integration with [!INCLUDE [cds_long_md](includes/cds_long_md.md)] are the integration table and field mappings. Integration table and field mappings specify the data that synchronizes and the direction of the synchronization. That is, whether data created in one app synchronizes to the other, or data synchronizes in both directions.

When you turn on the **Enable Dataverse Integration** toggle on the **Sustainability Setup** page, [!INCLUDE [prod_short](includes/prod_short.md)] creates the integration table and field mappings listed in the following table. In [!INCLUDE [prod_short](includes/prod_short.md)], you can review the table and field mappings on the **Integration Table Mappings** page.

| [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] | Synchronization Direction |
|---------------------------------------------|----------------------------------------------|---------------------------|
|ESG Concept|Concept|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|
|ESG Reporting Line|Assessment Requirement|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|
|ESG Reporting Name|Assessment|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|
|Posted ESG Report Line|Fact|[!INCLUDE[prod_short](includes/prod_short.md)] --> [!INCLUDE[prod_short](includes/cds_long_md.md)]|
|ESG Range Period|Range Period|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|
|ESG Requirement Concept|Requirement Concept ID|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|
|ESG Standard Requirement|Standard Requirement ID|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|
|ESG Standard|Standard ID|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|
|ESG Reporting Unit|Unit|[!INCLUDE[prod_short](includes/cds_long_md.md)] --> [!INCLUDE[prod_short](includes/prod_short.md)]|

### Set up an assessment in External ESG reporting

The next step is to set up assessments for your External ESG reporting. To learn more about how to set up an assessment in your External ESG reporting, go to [Create assessments](/industry/sustainability/external-reporting/assessments).

## Set up External ESG reporting in Business Central

The ESG report is automatically created in [!INCLUDE [prod_short](includes/prod_short.md)] from the assessment in your External ESG reporting. The next step is to connect the lines with the data sources in [!INCLUDE [prod_short](includes/prod_short.md)]. To do that, follow these steps.

1. In [!INCLUDE [prod_short](includes/prod_short.md)], [!INCLUDE [open-search-lowercase](includes/open-search-lowercase.md)], enter **ESG Reporting Aggregation**, and then choose the related link.
1. In the **Name** field, choose the assessment you created in Power Apps.
1. In the **Field Type** field, choose either **Table Field** or **Formula**, and then do one of the following:

   To specify a data source, choose **Table Field**, and then follow these steps:  

   1. For each line where you want to add an amount from [!INCLUDE [prod_short](includes/prod_short.md)], in the **Table No.** field, choose the table that contains the fields with the data you want to synchronize. When you choose a table, its fields are available in the **Field No.** field.
   1. In the **Field No.** field, choose the field that you want to synchronize.
   1. In the **Value Settings** field, specify whether you want to show values as a sum, or a total count.
   1. In the **Account Filter** field, choose the account to post to in your sustainability chart of accounts.

   To run a calculation on the values from the data source, choose **Formula**, and then enter the formula you want to use in the **Row Totaling** field. To learn more about formulas, go to [Working with row formulas](bi-row-definitions.md#working-with-row-formulas).

   Continue with the next step in this procedure.

1. In the **Reporting Unit of Measure** field, enter the unit of measure in which you want to calculate values in your ESG report.
1. In the **Calculate With**, **Show**, and **Show With** fields, define how you want to display values.
1. In the **Rounding** field, specify whether you want to round values to the nearest whole number. 
1. To verify that the report works, choose the **Preview** action, and then verify the values.

## Run the ESG compliance report

When your setup is ready, you can run the ESG compliance report.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **ESG Reporting Aggregation**, and then select the related link.
1. Choose the **Calculate and Post ESG Report**
1. A confirmation dialog displays. Verify that the template and batch are correct, and then choose **Yes**.

## Review your posted ESG compliance report

You can review your posted ESG compliance reports in [!INCLUDE [prod_short](includes/prod_short.md)] and in External ESG reporting.

To review your ESG report in [!INCLUDE [prod_short](includes/prod_short.md)], follow these steps:

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Posted ESG Reports**, and then select the related link.
1. Open the posted report you want to review.
1. The **Posted ESG Report** page shows the details about the posted report.

To review the assessment (ESG compliance report) in your External ESG reporting, follow these steps:

1. Open your External ESG reporting.
1. Find your assessment, and choose the **Requirements** tab.
1. To view details about a requirement, including its fact value, expand the requirement.

## Export your assessment from External ESG reporting

For example, if you want to share your ESG report, you can export it from External ESG reporting. To learn more about exports, go to [Export assessments](/industry/sustainability/external-reporting/exports).

1. Open your External ESG reporting.
1. Find your assessment, and choose the **Export** action.

## Related information

[Sustainability management overview](finance-manage-sustainability.md)  
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
