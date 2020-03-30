---
title: VAT Control Report | Microsoft Docs
description: Czech companies registered for VAT in the Czech Republic (with assigned CZ VAT ID number) have the obligation to submit the VAT Control Report.
author: v-pejano

ms-service: dynamics365-business-central
ms.topic: article
ms.search.keywords: CZ, Czech, local, Finance, VAT, Control Report
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-pejano
---

# VAT Control Report

The [!INCLUDE[d365fin](../../includes/d365fin_md.md)] functionality has been extended with the VAT Control Report feature. The basic page is the **VAT Control Report Card** page. VAT items are loaded by the VAT date or posting date (according to the general ledger setup) into the page for the selected period. The basic setup, i.e. distribution of combinations of VAT posting groups into the individual sections of control report, is determined by the VAT statement.

To process the control report, you must set up the VAT control report sections, tariff numbers, VAT statement, stat. reporting setup, and extend the VAT posting setup. The functionality contains:

* **VAT Control Report Card** page - allows you to select report period.

* **Control Report Lines Suggestion** function - loads control report lines of a selected period.

* Control performance - **VAT Control Report - Test** report - prints an overview according to individual sections.

* Control report export - **Export** function exports control report to the file.

* Closing lines - **Close lines** function fills the **Closed by Document No.** field on control report lines.

## See also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
