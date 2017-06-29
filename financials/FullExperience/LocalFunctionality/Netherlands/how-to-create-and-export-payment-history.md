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
# How to: Create and Export Payment History
After you have created a proposal and made any modifications, you can process the proposal to create a payment history. Proposals can be created manually or automatically from a vendor or customer ledger entry. For more information, see [How to: Create Proposals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-proposals.md).  
  
 For exporting payment histories, the following protocols are supported:  
  
-   \($ B\_11000006 CLIEOP3 $\)  
  
-   \($ B\_11000007 BTL91 $\)  
  
-   BBV  
  
-   PAYMUL  
  
### To create a payment history for a proposal  
  
1.  In the **Search** box, enter **Telebank - Bank Overview**, and then choose the related link.  
  
     If you want to print the proposal before you process it, choose the **Print** button.  
  
2.  To process the proposal, choose **Proposal** , and then choose **Process**.  
  
3.  To view the payment history, close the **Telebank Proposal** window. Make sure the same bank account in the **\($ N\_11000000 Telebank – Bank Overview $\)** window is selected. On the **Actions** tab, in the **Telebank** group, choose **Payment History**.  
  
     The **Payment History List** window displays the payment history that you just created.  
  
### To export a payment history  
  
-   In the **Payment History List** window, on the **Home** tab, choose **Export**.  
  
    > [!NOTE]  
    >  A text file will be created. This file contains the path and file name as defined in the Default File Names Field field of the export protocol.  
  
## See Also  
 [How to: Create Proposals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-proposals.md)   
 Paymt. History - Change Status Batch Job