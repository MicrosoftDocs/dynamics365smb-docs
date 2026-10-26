---
title: Set Up Payroll Data Import in Norway [NO]
description: Set up payroll data imports from Huldt & Lillevik in Business Central for Norway, including the import format, global dimensions, and file layout.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: payroll data definitions, data exchange definitions, payroll transactions, import payment file, Norwegian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up payroll data import in Norway

If your business uses the Huldt & Lillevik Lønn - Visma payroll service provider in Norway, the **Payroll Data Import Definition (NO)** extension helps you import payroll transactions into a general journal. The extension provides the `HULDT-LILLEVIK` data exchange definition for files from that provider. Learn more in [Set up data exchange definitions](../../across-how-to-set-up-data-exchange-definitions.md).

## Getting started

The first step is to map the types of payroll transactions to the general ledger accounts that you want to post them to in [!INCLUDE[prod_short](../../includes/prod_short.md)]. For example, you might want to post retirement plan contributions to an account named Pension, and the taxes paid on the contributions to an account named Pension Tax. This happens outside of [!INCLUDE[prod_short](../../includes/prod_short.md)], for example, you might use an Excel worksheet to visualize the mapping. Work with the payroll service provider to ensure that the file they export contains the mapping. Typically, you can find information about how to configure export files on the provider's website.  

After you install the extension, open **General Ledger Setup** and select `HULDT-LILLEVIK` in **Payroll Trans. Import Format**. Opening the page creates the definition if it's missing, but doesn't select it for you.

On the same page, configure the following options:

| Field | Description |
|---|---|
| **Import Dimension Codes** | Select to import the file's department and project codes as global dimension 1 and global dimension 2. If you don't select this option, those dimension values aren't imported. |
| **Ignore Zeros-Only Values** | Select to treat dimension values that contain only zeros as blank. This option applies when **Import Dimension Codes** is selected. |

The supplied definition uses a semicolon-separated file with 17 columns. It reads posting dates in `ddmmyyyy` format and divides the amount and quantity values by 100. Make sure the payroll export matches this format before you import it.

## Import a payroll file

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Journals**, and then choose the related link.
1. Choose the journal to use, and then use the **Import Payroll File** action to import the data file from the payroll service provider.  

## Related information

[Norway Local Functionality](norway-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
