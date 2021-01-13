---
title: Czech Local Functionality - Setup VAT date
description: This section describes Czech local functionality - VAT Date and Setup of the VAT Date Feature.
author: v-pejano

ms-service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: Czech, Finance, VAT, Localization, CZ
ms.date: 12/01/2020
ms.reviewer: v-pejano
ms.author: v-pejano
---


# VAT Date

The VAT date is important for tax documents according to §28 of VAT Law 235/2004. The VAT date can be different from the posting date or the document date. The VAT date is an important field for the VAT reporting.  

This feature focuses on improving the following:

## Setup of the VAT Date Feature

- Enabling VAT date usage in the system generally.
- Select the way the system will default the VAT date’s value in different areas (Posting Date or Document Date).
- Periods for reporting VAT and company accounting periods are often different. To allow users to seamlessly report and post VAT according to VAT periods, and to issue internal and other statutory reporting based on accounting periods, this VAT Date feature introduces VAT periods.
- Allow VAT Posting From/To – enter a date range in from/to fields to prevent mistakes of posting to closed accounting or VAT periods.

## Posting Sales, Purchase, and Service Transactions with VAT Date

To post transactions using a VAT date, the user must fill in the **VAT Date** field on the document headers and journal lines throughout the application.
After the posting of the VAT date, it becomes a part of the posted documents and G/L entries and VAT entries.

## Calculating and Posting VAT Settlement

The system filters VAT entries by the **VAT Date** field (instead of **Posting Date**) by selecting the VAT period and preparing a report showing which entries will be transferred to the Settlement account. Printouts also contains VAT date information.

## See Also

[Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
[VAT control report](how-to-create-vat-control-report.md)  
[VAT statement](vat-statement.md)
[Finance](../../finance.md)
[Czech Local Functionality](czech-local-functionality.md)