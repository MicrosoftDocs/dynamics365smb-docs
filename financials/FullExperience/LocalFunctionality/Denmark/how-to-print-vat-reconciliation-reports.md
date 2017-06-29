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
# How to: Print VAT Reconciliation Reports
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you can use the **VAT Reconciliation** report to view a list of general ledger accounts with their base amounts and VAT amounts. These amounts are grouped by VAT type to help with VAT settlement reconciliation.  
  
### To print a VAT reconciliation report  
  
1.  In the **Search** box, enter **VAT Reconciliation**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Show Details**|Select to print all transaction amounts in the report.<br /><br /> If you do not select this field, a single cumulative line is printed for each general ledger account.|  
    |**Show Transactions without VAT**|Select to print a line for each general ledger account that transactions are posted to. You can use this option for both single accounts and multiple accounts.<br /><br /> The default is **No**. The report includes only those transactions that include VAT entries. If you select this field, the report includes all transactions.|  
  
3.  On the **G\/L Entry** FastTab, select the appropriate filters.  
  
4.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Denmark Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/denmark-local-functionality.md)   
 Reconcile Cust and Vend Accs   
 VAT Reconciliation