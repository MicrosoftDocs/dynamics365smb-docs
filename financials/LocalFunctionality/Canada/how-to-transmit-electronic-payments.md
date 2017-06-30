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
# How to: Transmit Electronic Payments
After you have exported payment journal entries to a file using the Export Electronic Payments report, you can use the Void-Transmit Elec. Payments process to transmit the electronic payments file to your bank for processing.  
  
### To transmit payments  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  On the **Navigate** FastTab, choose **Electronic Payments**, and then choose **Transmit** or **Void**.  
  
3.  In the **Void\/Transmit Elec. Payments** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_10084\_N\_2\_1 Bank Account No. $\)**|Select the bank account for the electronic payment operation.|  
    |**\($ B\_10084\_N\_2\_3 E-Pay Operation $\)**|Specifies if you want to transmit or void the electronic payment file. The **Transmit** option produces an electronic payment file to be transmitted to your bank for processing. The **Void** option voids the exported file. Confirm that the correct selection has been made before you process the electronic payment file.|  
  
4.  To transmit the payments, choose the **OK** button.  
  
     After transmitting the electronic payments, post the payment journal.  
  
    > [!NOTE]  
    >  If you want to void a check after the journal has been transmitted and posted, you must contact your bank. You can then void the individual pieces of remittance advice from the **Check Ledger Entries** table. For more information, see [How to: Void Posted Checks](../how-to-void-posted-checks.md).  
  
## See Also  
 [Electronic Payments for United States, Canada, and Mexico](../electronic-payments-for-united-states-canada-and-mexico.md)   
 [How to: Set Up Electronic Payments for Bank Accounts](../how-to-set-up-electronic-payments-for-bank-accounts.md)   
 [How to: Void Posted Checks](../how-to-void-posted-checks.md)   
 Export Electronic Payments   
 Void-Transmit Elec. Payments   
 [How to: Export Electronic Payments](../how-to-export-electronic-payments.md)   
 [How to: Generate Electronic Payments](../how-to-generate-electronic-payments.md)