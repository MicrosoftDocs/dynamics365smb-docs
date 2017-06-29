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
# How to: File Non-Euro SEPA Payments
In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can file non\-euro SEPA payments with the bank. This is useful when you make payments to other countries that do not use SEPA and for currencies other than the euro.  
  
 Before you can file a non\-euro SEPA payment you must complete the following administration tasks:  
  
-   Set up a new export protocol for a non\-euro SEPA. For more information, see Export Protocol.  
  
-   In the **Country\/Region** table, clear the **SEPA Allowed** field for each country that belongs to the EEA zone.  
  
-   Verify that the **Currency Euro** field in the **General Ledger Setup** table is not in euro currency.  
  
-   Verify that the vendor’s **Preferred Bank Account** field in the **Vendor** table contains the IBAN and SWIFT code.  
  
### To file a non\-euro SEPA payment  
  
1.  In the **Search** box, enter **File Non Euro SEPA Payments**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_2000006\_N\_2\_1 Journal Template Name $\)**|Specify the general journal template for the non\-euro SEPA payment report.|  
    |**\($ B\_2000006\_N\_2\_7 Journal Batch $\)**|Specify the general journal batch for the non\-euro SEPA payment report.|  
    |**\($ B\_2000006\_N\_2\_3 Post General Journal Lines $\)**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**\($ B\_2000006\_N\_2\_13 Include Dimensions $\)**|Enter the dimensions that you want to include in the non\-euro SEPA payment report. The option is only available if the **Summarize Gen. Jnl. Lines** field in the **Electronic Banking Setup** window is selected.|  
    |**\($ B\_2000006\_N\_2\_5 Execution Date $\)**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**\($ B\_2000006\_N\_2\_1 File Name $\)**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 File Non Euro SEPA Payments   
 File SEPA Payments   
 [How to: File SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-file-sepa-payments.md)   
 [How to: Activate SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-activate-sepa-payments.md)   
 [SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/sepa-payments.md)