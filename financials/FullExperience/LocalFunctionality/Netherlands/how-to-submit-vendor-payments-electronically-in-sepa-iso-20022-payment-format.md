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
# How to: Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you can create and submit Single Euro Payments Area \(SEPA\) ISO 20022 vendor payments electronically.  
  
 Before you can create and submit SEPA vendor payments, you must enable SEPA payments. For more information, see [How to: Activate SEPA Payments-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-activate-sepa-payments-duplicate.md).  
  
### To submit vendor payments electronically in SEPA ISO 20022 payment format  
  
1.  In the **Search** box, enter **Telebank-Bank Overview**, and then choose the related link.  
  
2.  Select the relevant bank account, and then, on the **Navigate** tab, in the **Telebank** group, choose **Proposal**.  
  
3.  Select the relevant vendor bank account, and then, on the **Navigate** tab, in the **Proposal** group, choose **Get Entries**.  
  
4.  In the **Get Proposal Entries** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Currency Date**|Specify the currency date.|  
    |**Pmt. Discount Date**|Specify the payment discount date.|  
  
5.  On the **Transaction Mode** FastTab, select the appropriate filters.  
  
6.  On the **Cust. Ledger Entry** FastTab, select the appropriate filters.  
  
7.  On the **Vendor Ledger Entry** FastTab, select the **Vendor No.** filter, and then select a vendor number.  
  
    > [!NOTE]  
    >  Select other appropriate filters if required.  
  
8.  Choose the **OK** button.  
  
     The proposal lines populate in the **Telebank Proposal** window.  
  
## See Also  
 [How to: Activate SEPA Payments-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-activate-sepa-payments-duplicate.md)   
 [Single EURO Payments Area \(SEPA\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/single-euro-payments-area-sepa-.md)   
 Telebank - Bank Overview Window   
 Telebank Proposal Window