---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
In Russia, organizations are required to keep a journal of received and issued VAT invoices. FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> enables you to register VAT on purchase orders so that the information is tracked in the VAT invoices journal.  
  
### To register VAT on a purchase order  
  
1.  In the **Search** box, enter **Purchase Order**, and then choose the related link. Select the relevant purchase order.  
  
2.  On the **Shipping** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Vendor Receipts No.**|Enter the identification number from the vendor receipt.|  
    |**Vendor Receipts Date**|Enter the date from the vendor receipt.|  
  
3.  On the **VAT** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Vendor VAT Invoice No.**|Enter the invoice number from the original VAT transaction.|  
    |**Vendor VAT Invoice Date**|Enter the invoice date from the original VAT transaction.|  
    |**Vendor VAT Invoice Rcvd Date**|Enter the date that the purchase was received.|  
  
 The VAT transaction is now registered and will be tracked in the VAT invoices journal after the purchase order is posted.  
  
## See Also  
 [About Setting Up VAT](../../Finance/about-setting-up-vat.md)   
 [How to: Set Up VAT Business Posting Groups](../../Finance/how-to-set-up-vat-business-posting-groups.md)   
 [How to: Assign VAT Business Posting Groups to Customer Accounts and Vendor Accounts](../../Finance/how-to-assign-vat-business-posting-groups-to-customer-accounts-and-vendor-accounts.md)   
 VAT Entry   
 [How to: Set Up VAT Ledgers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-vat-ledgers.md)   
 [How to: Prepare VAT Entries for Posting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-prepare-vat-entries-for-posting.md)