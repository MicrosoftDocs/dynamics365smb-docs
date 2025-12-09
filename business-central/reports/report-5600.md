---
title: Fixed Asset Analysis (report)
description: This report helps with tasks such as reconciling fixed asset values with your general ledger, or reviewing net values and write down values. You can also see information only for sold fixed assets.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5600_Primary
ms.date: 10/23/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/23/2024
ai.usage: ai-assisted
---

# Fixed Asset Analysis (report)

The **Fixed Asset Analysis** report provides a comprehensive examination of an organization's fixed assets, such as property, plant, and equipment, for different purposes.

You can specify two date columns and three data columns to display in the report.

For example, to generate a report for reconciling with the general ledger, add columns for:

* Acquisition cost at an ending date.
* Depreciation at an ending date.
* Book value at an ending date.

A check report could have acquisitions/net change, write-down/net change, and appreciation/net change, so you can check every change to a fixed asset.

If you select the **Budget Report** field and specify an ending date in the future, the report calculates the future depreciation and gives estimates for future depreciation and book values, if you selected those fields as report columns.

## Use cases

[!INCLUDE[report-5600-scenario](../includes/report-5600-scenario-include.md)]

<!-- 

Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with fixed asset management or finance for fixed assets.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

Do not start lines with "Use the data to"

## Report name
Fixed Asset Analysis

## Report description
Fixed Asset Analysis Report is a flexible reporting option that provides a comprehensive examination of an organization's fixed assets, such as property, plant, and equipment (PP&E), for different purposes. If the purpose is to reconcile asset values with GL then fields like acquisition, depreciation can be selected. If the purpose is about reviewing net value along with write down value, users can use this report accordingly by choosing the relevant amount fields and amount fields for multiple periods.

### What the report does
The *Fixed Asset Analysis* report is a flexible reporting option that provides a comprehensive examination of an organization's fixed assets, such as property, plant, and equipment (PP&E), for different purposes. 
You can specify two date columns and three data columns to see in the report. 
For example, to generate a report to use for reconciling with the general ledger, add columns for acquisition cost at ending date, depreciation at ending date, and book value at ending date. A check report could have acquisitions/net change, write-down/net change, and Appreciation/net change, so every change to fixed asset can be checked if necessary. 
If you select the **Budget Report** field and specify an ending date in the future, the report will calculate the future depreciation and can give estimates for future depreciation and book values, if you selected those fields as report columns.

### Use cases
Analyze your fixed assets, use this report to aid you in tasks such as reconcile asset values with your general ledger (G/L) or reviewing net value along with write down value.

Please include your data sources and URLs

-->

Fixed asset managers use the report to:

* Monitor fixed asset values and review net value along with write down value by selecting the relevant amount fields and amount fields for multiple periods.
* Generate a check report with acquisitions/net change, write-down/net change, and appreciation/net change to verify every change to fixed assets.

Accountants use the report to:

* Reconcile asset values with the general ledger by selecting fields like acquisition and depreciation at an ending date, and book value at an ending date.
* Generate a budget report by selecting the **Budget Report** field and specifying an ending date in the future to calculate future depreciation and book values.

Controllers use the report to:

* Analyze fixed asset values for an organization and make strategic decisions.
* Review the depreciation expenses for all fixed assets for multiple periods.

## Try the report

Try the report here: [Fixed Asset Analysis](https://businesscentral.dynamics.com?report=5600)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze your fixed assets. To learn more, go to:

- [Fixed Asset Analysis Excel](report-4412.md)
- [Using data analysis to analyze fixed assets data](../ad-hoc-analysis-fa.md)  

## Related information

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]