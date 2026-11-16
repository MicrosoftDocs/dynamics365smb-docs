---
title: Fixed Asset List and Setup (report)
description: Review fixed asset identification, classification, dimensions, and depreciation setup for a selected depreciation book, excluding inactive assets.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5601_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 10/23/2024
ai-usage: ai-assisted
---

# Fixed Asset List (report)

The **Fixed Asset List** report lists fixed assets and their setup information for a given depreciation book.

The list includes asset information such as fixed asset class, subclass, location code, global dimensions, and FA posting group. It also shows information about depreciation, such as the method, start/end date, and years and months.

The report gets the information from the fixed asset cards and fixed asset depreciation books.

Inactive assets are excluded. The report shows the current setup, not an inventory or valuation as of a historical date. Select **New Page per Asset** to print each asset separately.

## Use cases

[!INCLUDE[report-5601-scenario](../includes/report-5601-scenario-include.md)]

<!-- 

Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with fixed asset management or finance for fixed assets.

Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    
* use case 3    

Do not capitalize the persona names. 

Do not start lines with "Use the data to"

## Report name
Fixed Asset List

## Report description
The Fixed Asset List report provides a comprehensive listing of all fixed assets owned by an organization at a specific point in time. This report is crucial for asset management, financial reporting, and compliance purposes.

### What the report does
The *Fixed Asset List* report shows a list of fixed assets and their setup information for a given depreciation book.
The list includes asset information such as fixed assets class, subclass, and location code, customer group and FA posting group.  
You can also see depreciation information such as depreciation method, depreciation start/end date, and depreciation years and months.

### Use cases
Get a comprehensive listing of all fixed assets owned by an organization at a specific point in time.


Please include your data sources and URLs at the end of the answer.

-->

Accountants use the report to:

* Review depreciation setup to check that it follows accounting standards.
* Identify and correct discrepancies between the fixed asset list and other financial records.

Controllers use the report to:

* Share an overview of the organization's active fixed assets with stakeholders such as investors or auditors.

Compliance officers use the report to:

* Verify that the organization's fixed asset information is accurate and complete, and follows relevant regulations.
* Prepare reports and other documentation for audits and regulatory inspections for fixed assets.

Fixed asset managers use the report to:

* Create a list of active fixed assets and their current setup.
* Verify the accuracy of fixed asset records by comparing them with the information in the report.

Facilities managers use the report to:

* Track the location and setup of active fixed assets in an organization.
* Plan for future capital expenditures related to fixed assets.

Use a book value report to review posted asset values.

## Try the report

Try the report here: [Fixed Asset List](https://businesscentral.dynamics.com?report=5601)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Fixed assets report overview](../fa-reports.md)    
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]