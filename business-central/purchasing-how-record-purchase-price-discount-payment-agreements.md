---
title: Record special purchase prices and discounts
description: Set up and manage special purchase prices and discounts for vendors, and automatically apply them to purchase documents.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: special price, alternate price, pricing
ms.search.form: 26, 1346, 7012, 7014, 7017, 7018, 7189, 7190, 9307
ms.date: 08/25/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Record special purchase prices and discounts

> [!NOTE]
> In 2020 release wave 2 we released streamlined processes for setting up and managing prices and discounts. If you're a new customer using that version, you're using the new experience. If you're an existing customer, whether you're using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. Learn more in [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

The different price and discount agreements that apply when you buy from different vendors must be defined so that the agreed rules and values are applied to purchase documents that you create for the vendors.

When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[prod_short](includes/prod_short.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on project and item journal lines. Learn more in [Best Price Calculation](purchasing-how-record-purchase-price-discount-payment-agreements.md#best-price-calculation).

Concerning prices, you can have a special purchase price inserted on purchase lines if a certain combination of vendor, item, minimum quantity, unit of measure, or starting/ending date exists.

Concerning discounts, you can set up and use two types of purchase discounts:

| Discount Type | Description |
| --- | --- |
| **Purchase Line Discount** |An amount discount that is inserted on purchase lines if a certain combination of vendor, item, minimum quantity, unit of measure, or starting/ending date exists. This type works in the same way as for purchase prices. |
| **Invoice Discount** |A percentage discount that is subtracted from the document total if the value amount of all lines on a purchase document exceeds a certain minimum. |

Because purchase line discounts and purchase prices are based on a combination of item and vendor, you can also enter this configuration from the item card, where the rules and values are defined. Learn more in [Register New Items](inventory-how-register-new-items.md).

## Set up a special purchase price for a vendor

#### [Current Experience](#tab/current-experience)

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then choose the related link.
2. Open the relevant vendor card, and then choose the **Prices** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Fill in one line for each combination for which the vendor grants you a special purchase price.

#### [New Experience](#tab/new-experience)

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then choose the related link.
2. Select the vendor, and then choose the **Purchase Price Lists** action.
3. Choose **New** to create a new purchase price list.
4. On the **General** and **Tax** FastTabs, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. To add items to the list, do one of the following:
   * To add many items, choose **Suggest Lines**, and then enter filter criteria to specify the types of items to add. Optionally, you can also enter some additional settings for the items that are specific to the price list. You can change these later, if needed.
   * To copy items from another price list, choose **Copy Lines**, and then choose the price list to copy.
   * To add items manually, in the grid, in the **Product Type** field, choose the type of product that the price list is for. Depending on your selection, fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. To start using the price list, in the **Status** field, choose **Active**.

> [!NOTE]
> If the vendor has a value in the **Pay-to Vendor No.** field, the **Purchase Price Lists** action shows price lists for the pay-to vendor. In the new pricing experience, purchase document lines use the buy-from vendor to find prices and line discounts.

## Set up a line discount for a vendor

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then choose the related link.
2. Open the relevant vendor card, and then choose the **Line Discounts** action.

   The **Vendor No.** field is prefilled with the vendor number.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Fill a line for each combination for which the vendor grants you a purchase line discount.

## Set up an invoice discount for a vendor

When your vendors have informed you which invoice discounts they grant, enter the invoice discount code on the vendor cards and set up the terms for each code.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then choose the related link.
2. Open the vendor card for a vendor that will be eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the vendor.

    > [!NOTE]  
    > Invoice discount codes are represented by existing vendor cards. This enables you to quickly assign invoice discount terms to vendors by picking the name of another vendors who have the same terms.

    Proceed to set up new the purchase invoice discount terms.
4. On the **Vendor Card** page, choose the **Invoice Discounts** action. The **Vend. Invoice Discounts** page opens.
5. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to. Leave the field blank to set up invoice discount terms in USD.
6. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
7. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
8. Repeat steps 5 through 7 for each currency that the vendor receives a different invoice discount for.

The invoice discount is now set up and assigned to the vendor in question. When you select the vendor code in the **Invoice Disc. Code** field on other vendor cards, the same invoice discount is assigned to those vendors.

## Choose a principle for posting purchase discounts

When you post a purchase invoice that includes one or more discounts, you can choose between two principles for posting discount amounts. You can post discounts separately or you can subtract discounts from invoice discounts.  

Before you can do this, you must have already set up the necessary accounts for posting discount amounts in the chart of accounts. You must also check that you have entered the correct account numbers in the general posting setup in the **Purch. Line Disc. Account** and **Purch. Inv. Disc. Account** fields.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchases & Payables Setup**, and then choose the related link.
2. In the **Discount Posting** field, choose one of the following principles for posting discounts.

|**Discount Posting Principle**|**Invoice Discount**|**Line Discount**|  
|------------------------------------|--------------------------|-----------------------|  
|**All Discounts**|Posted separately|Posted separately|  
|**Invoice Discounts**|Posted separately|Subtracted|  
|**Line Discounts**|Subtracted|Posted separately|  
|**No Discounts**|Subtracted|Subtracted|  

## Purchase invoice discounts and service charges

If you have fixed terms for invoice discounts with any vendors, you can enter them for those vendors. Then the discount is calculated when you fill in a purchase invoice.  

Before you can use invoice discounts with purchases, you must specify the vendors that offer you the discounts.  

You link discount percentages to specific invoice amounts in **Vend. Invoice Discounts** pages. You can enter any number of percentages in each page. Each vendor can have its own page, or you can link several vendors to the same page.  

In addition to a discount percentage, you can link a service charge amount to a specific invoice amount.  

You can define the terms of the invoice discount in LCY for domestic vendors and in foreign currency for foreign vendors.  

You can choose to have [!INCLUDE[prod_short](includes/prod_short.md)] automatically calculate the invoice discounts for quotes, blanket orders, orders, invoices, or credit memos.  

> [!TIP]  
> Before you enter this information, it's a good idea to prepare an outline of the discount structure that you want to use. This makes it easier to see which vendors can be linked to the same invoice discount page. The fewer pages that you have to set up, the faster that you can enter the basic information.

## Best price calculation

When you record special purchase prices and line discounts, [!INCLUDE[prod_short](includes/prod_short.md)] calculates the lowest permitted price and the highest permitted line discount for purchase document lines.

The vendor that [!INCLUDE[prod_short](includes/prod_short.md)] uses to find prices and line discounts depends on your pricing experience:

| Pricing experience | Vendor used for prices and line discounts |
| --- | --- |
| Current experience | The vendor in the **Pay-to Vendor No.** field on the purchase document. |
| New experience | The vendor in the **Buy-from Vendor No.** field on the purchase document. |

This behavior applies to purchase prices and line discounts on document lines. Invoice discounts use the invoice discount code from the pay-to vendor.

For the selected vendor, [!INCLUDE[prod_short](includes/prod_short.md)] checks whether a price or line discount agreement applies to the item, variant, quantity, unit of measure, currency, and date. For invoices and credit memos, it uses the date in the **Posting Date** field. For other purchase documents, it uses the date in the **Order Date** field. It then inserts the applicable direct unit cost and line discount percentage.

In the current pricing experience, agreements apply to a specific pay-to vendor and item. In the new pricing experience, agreements can apply to a specific buy-from vendor or all vendors, and line discounts can also apply to an item discount group. Purchases don't support vendor price groups or vendor discount groups.

If no special purchase price applies, [!INCLUDE[prod_short](includes/prod_short.md)] uses the applicable stockkeeping unit's last direct cost, when available, or the item's last direct cost.

## Related information

[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
