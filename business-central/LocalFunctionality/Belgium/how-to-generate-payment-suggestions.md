---
title: Generate payment suggestions [BE]
description: After setting up electronic banking, you can start generating payment suggestions in the payment journal.
author: brentholtorf
ms.topic: conceptual
ms.search.form: 256
ms.date: 04/02/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Generate payment suggestions in the Belgian version

After you set up electronic banking, you can start generating payment suggestions. You can do this in the payment journal.  

## Generate payment suggestions  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
1. Select the appropriate journal batch, and then choose the **Suggest Vendor Payments** action.  
1. On the **Suggest Vendor Payments EB** page, fill in the fields as described in the following table.  

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Last Due Date**|Enter the last due date that can appear on the vendor ledger entries to be included in the batch job.|  
   |**Take Credit Memos**|Select to include outstanding credit memos for vendors. The credit memos are subtracted from the amount due. When you select credit memos, the due date isn't used.|  
   |**Take Payment Discounts**|Select to include vendor ledger entries for which you can receive a payment discount.|  
   |**Payment Discount Date**|Enter the date that is used to calculate a payment discount.|  
   |**Available Amount**|If there's a maximum amount available for payments, you can enter it here. The batch job creates a payment suggestion based on this amount and the priority of vendors.|  
   |**Posting Date**|Enter the date that appears as the posting date on the lines that the batch job inserts in the payment journal.|  

1. Enter the filter criteria.  
1. Choose the **OK** button to start the batch job.  

When the batch job is finished, the payment journal contains all vendor ledger entries that match the filters.  

## Related information

- [Belgian Electronic Payments](belgian-electronic-payments.md)
- [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)
- [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)
- [Test Electronic Payments](how-to-test-electronic-payments.md)
- [Print Payment Files](how-to-print-payment-files.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
