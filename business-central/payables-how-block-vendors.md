---
title: Block vendors
description: Read about how to block vendors from being included in any transactions, or just how to block new payments to them.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.form: 27,
ms.date: 12/16/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Block vendors

You can block a vendor, for example because of insolvency, so that people can't select the vendor on purchase documents or post payments to the vendor.

The following table describes the options for blocking vendors.  

|Option|Description|  
|--------------------|------------|  
|**Blank**|Transactions are allowed for this vendor.|
|**Payment**|New payments can't be created for this vendor.|  
|**All**|No transactions are allowed for this vendor.|  

## To block a vendor

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Select the vendor that you want to block.
3. In the **Blocked** field, choose one of the options for blocking.

## Handling vendor payment disputes

You can out vendor ledger entries **On hold** if there's a dispute about a supplier document.

To learn more, go to [Handling vendor payment disputes](payables-how-handling-payment-disputes.md).

## Related information  

[Handling vendor payment disputes](payables-how-handling-payment-disputes.md)  
[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Making Payments](payables-make-payments.md)  
[Managing Payables](payables-manage-payables.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
