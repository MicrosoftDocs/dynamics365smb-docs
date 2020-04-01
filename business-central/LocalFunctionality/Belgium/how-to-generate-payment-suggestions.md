---
    title: How to Generate Payment Suggestions
    description: After you have set up electronic banking, you can start generating payment suggestions. You can do this in the payment journal.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Generate Payment Suggestions
After you have set up electronic banking, you can start generating payment suggestions. You can do this in the payment journal.  

## To generate payment suggestions  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2.  Select the appropriate journal batch, and then choose the **Suggest Vendor Payments** action.  
3.  On the **Suggest Vendor Payments EB** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Last Due Date**|Enter the last due date that can appear on the vendor ledger entries to be included in the batch job.|  
    |**Take Credit Memos**|Select to include outstanding credit memos for vendors. The credit memos will be subtracted from the amount due. When selecting credit memos, the due date is not used.|  
    |**Take Payment Discounts**|Select to include vendor ledger entries for which you can receive a payment discount.|  
    |**Payment Discount Date**|Enter the date that will be used to calculate a payment discount.|  
    |**Available Amount**|If there is a maximum amount available for payments, you can enter it here. The batch job will then create a payment suggestion based on this amount and the priority of vendors.|  
    |**Posting Date**|Enter the date that will appear as the posting date on the lines that the batch job inserts in the payment journal.|  

4.  Enter the filter criteria.  
5.  Choose the **OK** button to start the batch job.  

When the batch job is finished, the payment journal contains all vendor ledger entries that match the filters.  

## See Also  
 [Belgian Electronic Payments](belgian-electronic-payments.md)   
 [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
 [Test Electronic Payments](how-to-test-electronic-payments.md)   
 [Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md)   
 [Print Payment Files](how-to-print-payment-files.md)
