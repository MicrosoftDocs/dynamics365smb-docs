---
title: Handle external ESG compliance reporting
description: Learn how to set up and use ESG compliance reports.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: Sustainability, ESG, emission, GHG, certificate, green
ms.search.form: 
ms.date: 09/11/2025

ms.service: dynamics-365-business-central

---

# Handle external ESG compliance reporting

The European Union's (EU) Corporate Sustainability Reporting Directive (CSRD) specifies how, and when, companies report on sustainability matters. 

This article describes how to prepare your [!INCLUDE [prod_short](includes/prod_short.md)] so your business can meet CSRD requirements.

## Prerequisites

To use the features for ESG compliance reporting, you must have a valid license for Power Apps.

## Use Sustainability Manager

Sustainability Manager addresses external reporting challenges by providing templates based on ESG standards or frameworks. The tool helps you create, complete, and manage approval of comprehensive reports across both quantitative and qualitative metrics.

To learn more about Sustainability Manager, go to [Overview of external reporting in Sustainability Manager](/industry/sustainability/external-reporting/overview).

Sustainability Manager includes standard and framework reporting templates for the following:

- Standard and framework templates for CSRD.
- Australian Sustainability Reporting Standards (ASRS).
- Business Responsibility and Sustainability Reporting (BRSR) 1 and 2.
- Global Reporting Initiative (GRI)
- International Financial Reporting Standards (IFRS) 1 and 2.
- Sustainability Accounting Standards Board (SASB).

## Get started

The following sections describe each step in the process of setting up ESG compliance reporting.

### Integrate with Dataverse and enable data synchronization

Connect your [!INCLUDE [prod_short](includes/prod_short.md)] to [!INCLUDE [cds_long_md](includes/cds_long_md.md)], and enable data synchronization. To learn more, go to [Integrate with Microsoft Dataverse via data sync](admin-common-data-service.md).

For ESG reporting, the key part of the setup in the integration with [!INCLUDE [cds_long_md](includes/cds_long_md.md)] are the integration table and field mappings. The following table lists the integration table and field mappings related to ESG reporting.

| [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] | Synchronization Direction | Default Filter |
|---------------------------------------------|----------------------------------------------|---------------------------|----------------|
|ESG Concept|Concept|Bi-directional||
|ESG Reporting Line|Assessment Requirement|Bi-directional||
|ESG Reporting Name|Assessment|Bi-directional||
|Posted ESG Report Line|Fact|Bi-directional||
|ESG Range Period|Range Period|Bi-directional||
|ESG Requirement Concept|Requirement Concept ID|Bi-directional||
|ESG Standard Requirement|Standard Requirement ID|Bi-directional||
|ESG Standard|Standard ID|Bi-directional||
|ESG Reporting Unit|Unit|Bi-directional||

<!--100% guessed that the direction is bi-directional, and didn't know what the filters are-->

### Set up an assessment in Power Apps

The next step is to set up Power Apps, and connect it to [!INCLUDE [prod_short](includes/prod_short.md)].

1. Open your Power Apps.
1. Choose **Assessments**, and then choose **New**.
1. On the **New Assessment** page, in the **Name** field, give your assessment a name. Typically, names reflect the standard the assessment uses.
1. In the **Standard** field, choose the reporting template for the standard you want to report.
1. In the **Period** field, select the year to collect data for.
1. Choose **Save**.
1. Choose the **Requirements** tab.
1. Fill in a line for each requirement. <!--Not sure what the requirements represent.-->
1. In [!INCLUDE [prod_short](includes/prod_short.md)], [!INCLUDE [open-search-lowercase](includes/open-search-lowercase.md)], enter **ESG Reporting Aggregation**, and then choose the related link.
1. In the **Name** field, choose the assessment you created in Power Apps.<!--I assume they need to wait until data synchronizes so that their assessment is available? Does the ESG Reporting Aggregation page fill in automatically when it does?-->
1. For each line, in the **Table No.** field, choose the table that contains the fields with the data you want to synchronize. When you choose a table, its fields are available in the **Field No.** field.
1. In the **Field No.** field, choose the field that you want to synchronize.
1. In the **Value Settings** field, specify whether you want to show values as a sum, or a total count. <!--The tooltip doesn't provide much value :-)-->
1. In the **Account Filter** field, choose the account to post to in your sustainability chart of accounts.
1. In the **Calculate With**, **Show**, and **Show With** fields, define how you want to display values.
1. In the **Rounding** field, specify whether you want to round values to the nearest whole number. <!--guessing that's what this does-->
1. To verify that the report works, choose the **Preview** action, and then verify the values.

## Run the ESG compliance report

When your setup is ready, you can run the ESG compliance report.

