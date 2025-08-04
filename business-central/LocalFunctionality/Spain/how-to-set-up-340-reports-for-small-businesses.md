---
title: Set up 340 reports for small businesses [ES]
description: Learn how to set up 340 reports for small businesses in Spain on cash basis, that is, Cash Accounting Criteria (CAC)
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 340 reports, small business, unrealized VAT, cash basis, cash accounting criteria, CAC, Spanish version
ms.search.form: 10737, 10738, 10744
ms.date: 05/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up 340 reports for small businesses in the Spanish version

Use the following procedure to set up your business to report on a cash basis, that is, Cash Accounting Criteria (CAC). If you haven't already done so, you can set up posting groups for cash-based VAT accounting for purchases and sales.  

When you file a report 340, any transaction lines that are associated with unrealized VAT are assumed to take place under cash accounting.  

After VAT posting is set up to handle unrealized VAT, any printed sales order, purchase order, and so forth, is modified to have the following label in bold font added to the report just before the section reporting the document lines: **Régimen especial del criterio de caja**.  

## Set up reporting under CAC  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. On the **General** FastTab, select the **Unrealized VAT** checkbox on the **General Ledger Setup** page. Choose the **OK** button.  
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.  
1. On the **VAT Posting Setup** page, select a group to modify or create a posting group that has general ledger accounts to treat the VAT amounts for the various unrealized VAT accounts in your VAT Posting Setup, and then choose the **Edit** action.  
1. On the **General** FastTab, set the **Unrealized VAT Type** to **Percentage**.  
1. On the **Sales** and **Purchase** FastTabs, specify general ledger accounts for the various **VAT Unreal. Account** fields.  

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
