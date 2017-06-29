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
# How to: Generate Payment Suggestions
After you have set up electronic banking, you can start generating payment suggestions. You can do this in the payment journal.  
  
### To generate payment suggestions  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  Select the appropriate journal batch, and on the **Home** tab, in the **Progress** group, choose **Suggest Vendor Payments**.  
  
3.  In the **Suggest Vendor Payments EB**  window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_2000019\_F\_1\_3 Last Due Date $\)**|Enter the last due date that can appear on the vendor ledger entries to be included in the batch job.|  
    |**\($ B\_2000019\_F\_1\_5 Take Credit Memos $\)**|Select to include outstanding credit memos for vendors. The credit memos will be subtracted from the amount due. When selecting credit memos, the due date is not used.|  
    |**\($ B\_2000019\_F\_1\_14 Take Payment Discounts $\)**|Select to include vendor ledger entries for which you can receive a payment discount.|  
    |**\($ B\_2000019\_F\_1\_7 Payment Discount Date $\)**|Enter the date that will be used to calculate a payment discount.|  
    |**\($ B\_2000019\_F\_1\_9 Available Amount $\)**|If there is a maximum amount available for payments, you can enter it here. The batch job will then create a payment suggestion based on this amount and the priority of vendors.|  
    |**\($ B\_2000019\_F\_1\_12 Posting Date $\)**|Enter the date that will appear as the posting date on the lines that the batch job inserts in the payment journal.|  
  
4.  On the **Vendor** FastTab, enter the filter criteria.  
  
5.  Choose the **OK** button to start the batch job.  
  
     When the batch job is finished, the payment journal contains all vendor ledger entries that match the filters.  
  
## See Also  
 [Belgian Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-payments.md)   
 [How to: Set Up Vendors for Automatic Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [How to: Create Payment Journal Templates and Batches](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-create-payment-journal-templates-and-batches.md)   
 [How to: Test Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-test-electronic-payments.md)   
 [How to: Manage Electronic Payment Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-manage-electronic-payment-lines.md)   
 [How to: Print Payment Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-print-payment-files.md)