---
title: Manage VAT Rate Changes in Business Central
description: Prepare for a VAT rate change in Business Central, set up posting group conversions, and test the VAT Rate Change tool before converting your data.
author: jswymer
ms.topic: how-to
ms.reviewer: jswymer
ms.search.keywords: VAT, VAT rate, posting, tax, value-added tax
ms.search.form: 550
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Manage VAT rate changes in Business Central

VAT rates can change depending on local legislation. Any change in VAT impacts your data in [!INCLUDE[prod_short](includes/prod_short.md)] whether the VAT rate is lowered, raised, or removed. VAT is connected to many entities in [!INCLUDE[prod_short](includes/prod_short.md)], such as customers, vendors, items, resources, item charges, and general ledger accounts. Changes in VAT rates usually happen at a specific date. Before that date, you should change your VAT setup, posting groups, and so on, so that new sales orders and purchase orders use the new VAT rate.

## Change VAT rates

A good approach to managing a VAT rate change is to fully post and close open orders and other documents before the date of the rate change. Posting and closing helps ensure that the orders and documents aren't affected. This approach is the cleanest because it lets you start new orders and documents with the new VAT rate.

The following approach is suggested to manage a VAT rate change:

1. Post and close open orders, journals, and other documents fully before the switch date. However, you can wait until afterward as long as you don't add new lines and you ensure the effective date is before the switch date.  
1. Create the new VAT setup.
1. Make the VAT switch on the relevant entities, such as customers, vendors, and items.
1. On the VAT rate switch date, create new documents that use the new rate.

## Use the VAT rate change tool

The VAT Rate Change tool can help you convert VAT rates on master data, journals, and orders. The tool is useful if you want to convert VAT on master data more easily or if you have orders that you can't close before the switch date. However, there are a few restrictions and limitations.

## Understand the VAT rate conversion process and limitations

The VAT Rate Change tool converts VAT rates for master data, journals, and orders in different ways. The new general product posting group or VAT product posting group updates the selected master data and journals. If an order was fully or partially shipped or received, the shipped or received items keep the current general product posting group or VAT product posting group. A new order line is created for any outstanding quantity and updated with the new posting groups. Also, item charge assignments, configuration templates for items, reservations, and item tracking information are updated accordingly.

On order lines, the unit price updates for all lines of the type Item and Resource, if you're using prices including VAT for the item. For other line types, you can decide whether to update the unit price.

There are a few things that the tool doesn't convert:

* Sales or purchase invoice lines that refer to posted shipments or receipts. These lines keep the current VAT rate.
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

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Rate Change Setup**, and then choose the related link.  
1. On the **Master Data**, **Journals**, and **Documents** FastTabs, choose a posting group value from the option list for needed fields. For each group, choose whether to convert VAT product posting groups or general product posting groups, or convert both values if they're available for the master data. For some areas, you can also filter to convert only a subset of values, for example, G/L accounts.
1. On the **Unit Price Incl. VAT** FastTab, choose the order line types for which you want to update unit prices. For prices that include VAT, unit prices on lines of type **Item** and **Resource** always update when the VAT percentage changes.

### To set up product posting group conversion

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Rate Change Setup**, and then choose the related link.  
1. On the **VAT Rate Change Setup** page, choose either the **VAT Prod. Posting Group Conv.** or **Gen. Prod. Posting Group Conv.** action.
1. In the **From Code** field, enter the current posting group.
1. In the **To Code** field, enter the new posting group.

### To perform VAT rate change conversion

You use the VAT rate change tool to manage changes in the standard rate of VAT. You perform VAT and general posting group conversions to change VAT rates and maintain accurate VAT reporting. Depending on your setup, the following changes happen:  

* VAT and general posting groups are converted.  
* Changes are implemented in general ledger accounts, items, resources, open documents, and journal lines.

> [!IMPORTANT]  
> Before you perform VAT rate change conversion, you can test the conversion. To do so, follow these steps, but make sure to clear the **Perform Conversion** and **VAT Rate Change Tool Completed** checkboxes. During test conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is cleared and the **Converted Date** field in the **VAT Rate Change Log Entry** table is blank. After the conversion completes, choose **VAT Rate Change Log Entries** to view the results of the test conversion. Verify each entry before you perform the conversion. In particular, verify transactions that use an old VAT rate.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Rate Change**, and then choose the **VAT Rate Change Setup** link.  
1. Verify that you already set up the VAT product posting group conversion or general product posting group conversion.
1. Choose the **Perform Conversion** checkbox.
1. Clear the **VAT Rate Change Tool Completed** checkbox. The checkbox is automatically selected when the conversion is completed.
1. Choose the **Convert** action.
1. After the conversion is complete, choose the **VAT Rate Change Log Entries** action to view the results of the conversion.

> [!IMPORTANT]  
> For successfully converted entries, **Converted** is selected and **Converted Date** shows the work date used for the conversion.

## Related information

[Set Up Value-Added Tax](finance-setup-vat.md)  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Local functionality in Business Central](about-localization.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
