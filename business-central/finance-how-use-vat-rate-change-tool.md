---
title: Managing VAT rate changes
description: Learn how to use the VAT Rate Change tool to change VAT rates based on local legislation.
author: jswymer
ms.topic: how-to
ms.reviewer: jswymer
ms.search.keywords: VAT, VAT rate, posting, tax, value-added tax
ms.search.form: 550, 
ms.date: 04/28/2025
ms.author: jswymer
ms.service: dynamics-365-business-central
---

# Managing VAT rate changes

VAT rates can change depending on local legislation. Any change in VAT impacts your data in [!INCLUDE[prod_short](includes/prod_short.md)] whether the VAT rate is lowered, raised, or removed. VAT is connected to many entities in [!INCLUDE[prod_short](includes/prod_short.md)], such as customers, vendors, items, resources, item charges, and general ledger accounts. Changes in VAT rates usually happen at a specific date. Before that date, you should change your VAT setup, posting groups, and so on, so that new sales orders and purchase orders use the new VAT rate.

## Changing VAT rates

A good approach to managing a VAT rate change is to fully post and close open orders and other documents before the date of the rate change. Posting and closing helps ensure that the orders and documents aren't affected. This approach is the cleanest because it lets you start new orders and documents with the new VAT rate.

The following approach is suggested to manage a VAT rate change:

1. Post and close open orders, journals, and other documents fully before the switch date. However, you can wait until afterward as long as you don't add new lines and you ensure the effective date is before the switch date.  
2. Create the new VAT setup.  
3. Make the VAT switch on the relevant entities, such as customers, vendors, items, and so on.  
4. On the VAT rate switch date, you create new documents that use the new rate.  

## The VAT Rate Change tool

The VAT Rate Change tool can help you convert VAT rates on master data, journals, and orders. The tool is useful if you want to convert VAT on master data more easily or if you have orders that you can't close before the switch date. However, there are a few restrictions and limitations.

## Understanding the VAT rate conversion process and limitations

The VAT Rate Change tool converts VAT rates for master data, journals, and orders in different ways. The new general product posting group or VAT product post group update the selected master data and journals. If an order was fully or partially shipped, the shipped items keep the current general product posting group or VAT product posting group. A new order line is created for the unshipped items and updated to align current and new VAT or general product posting groups. Also, item charge assignments, configuration templates for items, reservations, and item tracking information updates accordingly.

On order lines, the unit price updates for all lines of the type Item and Resource, if you're using prices including VAT for the item. For other line types, you can decide whether to update the unit price.

There are a few things that the tool doesn't convert:

* Sales or purchase orders and invoices where shipments were posted. These documents are posted using the current VAT rate.  
* Documents with posted prepayment invoices. For example, you made or received prepayments on invoices that aren't completed before you use the VAT rate change tool. In this case, there's a difference between the VAT that's due and the VAT that was paid in the prepayments when the invoice is completed. The VAT rate change tool skips these documents and you must manually update them.  
* Sales or purchase orders with warehouse integration if they're partially shipped or received.  
* Drop shipments.
* Special orders.
* Assembly orders.
* Service contracts.  
* Credit memos.
* Return orders.
* Prices on items (master data)
* Prices on sales prices (master data)
* Business posting groups on customers and vendors.

### To prepare VAT rate change conversions

Before you set up the VAT rate change tool, make the following preparations.

* If you have transactions that use different rates, separate them into different groups. Do that either by creating new general ledger accounts for each rate or by using data filters to group transactions according to rate.  
* If you create new general ledger accounts, you must create new general posting groups.  
* To reduce the number of documents that get converted, post as many documents as possible. The fewer unposted documents you have, the better.  
* Back up data.

### To set up the VAT rate change tool

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change Setup**, and then choose the related link.  
2. On the **Master Data**, **Journals**, and **Documents** FastTabs, choose a posting group value from the option list for needed fields. For each group, choose whether to convert VAT product posting groups or general product posting groups, or convert both values if they're available for the master data. For some areas, you can also filter to convert only a subset of values, for example, G/L accounts.
3. On the **Unit Price Incl. VAT** FastTab, choose which line types on orders for which you want to update unit prices. Unit prices on lines of type Item and Resource always update.

### To set up product posting group conversion

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change Setup**, and then choose the related link.  
2. On the **VAT Rate Change Setup** page, choose either the **VAT Prod. Posting Group Conv.** or **Gen Prod. Posting Group Conv.** action.  
3. In the **From Code** field, enter the current posting group.  
4. In the **To Code** field, enter the new posting group.  

### To perform VAT rate change conversion

You use the VAT rate change tool to manage changes in the standard rate of VAT. You perform VAT and general posting group conversions to change VAT rates and maintain accurate VAT reporting. Depending on your setup, the following changes happen:  

* VAT and general posting groups are converted.  
* Changes are implemented in general ledger accounts, customers, vendors, open documents, journal lines, and so on.  

> [!IMPORTANT]  
> Before you perform VAT rate change conversion, you can test the conversion. To do so, follow these steps, but make sure to clear the **Perform Conversion** and **VAT Rate Change Tool Completed** checkboxes. During test conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is cleared and the **Converted Date** field in the **VAT Rate Change Log Entry** table is blank. After the conversion completes, choose **VAT Rate Change Log Entries** to view the results of the test conversion. Verify each entry before you perform the conversion. In particular, verify transactions that use an old VAT rate.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change**, and then choose the **VAT Rate Change Setup** link.  
2. Verify that you already set up the VAT product posting group conversion or general product posting group conversion.  
3. Choose the **Perform Conversion** checkbox.  

    > [!IMPORTANT]  
    > Clear the **VAT Rate Change Tool Completed** checkbox. The checkbox is automatically selected when the VAT rate change conversion is completed.  

4. Choose the **Convert** action.  
5. After the conversion is complete, choose the **VAT Rate Change Log Entries** action to view the results of the conversion.  

> [!IMPORTANT]  
> After the conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is chosen and the **Converted Date** field in the **VAT Rate Change Log Entry** table displays the conversion date.  

## Related information

[Set Up Value-Added Tax](finance-setup-vat.md)  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Local functionality in Business Central](about-localization.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
