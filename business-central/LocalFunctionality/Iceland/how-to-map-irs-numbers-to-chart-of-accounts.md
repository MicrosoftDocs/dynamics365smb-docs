---
title: Map IRS Numbers to the Chart of Accounts in Iceland
description: Learn how to create Icelandic IRS numbers, assign them to posting accounts, and review the mappings with IRS reports in Dynamics 365 Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: predefined IRS, general ledger accounts, Internal Revenue Service
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Map IRS numbers to chart of accounts in the Icelandic version

Companies in Iceland are required to send the tax authority a data file in a predefined format. Before doing that, you must map predefined Internal Revenue Service (IRS) account codes to general ledger accounts.  

## Create an Internal Revenue Service number  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **IRS Number**, and then choose the related link.
1. Choose the **New** action.  
1. On the new line, enter the tax authority's code in **IRS Number**, and provide a name in **Name**.
1. Use **Reverse Prefix** to indicate whether the IRS number requires a reversed balance sign for reporting.
1. Choose the **OK** button.  

## Map an IRS number to a general ledger account  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Chart of Accounts**, and then choose the related link.
1. Select a general ledger account that has an **Account Type** of **Posting**.  
1. In the **IRS Number** field, select an IRS number from the list.  

Use **IRS Details** or **Trial Balance - IRS Number** to review the mappings and balances for the reporting period.

## Related information

 [Special Data Output and Reports for the Tax Authority](special-data-output-and-reports-for-the-tax-authority.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
