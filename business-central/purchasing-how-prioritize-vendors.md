---
title: Assign a Priority Level to a Vendor (contains video)
description: You can assign numbers to your vendors or suppliers to prioritize them and facilitate payment suggestions in Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supplier, payment priority
ms.search.form: 26, 27
ms.date: 04/01/2021
ms.author: bholtorf

---
# Prioritize Vendors

[!INCLUDE[prod_short](includes/prod_short.md)] can suggest various payments to vendors, for example, payments that will be due soon or payments where a discount is available. For more information, see [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).

First, you must prioritize your vendors by assigning numbers to them.
<br><br>
> [!Video https://www.microsoft.com/videoplayer/embed/RE3PRGa?rel=0]

## To prioritize vendors

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Select the relevant vendor, and then choose **Edit**.
3. In the **Priority** field, enter a number.

[!INCLUDE[prod_short](includes/prod_short.md)] considers the lowest number, except 0, to have the highest priority. So, for example, if you use 1, 2, and 3, then 1 will have the highest priority.

If you do not want to prioritize a vendor, leave the **Priority** field blank. Then, if you use the payment suggestion feature, the vendor will be listed after all the vendors that have a priority number. You can enter as many priority levels as necessary.

## See also

[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Managing Payables](payables-manage-payables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
