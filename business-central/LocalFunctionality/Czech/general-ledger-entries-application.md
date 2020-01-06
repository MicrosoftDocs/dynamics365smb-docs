---
title: Czech Local Functionality - General ledger entries application | Microsoft Docs
description: This section describes local functionality - General ledger entries application
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, finance, CZ, General ledger, Entries
ms.date: 12/30/2019
ms.reviewer: v-pejano
ms.author: v-pejano
---

# General Ledger Entries Application

Apart from application of Customer and Vendor Ledger Entries, a new functionality of General Ledger Entries Application has been introduced. Application of General Ledger Entries is typically used to allow companies to work with temporary and transfer accounts in the General Ledger. Temporary and transfer accounts are used as a temporary “storage” and contain amounts (Ledger Entries) pending further “processing”. The new application functionality enables the user to match general expenses to distributed expenses (transferred earlier from account general for all amounts) by using the new applying and unapplying functions, and to companies to see analytic subtotals by using the new Open G/L Entries on Date or Inventory Account to the date reports for a specific date.

The General Ledger Entries structure has been redesigned by adding the new storage for application information of a G/L Entry. The Detailed G/L Entry table contains all entries related to the original G/L Entry and stores the application amount, while the G/L Entry table contains overalls of this amount in the Applied Amount flowfield.  

**Apply Entries** and **Unapply Entries** functions on G/L Entries page have been added to the user interface. Partial applying is allowed. Remaining amount for applying is shown on G/L Entry.
User can apply G/L Entries before posting in General Journal or Cash Desk.
User can run batch applying using report **G/L Entry Applying**.

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)  
