---
title: Czech Local Functionality - Statutory Statements [CZ]
description: This feature provides the reports - Balance Sheet, Income Statement.
author: v-makune

ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 08/26/2022
ms.reviewer: bholtorf
ms.author: v-pejano
---

# Statutory Statements in the Czech Version

Companies must create financial statements according to Accounting Law 563/1991. They must create the balance sheet and the profit and loss statement. The **Statutory Statements** feature provides the following reports:

- **Balance Sheet**
- **Income Statement**

These reports use the financial reports feature with the statement structure defined.

The **Acc. Schedule Name** table contains this new field in the Czech version:

- **Acc. Schedule Type** – provides the balance sheet or income statement option

The **Acc. Schedule Line** table contains these new fields in the Czech version:

- **Row Correction** – links to another line for balance sheet setup
- **Assets/Liabilities Type** – shows assets or liabilities for balance sheet setup
- **Calc** – provides the always, never, when positive, when negative options

The balance sheet and the profit and loss statements are often prepared in Microsoft Excel file templates with the required design layout for the statement report. Both documents can be customized using Excel workbooks (.xlsx files). Similarly, you can export financial report data to Excel files. Learn more about Excel report templates at [Working with Excel Layouts](../../ui-excel-report-layouts.md).

## Related information

[Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Statutory Company Information](statutory-company-information.md)  
[Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
