---
title: Managing VAT Rate changes
description: Learn how to use the VAT Rate Change tool for Dynamics 365 Business Central for changing VAT rates based on local legislation.
author: andregu

ms.topic: conceptual
ms.reviewer: bholtorf
ms.workload: na
ms.search.keywords: VAT, VAT rate, posting, tax, value-added tax
ms.search.form: 550, 
ms.date: 06/16/2021
ms.author: andregu

---

# Managing VAT Rate Changes

VAT rates can change depending on local legislation. Any change in VAT impacts your data in [!INCLUDE[prod_short](includes/prod_short.md)] whether or not the VAT rate is lowered, raised, or removed. VAT is connected to many entities in [!INCLUDE[prod_short](includes/prod_short.md)], such as customers, vendors, items, resources, item charges, and general ledger accounts. Changes in VAT rates usually happen at a specific date, from which point you will need to have changed the VAT setup, posting groups etc. to make sure new sales orders and purchase orders are created with the new VAT rate.

## Changing VAT rates

The optimal approach to manage a VAT rate change is to fully post and close open orders and other documents before the VAT rate switch date, to make sure these are not impacted by the change. This is the cleanest approach that allows you to start up new orders and documents with the new VAT rate.

The following approach is suggested to manage a VAT rate change

1. Fully post and close open orders, journals and other documents before the switch date. You can wait to after the switch date as long as you do not add new lines and make sure the effective date will be prior the switch date.  
2. Create the new VAT setup.  
3. Make the VAT switch on entities (relevant customers, vendors, items, and so on).  
4. At the VAT rate switch date you create new documents that will use the new rate.  


> [!NOTE]  
> We are currently updating the VAT Rate Change tool. The functionality mentioned below may not match the functionality in your environment. The update will take place before July 1st 2020 and will not be a regular monthly update. Instead, all environments will be updated automatically (hotfix). When this update is complete, this message will no longer appear.  

## The VAT Rate Change tool

The VAT Rate Change tool can assist with conversion of VAT Rates on master data, journals and orders, to some extent. This is useful if you want to convert VAT on master data more easily or if you have orders that you cannot close before the switch date and will be processed over a longer period of time, crossing the VAT rate switch date. There are certain restrictions and limitations in the VAT Rate Change tool that applies.

## Understanding the VAT rate conversion process and limitations

The VAT Rate Change tool performs VAT rate conversions for master data, journals, and orders in different ways. The selected master data and journals will be updated by the new general product posting group or VAT product post group. If an order has been fully or partially shipped, the shipped items will keep the current general product posting group or VAT product posting group. A new order line will be created for the unshipped items and updated to align current and new VAT or general product posting groups. In addition, item charge assignments, configuration templates for items, reservations, and item tracking information will be updated accordingly. 

On order lines, the unit price will be updated for all lines of type Item and Resource, if using prices incl. VAT for the item. For other line types it is possible to decide whether or not the unit price should be updated.

There are a few things that the tool does not convert:

* Sales or purchase orders and invoices where shipments have been posted. These documents are posted using the current VAT rate.  
* Documents that have posted prepayment invoices. For example, you have made or received prepayments on invoices that have not been completed before you use the VAT rate change tool. In this case, there will be a difference between the VAT that is due and the VAT that has been paid in the prepayments when the invoice is completed. The VAT rate change tool will skip these documents and you will have to manually update them.  
* Sales or purchase orders with warehouse integration if they are partially shipped or received.  
* Drop shipments.
* Special orders. 
* Assembly orders.
* Service contracts.  
* Credit memos.
* Return orders.
* Prices on Items (master data)
* Prices on Sales Prices (master data)
* Business Posting Groups on Customers and Vendors.

### To prepare VAT rate change conversions

Before you set up the VAT rate change tool, you must make the following preparations.

* If you have transactions that use different rates, then they must be separated into different groups either by creating new general ledger accounts for each rate or by using data filters to group transactions according to rate.  
* If you create new general ledger accounts, then you must create new general posting groups.  
* To reduce the number of documents that get converted, post as many documents as possible and reduce unposted documents to a minimum.  
* Back up data.

### To set up the VAT rate change tool

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change Setup**, and then choose the related link.  
2. On the **Master Data**, **Journals**, and **Documents** FastTabs, choose a posting group value from the option list for needed fields. For each group you can choose whether to convert VAT product posting groups or general product posting groups, or convert both values if they are available in the master data item. For some areas you can also set a filter to convert only a subset of values, for example, G/L accounts. 
3. On the **Prices Incl. VAT** FastTab, choose which line types on orders for which you want to update unit prices. Unit prices on lines of type Item and Resource will always be updated.

### To set up product posting group conversion

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change Setup**, and then choose the related link.  
2. On the **VAT Rate Change Setup** page, choose either the **VAT Prod. Posting Group Conv.** or **Gen Prod. Posting Group Conv.** action.  
3. In the **From Code** field, enter the current posting group.  
4. In the **To Code** field, enter the new posting group.  

### To perform VAT rate change conversion

You use the VAT rate change tool to manage changes in the standard rate of VAT. You perform VAT and general posting group conversions to change VAT rates and maintain accurate VAT reporting. Depending on your setup, the following changes are made:  

* VAT and general posting groups are converted.  
* Changes are implemented in general ledger accounts, customers, vendors, open documents, journal lines, and so on.  

> [!IMPORTANT]  
> Before you perform VAT rate change conversion, you can test the conversion. To do so, follow the steps below, but make sure to clear the **Perform Conversion** and **VAT Rate Change Tool Completed** check boxes. During test conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is cleared and the **Converted Date** field in the **VAT Rate Change Log Entry** table is blank. After the conversion is complete, choose **VAT Rate Change Log Entries** to view the results of the test conversion. Verify each entry before you perform the conversion. In particular, verify transactions that use an old VAT rate.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change**, and then choose the **VAT Rate Change Setup** link.  
2. Verify that you have already set up the VAT product posting group conversion or general product posting group conversion.  
3. Choose the **Perform Conversion** check box.  

    > [!IMPORTANT]  
    >  Clear the **VAT Rate Change Tool Completed** check box. The check box is automatically selected when the VAT rate change conversion is completed.  

4. Choose the **Convert** action.  
5. After the conversion is complete, choose the **VAT Rate Change Log Entries** action to view the results of the conversion.  

> [!IMPORTANT]  
> After the conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is chosen and the **Converted Date** field in the **VAT Rate Change Log Entry** table displays the conversion date.  

## See also

[Set Up Value-Added Tax](finance-setup-vat.md)  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Local functionality in Business Central](about-localization.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
