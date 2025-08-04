---
title: Fixed Asset G/L Analysis (report)
description: Help reconciling fixed assets transactions to the general ledger and specifically for validating the disposal entries.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_5610_Primary
ms.date: 10/23/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/23/2024
ai.usage: ai-assisted
---

# Fixed Asset G/L Analysis (report)

The **Fixed Asset G/L Analysis** report shows an analysis of your fixed assets with various types of data for individual assets and groups of assets.

The report assumes that you know which G/L accounts are specified in the posting setup.

The amounts in this report are calculated from fixed asset ledger entries based on the posting date. If you have set up integration to general ledger for the current depreciation book, you can find the same amounts in the corresponding general ledger entries. The **Fixed Asset - Analysis report**, which is similar, uses fixed asset posting dates.

## Use cases

[!INCLUDE[report-5608-scenario](../includes/report-5610-scenario-include.md)]

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
Fixed Asset G/L Analysis

## Report description
The Fixed Assets G/L Analysis report is essential for financial management and reporting, offering detailed insights into the accounting treatment and reconciliation of subledger with the general ledger mainly validating the disposal entries. Structurally it is similar to FA Analysis report but this one is focused on GL reconciliation purpose. 

### What the report does
The *Fixed Asset G/L Analysis* report shows an analysis of your fixed assets with various types of data for individual assets and/or groups of assets. 
On the Fixed Assets FastTab, you can set filters if you want the report to include only certain fixed assets. 
On the Options FastTab, tailor the report to meet your specific needs. 
The report is similar to the **Fixed Asset Analysis** report, but specifically for reconciling to the general ledger (G/L) and specifically for validating the disposal entries. 
The report assumes that you know the general ledger (G/L) accounts that are specified in the posting setup.
If G/L integration is activated for a depreciation book, this report shows amounts posted to the general ledger (G/L) coming from the FA application area. The report is based on the posting date in the fixed assets (FA) ledger, whereas all other reports use the FA posting date.

### Use cases
Help reconciling fixed assets transactions to the general ledger and specifically for validating the disposal entries.


Please include your data sources and URLs

-->

Finance managers use the report to:

* Verify that all fixed asset transactions are accurate in the general ledger.
* Monitor the financial performance of the organization based on the accounting for fixed assets.
* Ensure that the accounting for fixed assets aligns with the organization's financial goals.

Accountants use the report to:

* Reconcile fixed asset transactions with the general ledger and identify discrepancies.
* Verify that the disposal entries are accurate in financial statements.
* Ensure that the accounting for fixed assets complies with accounting standards and regulations.

## Try the report

Try the report here: [Fixed Asset G/L Analysis](https://businesscentral.dynamics.com?report=5610)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]