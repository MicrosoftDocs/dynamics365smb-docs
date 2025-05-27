---
title: Map IRS numbers to chart of accounts [IS]
description: This article explains how to map predefined Internal Revenue Service (IRS) account codes to general ledger accounts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: prededined IRS, general ledger accounts, Internal Revenue Service
ms.date: 02/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Map IRS numbers to chart of accounts in the Icelandic version

Companies in Iceland are required to send the tax authority a data file in a predefined format. Before doing that, you must map predefined Internal Revenue Service (IRS) account codes to general ledger accounts.  

## Create an Internal Revenue Service number  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Number**, and then choose the related link.  
1. Choose the **New** action.  
1. On the new line, enter a number in the **IRS number** field, and provide a name in the **Name** field.  
1. Select the **Reverse Prefix** check box if you want the negative operator to be reversed on the balance of the general ledger account that the IRS number is mapped to.  
1. Choose the **OK** button.  

## Map an IRS number to a general ledger account  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
1. Select a general ledger account that has an **Account Type** of **Posting**.  
1. In the **IRS Number** field, select an IRS number from the list.  

## Related information

 [Special Data Output and Reports for the Tax Authority](special-data-output-and-reports-for-the-tax-authority.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
