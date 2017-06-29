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
# How to: File SEPA Payments
In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can use Single Euro Payments Area \(SEPA\) credit transfers to file SEPA payments with the bank.  
  
 SEPA unifies payment methods in participating European countries\/regions, which makes international payments as easy to process as domestic payments. European citizens and companies can make and receive payments in euros, whether within or across national borders, with the same basic conditions, rights, and obligations, regardless of location.  
  
 Before you can file a SEPA payment you must complete the following administration tasks:  
  
-   Set up a new export protocol. For more information, see Export Protocol.  
  
-   In the **Country\/Region** table, select the **SEPA Allowed** field for each country that belongs to the EEA zone.  
  
-   Verify that the **Currency Euro** field in the **General Ledger Setup** table corresponds with the currency in the payment lines.  
  
-   Verify that the vendor’s **Preferred Bank Account** field in the **Vendor** table contains the IBAN and SWIFT code.  
  
### To file a SEPA payment  
  
1.  In the **Search** box, enter **File SEPA Payments**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_2000005\_N\_2\_11 Journal Template Name $\)**|Specify the general journal template for the SEPA payment report.|  
    |**\($ B\_2000005\_N\_2\_7 Journal Batch $\)**|Specify the general journal batch for the SEPA payment report.|  
    |**\($ B\_2000005\_N\_2\_3 Post General Journal Lines $\)**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**\($ B\_2000005\_N\_2\_13 Include Dimensions $\)**|Enter the dimensions that you want to include in the SEPA payment report. The option is only available if the **Summarize Gen. Jnl. Lines** field in the **Electronic Banking Setup** window is selected.|  
    |**\($ B\_2000005\_N\_2\_5 Execution Date $\)**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**\($ B\_2000005\_N\_2\_1 File Name $\)**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 File SEPA Payments   
 [How to: Set Up Export Protocols](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-export-protocols.md)   
 Export Protocol   
 [How to: File Non\-Euro SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-file-non-euro-sepa-payments.md)   
 [How to: Activate SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-activate-sepa-payments.md)