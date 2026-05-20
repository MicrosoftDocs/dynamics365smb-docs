---
title: Set up subcontractor prices
description: Learn how to set up and maintain subcontractor prices for work center groups, including copying prices between vendors and filtering options.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, prices, work center group, vendor
ms.search.form: 99000886
ms.date: 05/20/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up subcontractor prices

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

You can store subcontractor prices and view all prices for each item at a glance. You can maintain subcontractor prices by assigning them to vendors, standard catalog filters, and work center groups. You can access subcontractor prices from the work center group card and the vendor card.

## Set up subcontractor prices

The following steps describe how to set up subcontractor prices.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontractor Prices**, and then choose the related link.
2. On the **General** FastTab, use the filters to find specific subcontractor prices. The following filters are available:

   - **Vendor No. Filter**
   - **Work Center Group No. Filter**
   - **Standard Catalog Code Filter**
   - **Item No. Filter**
   - **Starting Date Filter**

3. In the lines, fill in the following required fields:
   - **Work Center Group No.**
   - **Vendor No.**
   - **Item No.**

4. In the **Standard Catalog Code** field, enter specific activities for the work center group.
5. In the **Purchase Price** field, enter the activity-related price. You can specify prices for items, time periods, units of measure, and quantities.

> [!NOTE]
> The **Work Center Group No.**, **Vendor No.**, and **Item No.** fields are required.

## Set up prices from a work center group

You can store activity-related prices for individual work center groups.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Center Groups**, and then choose the related link.
2. Open the work center group.
3. Choose the **Subcontractor Prices** action.

   [!INCLUDE [prod_short](includes/prod_short.md)] displays the **Subcontractor Prices** page with the **Work Center Group No. Filter** already filled in.

4. In the lines, in the **Standard Catalog Code** field, enter specific activities for the work center group.
5. In the **Purchase Price** field, enter the activity-related price. You can specify prices for items, item variants, time periods, units of measure, and quantities. You can also specify minimum quantities.
6. If you agreed on a minimum amount per process with your subcontracting vendor for each production order quantity, enter it in the **Minimum Amount** field.

   Price determination for the production order operation considers this amount and determines the purchase price based on the order quantity.

> [!NOTE]
> The **Work Center Group No.**, **Vendor No.**, and **Item No.** fields are required.

## Copy prices between vendors

You can copy subcontractor prices from one vendor to another vendor.

1. On the **Subcontractor Prices** page, in the **Vendor No. Filter** field, enter the vendor number from which you want to copy prices.
2. In the **Work Center Group No. Filter** field, enter the work center group number.
3. Choose the **Copy Subcontractor Prices** action.
4. Select the lines you want to copy.
5. Choose **OK**.

[!INCLUDE [prod_short](includes/prod_short.md)] copies the selected lines for the specified vendor.

## View prices from a routing

You can view subcontractor prices from a routing.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routing**, and then choose the related link.
2. Open the routing.
3. On the lines, select the subcontracting operation.
4. Choose the **Subcontractor Prices** action.

[!INCLUDE [prod_short](includes/prod_short.md)] displays the **Subcontractor Prices** page where you can view or edit the information for the item.

## Related information

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]