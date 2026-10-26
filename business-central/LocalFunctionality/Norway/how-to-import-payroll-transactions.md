---
title: Import Payroll Transactions in the Norwegian Version [NO]
description: Learn how to import payroll transactions into a general journal in Business Central using the Norwegian payroll solution, Huldt & Lillevik Lønn - Visma.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: import payroll transactions, Visma, Huldt & Lillevik Lønn, payroll solution, Norwegian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import payroll transactions in the Norwegian version

You can import payroll transactions into a general journal from the leading Norwegian payroll solution, Huldt & Lillevik Lønn - Visma. You can then use the general journal to post the imported payroll transactions to general ledger accounts or bank accounts. To import payroll transactions, you must first set up payroll integration.  

> [!NOTE]  
> To import payroll transactions, your [!INCLUDE[prod_short](../../includes/prod_short.md)] must include the **Payroll Data Import Definition (NO)** extension. If you aren't sure if you have this extension, talk to your administrator.

On **General Ledger Setup**, select `HULDT-LILLEVIK` in **Payroll Trans. Import Format** before you import the file. To include the file's department and project codes as global dimensions, select **Import Dimension Codes**. Learn more in [Payroll data definitions](ui-extensions-payroll-data-definitions-no.md#getting-started).

## Import payroll transactions  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Journals**, and then choose the related link.  
1. Choose the journal to use, and then use the **Import Payroll File** action to import the data file from the payroll service provider.  
1. Choose the **OK** button.

Review the imported journal lines before you post them.

## Related information

- [Set up payroll data import in Norway](ui-extensions-payroll-data-definitions-no.md)
- [Norway Local Functionality](norway-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
