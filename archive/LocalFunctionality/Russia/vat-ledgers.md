---
    title: VAT Ledgers | Microsoft Docs
    description: The VAT ledger feature enables you to create and print the following forms:
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# VAT Ledgers
The VAT ledger feature enables you to create and print the following forms:  
  
-   VAT Purchase Ledger  
  
-   VAT Sales Ledger  
  
-   VAT Purchase Ledger Additional Sheet  
  
-   VAT Sales Ledger Additional Sheet  
  
## VAT Purchase Ledgers and VAT Sales Ledgers  
 Before you can create VAT ledgers, you must set up number series and vendor posting groups. You must also set up VAT posting groups to identify how VAT entries must be included in VAT ledgers. Also, for each VAT posting setup, you must specify if entries that use the setup must be included in VAT ledgers, and if the entries are VAT exempt. For more information, see [How to: Set Up VAT Ledgers](how-to-set-up-vat-ledgers.md).  
  
 You can create and store any number of VAT ledgers. For example, you can create the following:  
  
-   Sales ledgers for different groups of customers.  
  
-   Additional sales ledgers for amount differences and prepayments.  
  
-   Joint sales ledgers for the whole company.  
  
 To create a VAT ledger, first you must define a VAT ledger type, and then you must add lines to the VAT purchase ledger or VAT sales ledger by using the **Create VAT Purchase Ledger** and **Create VAT Sales Ledger** batch jobs. When you have added lines to the VAT ledger, you can print it.  
  
 For more information, see [How to: Create VAT Ledgers](how-to-create-vat-ledgers.md).  
  
## Marking a VAT Purchase Ledger  
 The VAT for purchase documents must be reflected in the purchase ledger. Return orders of the customers must be reflected in purchase books.  
  
 The following procedure shows how to mark a VAT purchase ledger.  
  
1.  In the **Sales Return Order** form or the **Sales Credit Memo** form, click the **VAT** tab.  
  
2.  Select the **Include in Purch. VAT Ledger** check box.  
  
 These marked documents will be reflected in the purchase book or in the sales book. Sales return orders are marked by default.  
  
## See Also  
 [How to: Set Up VAT Ledgers](how-to-set-up-vat-ledgers.md)   
 [How to: Create VAT Ledgers](how-to-create-vat-ledgers.md)   
 [How to: Create Additional Sheets](how-to-create-additional-sheets.md)   
 [Posting VAT on Sales](posting-vat-on-sales.md)   
 Custom Declarations   
 [Amount Difference](assetId:///ecc3830d-d498-44a3-bdb6-79e094d620e9)