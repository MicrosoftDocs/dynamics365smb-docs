---
title: Czech Local Functionality - General ledger entries application | Microsoft Docs
description: This section describes local functionality - General ledger entries application
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, finance, CZ, General ledger, Entries
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-pejano
---

# General Ledger Entries Application

Apart from the application of customer and vendor ledger entries, a new functionality for general ledge entry application has been introduced. Application of G/L entries is typically used to allow companies to work with temporary and transfer accounts in the general ledger. Temporary and transfer accounts are used as a temporary “storage” and contain amounts (ledger entries) pending further processing. The new application functionality enables the user to match general expenses to distributed expenses (transferred earlier from account general for all amounts) by using the new applying and unapplying functions, and for companies to see analytic subtotals by using the new **Open G/L Entries on Date** or **Inventory Account to Date** reports for a specific date.

The G/L entries structure has been redesigned by adding the new storage for application information of a G/L entry. The **Detailed G/L Entry** table contains all entries related to the original G/L entry and stores the application amount, while the **G/L Entry** table contains overalls of this amount in the **Applied Amount** FlowField.  

The **Apply Entries** and **Unapply Entries** functions on the **G/L Entries** page have been added to the user interface.

Partial application is allowed. The remaining amount for applying is shown on the G/L entry. Users can apply G/L entries before posting the general journal or the cash desk.

User can run batch application by using the **G/L Entry Applying** report .

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)  
