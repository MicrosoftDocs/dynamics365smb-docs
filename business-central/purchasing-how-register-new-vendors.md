---
title: Create a Vendor Card to Register a New Vendor | Microsoft Docs
description: Learn how to create a vendor card to register a new vendor or supplier.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supplier
ms.date: 04/01/2020
ms.author: sgroespe

---
# Register New Vendors
Vendors provide the products that you sell. Each vendor that you purchase from must be registered as a vendor card.

Before you can register new vendors, you must set up various purchase codes that you can select from when you fill vendor cards. When all of the required master data is created, you can perform additional configuration of the vendor, such as prioritize the vendor for payment purposes and list items that the vendor and other vendors can supply. Another group of setup tasks for vendors is to record your agreements concerning discounts, prices, and payment methods. For more information, see [Setting Up Purchasing](purchasing-setup-purchasing.md).

Vendor cards hold the information that is required to buy products from the vendor. For more information, see [Record Purchases](purchasing-how-record-purchases.md) and [Register New Items](inventory-how-register-new-items.md).

> [!NOTE]  
>   If vendor templates exist for different vendor types, then a page appears when you create a new vendor card from where you can select an appropriate template. If only one vendor template exists, then new vendor cards always use that template.
<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE3PZtd?rel=0]

## To create a new vendor card
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
2. On the **Vendors** page, Choose **New**.

    If more than one vendor template exists, then a page opens from which you can select a vendor template. In that case, follow the next two steps.
3. On the **Select a template for a new vendor** page, choose the template that you want to use for the new vendor card.
4. Choose the **OK** button. A new vendor card opens with some fields filled with information from the template.
5. Proceed to fill or change fields on the vendor card as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
>   If you do not know the invoicing address that will be used for every invoice from a vendor, do not fill in the **Pay-to** field. Instead, choose the pay-to vendor number after you have set up a purchase quote, order, or invoice header.

The vendor is now registered, and the vendor card is ready to be used on purchase documents.

If you want to use this vendor card as a template when you create new vendor cards, you can save it as a vendor template. For more information, see the following section.

## To save the vendor card as a template
1. On the **Vendor Card** page, choose the **Save as Template** action. The **Vendor Template** page opens showing the vendor card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** page opens showing any dimension codes that are set up for the vendor.
4. Edit or enter dimension codes that will apply to new vendor cards created by using the template.
5. When you have completed the new vendor template, choose the **OK** button.  
   The vendor template is added to the list of vendor templates, so that you can use it to create new vendor cards.

## See Also
[Merge Duplicate Records](sales-how-merge-duplicate-records.md)  
[Create Number Series](ui-create-number-series.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Record Purchases](purchasing-how-record-purchases.md)   
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
