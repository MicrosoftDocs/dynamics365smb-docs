---
title: Czech local functionality - Setup VAT date
description: Learn how to set up and use the VAT Date feature in the Czech version of Business Central, including configuration steps and VAT reporting options.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: install-set-up-deploy
ms.search.keywords: Czech, Finance, VAT, Localization, CZ
ms.date: 06/04/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# VAT date in the Czech version

The VAT date is important for tax documents according to §28 of VAT Law 235/2004. The VAT date can be different from the posting date or the document date. The VAT date is an important field for the VAT reporting.  

This feature focuses on improving the following aspects:

## Setup of the VAT Date feature

- Enabling VAT date usage in the system generally.
- Select the system's default value for the VAT date in different areas (Posting Date or Document Date).
- Periods for reporting VAT and company accounting periods are often different. To allow users to seamlessly report and post VAT according to VAT periods, and to issue internal and other statutory reporting based on accounting periods, this VAT Date feature introduces VAT periods.
- Allow VAT Posting From/To – enter a date range in from/to fields to prevent mistakes of posting to closed accounting or VAT periods.

## Posting sales, purchase, and service transactions with VAT date

To post transactions using a VAT date, the user must fill in the **VAT Date** field on the document headers and journal lines throughout the application.
After the posting of the VAT date, it becomes a part of the posted documents and G/L entries and VAT entries.

## Calculating and posting VAT settlement

The system filters VAT entries by the **VAT Date** field (instead of **Posting Date**) by selecting the VAT period and preparing a report showing which entries are transferred to the Settlement account. Printouts also contain VAT date information.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)    
- [VAT Control Report](vat-control-report.md)  
- [VAT statement](vat-statement.md)  
- [Finance](../../finance.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
