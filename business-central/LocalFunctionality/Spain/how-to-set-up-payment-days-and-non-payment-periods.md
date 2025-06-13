---
title: How to Set Up Payment Days and Non-Payment Periods
description: Learn how to set up payment days and non-payment periods to accurately calculate due dates for sales and purchase documents in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: set up payment days, set up non-payment periods, calculate due dates, payment days, non-payment periods, Spanish version
ms.date: 05/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up payment days and non-payment periods

Payment days and non-payment periods are used to calculate due dates. Due date calculation is used for sales and purchase documents.  

A payment day is a day on which invoices are paid.  

A non-payment period is a range of dates during which the company doesn't make payments. This functionality is often used for holiday periods.  

For sales and purchase invoices, the customer and vendor payment days and non-payment periods are taken into account.  

## Set up payment days and non-payment periods for a company  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
1. Expand the **Payments** FastTab.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payment Days Code**|Enter the payment day code.|  
    |**Non-Paymt. Periods Code**|Enter the non-payment periods code.|  

1. To open the **Payment Days** page, choose the **Payment Days** action.  
1. On the **Payment Days** page, in the **Payment Day** field, enter the payment day for the company.  
1. Choose the **OK** button.  
1. To open the **Non-Payment Periods** page, choose the **Non-Payment Periods** action.  
1. Enter information into the relevant fields.  
1. Choose the **OK** button.  

## Set up payment days for customers and vendors  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers** or enter **Vendors**, and then choose the related link.  
1. Select the required customer or vendor, and then choose the **Payment Days** action.  
1. On the **Payment Days** page, in the **Payment Day** field, enter the payment day for the customer or vendor.  
1. Choose the **OK** button.  

## Set up non-payment periods for customers and vendors  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers** or enter **Vendors**, and then choose the related link.  
1. Select the required customer or vendor, and then choose the **Non-Payment Periods** action.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**From Date**|Enter the starting date for the non-payment period.|  
    |**To Date**|Enter the ending date for the non-payment period.|  
    |**Description**|Enter a description.|  

1. Choose the **OK** button.  

## Related information

[Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
