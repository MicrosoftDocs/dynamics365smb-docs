---
title: Use Multiple Customer VAT Registration Numbers
description: Set up alternative customer VAT registration numbers in Business Central and apply the correct VAT details when shipping to another country or region.
author: altotovi
ms.topic: how-to
ms.search.keywords: VAT, multiple, alternative, customer, tax, value-added tax
ms.search.form: 212, 301
ms.date: 11/11/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Use multiple customer VAT registration numbers

For businesses with warehouses in multiple EU countries, managing VAT (Value Added Tax) can be challenging, as each warehouse location requires a different VAT number to comply with the specific regulations of each country. This article provides information about this requirement and explains the functionality for multiple value-added tax (VAT) registration numbers. This functionality allows users to set up tax registration numbers for their customers in different countries/regions.  

> [!NOTE]
> The *Multiple VAT numbers for customers* functionality is available only from Business Central 2024 release wave 2 (version 25).

## How to set up the alternative VAT registration numbers  

To set up the alternative VAT registration numbers for different countries/regions, follow these steps: 

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Alternative Customer VAT Registration**, and then select the related link. 
1. Enter the customer in **Customer No.** and the country/region for this VAT registration in **VAT Country/Region Code**.
1. Enter the VAT number in **VAT Registration No.**. Use the format required for that country/region.
1. If you want to use different VAT or general posting groups, enter them in **VAT Bus. Posting Group** and **Gen. Bus. Posting Group**.
1. Close the page.

To create an alternative address for your customer, follow these steps:  

1. Open the **Customer** card for the customer you want to add a ship-to address for.
1. Select **Customer**, and choose the **Ship-to Addresses** action.
1. On the **Ship-to Address List** page, select **New**.
1. Fill in the information about your customer's ship-to destination.
1. Choose the **Country/Region Code**.
1. If the country/region differs from the customer's country/region and no alternative VAT registration is set up for it, choose **Add** in the notification. On the **Alternative Customer VAT Registration** page, **Customer No.** and **VAT Country/Region Code** are filled in. Enter the remaining setup.

> [!NOTE]
> The notification appears only if **Suggest an alternative customer VAT registration from ship-to address** is enabled on the **My Notifications** page.

## Work with the sales documents   

You can create new [sales invoice](sales-how-invoice-sales.md) or [sales order](sales-how-sell-products.md) in [!INCLUDE[prod_short](includes/prod_short.md)]. If you need to use a ship-to address that differs from the customer's address and is located in a different country, follow the steps:  

### Alternate shipping address  

1. Expand the **Shipping and Billing** FastTab.   
1. In **Ship-to**, choose **Alternate Shipping Address**.
1. On the **Ship-to Address List** page, choose an address in a different country/region.
1. If the **Confirm Alternative Customer VAT Registration** dialog appears, review the changed fields and select **OK**.
1. Check the VAT-related fields on the **Invoice Details** FastTab. The values come from the matching alternative customer VAT registration.
1. Post the document.

> [!NOTE]
> The confirmation dialog appears only if **Confirm an alternative customer VAT registration.** is enabled on the **My Notifications** page. If you select **Don't show again**, enable that notification again to restore the dialog.

### Custom address  

In case you don't have the ship-to address configured but still want to use a different address for shipping, you can use this option.  

1. Expand the **Shipping and Billing** FastTab.   
1. In **Ship-to**, choose **Custom Address**.
1. Change **Country/Region** to match the **VAT Country/Region Code** of an alternative customer VAT registration.
1. If the **Confirm Alternative Customer VAT Registration** dialog appears, review the changed fields and select **OK**.
1. Check the updated VAT-related fields on the **Invoice Details** FastTab.

### Work with no shipment 

If there's no shipment as a process, you still can leverage the **Alternative Customer VAT Registration** setup.

In the sales order or invoice, find **VAT Country/Region Code** on the **Invoice Details** FastTab and specify a value that matches an alternative customer VAT registration. If the confirmation notification is enabled, the same confirmation dialog appears.

In this situation, you can post a sales invoice with the proper **VAT Registration No.** for your customer even if you don't ship items with this document. 

### Work with the sales credit memo  

When you create a corrective sales credit memo from a posted sales invoice, it takes the VAT details from that invoice. If the invoice used an alternative customer VAT registration, you don't need to select that registration again on the corrective credit memo.

## Related information

[VAT Management Overview](finance-manage-vat.md)    
[Set Up Value-Added Tax](finance-setup-vat.md)    
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)    
[Report VAT to a Tax Authority](finance-how-report-vat.md)    
[Local functionality in Business Central](about-localization.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
