---
title: Fixed Asset Register (report)
description: Get a detailed and organized overview of all your fixed asset transactions.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_5603_Primary
ms.date: 10/23/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/23/2024
ai.usage: ai-assisted
---

# Fixed Asset Register (report)

The **Fixed Asset Register** report shows posted fixed asset ledger entries sorted by register numbers.

You can explore information about all transactions posted for fixed assets, such as:

* FA posting date
* Document type and number
* Depreciation book code
* Fixed asset number and description
* FA posting category and type
* Amount, posting date, and entry number

On the request page, you can set a filter for the relevant fixed asset. If you don't set filters, the report shows the register for all fixed assets.

You can set up the report to become part of the posting process; that is, it can print when you post. To print the register when you post a journal, select the **Post and Print** action on the journal. You can use the report to document posted entries or for auditing.

## About the fixed assets register

[!INCLUDE[prod_short](../includes/prod_short.md)] automatically assigns consecutive entry numbers to all entries that you post to depreciation books. In the FA registers, the entries are sorted by the entry number order, regardless of the FA numbers or depreciation book numbers.

[!INCLUDE [prod_short](../includes/prod_short.md)] creates a register each time you post, either directly from a fixed asset journal or indirectly from purchase invoices or sales invoices. The individual registers are also numbered (one is the first number).

## Use cases

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
Fixed Asset Register

## Report description
The Fixed Asset Register report is a comprehensive and structured document that serves as the central repository of all fixed asset transactions done by an organization.

### What the report does
The *Fixed Asset Register* report shows posted fixed asset ledger entries that are sorted and divided by register number. 
You can see all the transactions posted for fixed assets with information such as FA posting date, document type and number, depreciation book code, fixed asset number and description, FA posting category and type, posting date, amount, and entry number. On the request page, you can set a filter for the relevant fixed asset. If you do not set any filters, the report shows the register for all fixed assets.

### Use cases
It is used to provide a detailed and organized overview of fixed asset transactions, making it easier to track and manage fixed assets.
Use the report to provide a detailed and organized overview of fixed asset transactions, making it easier to track and manage fixed assets.

## About the Fixed Assets register
Business Central automatically assigns consecutive entry numbers to all entries that you post to depreciation books. In the FA registers, the entries are sorted in entry number order regardless of FA numbers or depreciation book numbers.
A register is created automatically with each posting, either directly from a fixed asset journal or indirectly from purchase invoices or sales invoices. The individual registers are also numbered (one is the first number).

Please include your data sources and URLs

-->

[!INCLUDE[report-5603-scenario](../includes/report-5603-scenario-include.md)] Use the report to get a detailed and organized overview of fixed asset transactions, so it's easier to track and manage fixed assets.

Controllers use the report to:

* Analyze fixed asset transactions for an organization and make strategic decisions.
* Share a comprehensive overview of an organization's fixed asset transactions with stakeholders, such as investors or auditors.

Accountants use the report to:

* Reconcile fixed asset transactions with the general ledger and ensure that they're accurate.
* Identify and correct errors or discrepancies in fixed asset transactions.
* Track the value of fixed assets over time by analyzing the depreciation information in the report.

Auditors use the report to:

* Verify the existence of fixed assets listed on the report by physically inspecting them.
* Review fixed asset transactions to ensure that they're accurate and comply with accounting standards.
* Prepare reports and other documentation for audits and regulatory inspections.

## Try the report

Try the report here: [Fixed Asset Register](https://businesscentral.dynamics.com?report=5603)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]