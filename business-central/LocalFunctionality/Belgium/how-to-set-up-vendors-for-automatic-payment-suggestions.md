---
title: Set Up Vendors for Automatic Payment Suggestions [BE]
description: Configure vendors to automatically include their unpaid invoices in payment suggestions for streamlined processing.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: unpaid invoices, payment suggestions, vendor setup, automatic payments, Belgian version
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Set up vendors for automatic payment suggestions in the Belgian version

You can set up each vendor so that unpaid invoices from that vendor are automatically included in payment suggestions. By default, new vendors are included. If you don't want a vendor's outstanding ledger entries to be included in payment suggestions, clear the **Suggest Payments** checkbox for that vendor.

You can also use the **Priority** and **Preferred Bank Account Code** fields to fine-tune how a vendor is handled when you generate payment suggestions.

## Set up a vendor to be included in the payment suggestion batch  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. On the **Vendors** page, select a relevant vendor, and then choose the **Edit** action.  
1. On the vendor card, go to the **Payments** FastTab, and then fill in the fields as described in the following table.

   |Field|Description|
   |---------------------------------|---------------------------------------|
   |**Priority**|Specifies the importance of the vendor when suggesting payments with the **Suggest Vendor Payments** function. Vendors with a higher priority are paid first when the available amount for payments is limited.|
   |**Preferred Bank Account Code**|Specifies the vendor's bank account that's automatically inserted as the beneficiary bank account on payment journal lines created for this vendor.|
   |**Suggest Payments**|Select to include the vendor's outstanding ledger entries in payment suggestions. This checkbox is selected by default for new vendors. Clear it if you don't want payment suggestions generated for the vendor.|

1. Choose the **OK** button.  
  
## Related information

- [Belgian Electronic Banking](belgian-electronic-banking.md)  
- [Belgian Electronic Payments](belgian-electronic-payments.md)  
- [Suggest Vendor Payments](../../payables-how-suggest-vendor-payments.md)  
- [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)  
- [Test Electronic Payments](how-to-test-electronic-payments.md)  
- [Print Payment Files](how-to-print-payment-files.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
