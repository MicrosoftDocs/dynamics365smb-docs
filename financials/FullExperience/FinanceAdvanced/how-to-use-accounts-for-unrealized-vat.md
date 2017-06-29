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
# How to: Use Accounts for Unrealized VAT
You can choose to have VAT amounts calculated and posted to a temporary general ledger account when an invoice is posted, and then posted to the correct general ledger account and included in VAT statements when the actual payment of the invoice is posted. Before you can do this, you must complete the VAT posting setup.  
  
### To use accounts for unrealized VAT  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  In the **General Ledger Setup** window, on the **General** FastTab, select the **Unrealized VAT** check box.  
  
3.  Close the window.  
  
4.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
5.  In the **VAT Posting Setup** window, to view the options, choose the **Unrealized VAT Type** field, and then select an option that determines how unrealized VAT will be handled.  
  
6.  In the **Sales VAT Unreal. Account** field, enter the general ledger account for unrealized sales VAT.  
  
7.  In the **Purch. VAT Unreal. Account** field, enter the general ledger account for unrealized purchase VAT.  
  
> [!IMPORTANT]  
>  The first \<Blank\> option is the default value of the field. This means that unrealized VAT is not used. You can select one of the other options only if the **Unrealized VAT** field in the **General Ledger Setup** window is selected.  
  
## See Also  
 [How to: Set Up Combinations of VAT Business Posting Groups and VAT Product Posting Groups](../Finance/how-to-set-up-combinations-of-vat-business-posting-groups-and-vat-product-posting-groups.md)