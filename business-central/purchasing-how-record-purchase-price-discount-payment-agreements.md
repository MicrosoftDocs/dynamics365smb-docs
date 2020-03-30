---
title: Special and Alternate Vendor Pricing and Discounts | Microsoft Docs'
description: You can define different or alternate prices and discount agreements and apply them to purchase documents for vendors.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 04/01/2020
ms.author: sgroespe

---
# Record Special Purchase Prices and Discounts
The different price and discount agreements that apply when you buy from different vendors must be defined so that the agreed rules and values are applied to purchase documents that you create for the vendors.

When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines. For more information, see [Best Price Calculation](purchasing-how-record-purchase-price-discount-payment-agreements.md#best-price-calculation).

Concerning prices, you can have a special purchase price inserted on purchase lines if a certain combination of vendor, item, minimum quantity, unit of measure, or starting/ending date exists.

Concerning discounts, you can set up and use two types of purchase discounts:

| Discount Type | Description |
| --- | --- |
| **Purchase Line Discount** |An amount discount that is inserted on purchase lines if a certain combination of vendor, item, minimum quantity, unit of measure, or starting/ending date exists. This works in the same way as for purchase prices. |
| **Invoice Discount** |A percentage discount that is subtracted from the document total if the value amount of all lines on a purchase document exceeds a certain minimum. |

Because purchase line discounts and purchase prices are based on a combination of item and vendor, you can also enter this configuration from the item card, where the rules and values are defined. For more information, see [Register New Items](inventory-how-register-new-items.md).

## To set up a special purchase price for a vendor
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the relevant vendor card, and then choose the **Prices** action.

    The **Purchase Type** field is prefilled with **Vendor**, and the **Purchase Code** field is prefilled with the vendor number.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Fill a line for each combination for which the vendor grants you a purchase line discount.

## To set up a line discount for a vendor
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the relevant vendor card, and then choose the **Line Discounts** action.

    The **Purchase Type** field is prefilled with **Vendor**, and the **Purchase Code** field is prefilled with the vendor number.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Fill a line for each combination for which the vendor grants you a purchase line discount.

## To set up an invoice discount for a vendor
When your vendors have informed you which invoice discounts they grant, enter the invoice discount code on the vendor cards and set up the terms for each code.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the vendor card for a vendor that will be eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the vendor.

    > [!NOTE]  
    >   Invoice discount codes are represented by existing vendor cards. This enables you to quickly assign invoice discount terms to vendors by picking the name of another vendors who will have the same terms.

    Proceed to set up new the purchase invoice discount terms.
4. On the **Vendor Card** page, choose the **Invoice Discounts** action. The **Vend. Invoice Discounts** page opens.
5. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to. Leave the field blank to set up invoice discount terms in USD.
6. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
7. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
8. Repeat steps 5 through 7 for each currency that the vendor will receive a different invoice discount for.

The invoice discount is now set up and assigned to the vendor in question. When you select the vendor code in the **Invoice Disc. Code** field on other vendor cards, the same invoice discount is assigned to those vendor.

## To choose a principle for posting purchase discounts  
When you post a purchase invoice that includes one or more discounts, you can choose between two principles for posting discount amounts. You can post discounts separately or you can subtract discounts from invoice discounts.  

Before you can do this, you must have already set up the necessary accounts for posting discount amounts in the chart of accounts. You must also check that you have entered the correct account numbers in the general posting setup in the **Purch. Line Disc. Account** and **Purch. Inv. Disc. Account** fields.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.
2. In the **Discount Posting** field, choose one of the following principles for posting discounts.

|**Discount Posting Principle**|**Invoice Discount**|**Line Discount**|  
|------------------------------------|--------------------------|-----------------------|  
|**All Discounts**|Posted separately|Posted separately|  
|**Invoice Discounts**|Posted separately|Subtracted|  
|**Line Discounts**|Subtracted|Posted separately|  
|**No Discounts**|Subtracted|Subtracted|  

## Purchase Invoice Discounts and Service Charges
If you have fixed terms for invoice discounts with any vendors, you can enter them for those vendors. Then the discount will be calculated when you fill in a purchase invoice.  

 Before you can use invoice discounts with purchases, you must specify the vendors that offer you the discounts.  

 You link discount percentages to specific invoice amounts in **Vend. Invoice Discounts** pages. You can enter any number of percentages in each page. Each vendor can have its own page, or you can link several vendors to the same page.  

 In addition to a discount percentage, you can link a service charge amount to a specific invoice amount.  

 You can define the terms of the invoice discount in LCY for domestic vendors and in foreign currency for foreign vendors.  

 You can choose to have [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculate the invoice discounts for quotes, blanket orders, orders, invoices, or credit memos.  

> [!TIP]  
>  Before you enter this information, it is a good idea to prepare an outline of the discount structure that you want to use. This makes it easier to see which vendors can be linked to the same invoice discount page. The fewer pages that you have to set up, the faster that you can enter the basic information.

## Best Price Calculation
When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines.

The best price is the lowest permissible price with the highest permissible line discount on a given date. [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates this when it inserts the unit price and the line discount percentage for items on new document and journal lines.

> [!NOTE]  
>   The following describes how the best price is calculated for sales. The calculation is the same for purchases.

1. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

    - Does the customer have a price/discount agreement, or does the customer belong to a group that does?
    - Is the item or the item discount group on the line included in any of these price/discount agreements?
    - Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?
    - Is a unit of measure code specified? If so, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks if any price/discount agreements apply to information on the document or journal line, and then inserts the applicable unit price and line discount percentage, using the following criteria:

    - Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
    - Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if LCY would provide a better price. If there is no price/discount agreement for the specified currency code, [!INCLUDE[d365fin](includes/d365fin_md.md)] inserts the lowest price and the highest line discount in LCY.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## See Related Training at [Microsoft Learn](/learn/modules/set-up-prices-discounts-dynamics-365-business-central/index)

## See Also
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
