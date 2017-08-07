---
    title: How to Register VAT on Purchase Orders | Microsoft Docs
    description: In Russia, organizations are required to keep a journal of received and issued VAT invoices. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] enables you to register VAT on purchase orders so that the information is tracked in the VAT invoices journal.
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
# How to: Register VAT on Purchase Orders
In Russia, organizations are required to keep a journal of received and issued VAT invoices. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] enables you to register VAT on purchase orders so that the information is tracked in the VAT invoices journal.  
  
### To register VAT on a purchase order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Order**, and then choose the related link. Select the relevant purchase order.  
  
2.  On the **Shipping** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Vendor Receipts No.**|Enter the identification number from the vendor receipt.|  
    |**Vendor Receipts Date**|Enter the date from the vendor receipt.|  
  
3.  On the **VAT** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Vendor VAT Invoice No.**|Enter the invoice number from the original VAT transaction.|  
    |**Vendor VAT Invoice Date**|Enter the invoice date from the original VAT transaction.|  
    |**Vendor VAT Invoice Rcvd Date**|Enter the date that the purchase was received.|  
  
 The VAT transaction is now registered and will be tracked in the VAT invoices journal after the purchase order is posted.  
  
## See Also  
 [About Setting Up VAT](about-setting-up-vat.md)   
 [How to: Set Up VAT Business Posting Groups](how-to-set-up-vat-business-posting-groups.md)   
 [How to: Assign VAT Business Posting Groups to Customer Accounts and Vendor Accounts](how-to-assign-vat-business-posting-groups-to-customer-accounts-and-vendor-accounts.md)   
 VAT Entry   
 [How to: Set Up VAT Ledgers](how-to-set-up-vat-ledgers.md)   
 [How to: Prepare VAT Entries for Posting](how-to-prepare-vat-entries-for-posting.md)