---
title: How to view ledger reconciliations
description: Learn how to view general ledger reconciliation with the customer ledger and vendor ledger in the French version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: ledger reconciliation, customer ledger, vendor ledger, French version
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
ai-usage: ai-assisted
---

# View ledger reconciliations

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes two reports that can help you reconcile general ledger entries with customer ledger entries and vendor ledger entries. The reports print a separate page for each customer or vendor that sums up amounts from general ledger transactions based on payments and posted invoices.  

> [!NOTE]
> As of release 28, the **GL/Cust. Ledger Reconciliation** and **GL/Vend. Ledger Reconciliation** reports moved from the base application to the **Payment Management FR** extension. If you don't see these reports, make sure the **Payment Management FR** extension is installed for your environment.

The following procedure applies to viewing reconciliation between the general ledger and the customer ledger, but the same steps apply to reconciliation with the vendor ledger.  

## View general ledger reconciliation with the customer ledger  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger**, and then choose the related link in **General Ledger**.  
1. Choose the **Reports** action, choose the **France** action, and then choose the **GL/Cust. Ledger Reconciliation** action.  
1. Set the appropriate filters on the **GL/Cust. Ledger Reconciliation** page.  

   > [!NOTE]  
   > You must specify a date filter.  

1. Choose the **Preview** button.  

You can now review the debit and credit amounts for each customer, and the document numbers that resulted in each general ledger transaction.  

## Related information

- [France local functionality](france-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
