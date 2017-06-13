---
title: Create a Vendor Card to Register a New Vendor | Microsoft Docs
description: Learn how to create a vendor card to register a new vendor or supplier.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supplier
ms.date: 03/29/2017
ms.author: sgroespe

---
# How to: Register New Vendors
Vendors provide the products that you sell. Each vendor that you purchase from must be registered as a vendor card.

Before you can register new vendors, you must set up various purchase codes that you can select from when you fill vendor cards. When all of the required master data is created, you can perform additional configuration of the vendor, such as prioritize the vendor for payment purposes and list items that the vendor and other vendors can supply. Another group of setup tasks for vendors is to record your agreements concerning discounts, prices, and payment methods. For more information, see [Setting Up Purchasing](purchasing-setup-purchasing.md).

Vendor cards hold the information that is required to buy products from the vendor. For more information, see [How to: Record Purchases](purchasing-how-record-purchases.md) and [How to: Register New Items](inventory-how-register-new-items.md).

> [!NOTE]  
>   If vendor templates exist for different vendor types, then a window appears when you create a new vendor card from where you can select an appropriate template. If only one vendor template exists, then new vendor cards always use that template.

## To create a new vendor card
1. On the Home page, choose **Vendors** to open the list of existing vendors.  
2. In the **Vendors** window, Choose **New**.

    If more than one vendor template exists, then a window opens from which you can select a vendor template. In that case, follow the next two steps.
3. In the **Select a template for a new vendor** window, choose the template that you want to use for the new vendor card.
4. Choose the **OK** button. A new vendor card opens with some fields filled with information from the template.
5. Proceed to fill or change fields on the vendor card as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

The vendor is now registered, and the vendor card is ready to be used on purchase documents.

If you want to use this vendor card as a template when you create new vendor cards, you can save it as a vendor template. For more information, see the following section.

## To save the vendor card as a template
1. In the **Vendor Card** window, choose the **Save as Template** action. The **Vendor Template** window opens showing the vendor card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** window opens showing any dimension codes that are set up for the vendor.
4. Edit or enter dimension codes that will apply to new vendor cards created by using the template.
5. When you have completed the new vendor template, choose the **OK** button.  
   The vendor template is added to the list of vendor templates, so that you can use it to create new vendor cards.

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[How to: Record Purchases](purchasing-how-record-purchases.md)   
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
