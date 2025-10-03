---
title: Assign a Priority Level to a Vendor
description: Assign priority numbers to vendors or suppliers in Business Central to streamline payment suggestions and manage payables efficiently.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: supplier, payment priority
ms.search.form: 26, 27
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Prioritize vendors

[!INCLUDE[prod_short](includes/prod_short.md)] can suggest various payments to vendors, for example, payments that are due soon or payments where a discount is available. Learn more in [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).

First, you must prioritize your vendors by assigning numbers to them.
<br><br>
> [!Video https://learn-video.azurefd.net/vod/player?id=283f5ccb-3cbb-48c5-b50d-fd91466e8094]

## Prioritize vendors

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then choose the related link.
2. Select the relevant vendor, and then choose **Edit**.
3. In the **Priority** field, enter a number.

[!INCLUDE[prod_short](includes/prod_short.md)] considers the lowest number, except 0, to have the highest priority. So, for example, if you use 1, 2, and 3, then 1 has the highest priority.

If you don't want to prioritize a vendor, leave the **Priority** field blank. Then, if you use the payment suggestion feature, the vendor will be listed after all the vendors that have a priority number. You can enter as many priority levels as necessary.

## Related information

- [Register New Vendors](purchasing-how-register-new-vendors.md)  
- [Setting Up Purchasing](purchasing-setup-purchasing.md)  
- [Managing Payables](payables-manage-payables.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
