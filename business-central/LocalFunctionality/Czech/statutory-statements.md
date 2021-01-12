---
title: Czech Local Functionality - Statutory Statements
description: This feature provides the reports - Balance Sheet, Income Statement.
author: v-makune

ms-service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 12/01/2020
ms.reviewer: v-pejano
ms.author: v-pejano
---


# Statutory Statements

Companies must create financial statements according to the Accounting Law 563/1991. They must create the balance sheet and the profit and loss statement.
This feature provides the following reports:

- **Balance Sheet**
- **Income Statement**

These reports use the Account Schedule feature with the statement structure defined.

The **Acc. Schedule Name** table contains this new field in the Czech version:
- **Acc. Schedule Type** – Balance Sheet or Income Statement option

The **Acc. Schedule Line** table contains these new fields in the Czech version:
- **Row Correction** – links to another line for balance sheet setup
- **Assets/Liabilities Type** – Assets or Liabilities for Balance Sheet setup
- **Calc** – Always, Never, When positive, When Negative options

The balance sheet and the profit and loss statements are often prepared in Excel file templates with the necessary design for statement printout. Users want to map defined account schedules to prepared Excel templates.

For the reasons above, this feature provides the new setup of Excel templates and statement file mapping. Based on this setup, users can export account schedule data to Excel files.

## See Also

[Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Statutory company information](statutory-company-information.md)  
[Finance](../../finance.md)  
