---
title: Multiple VAT registration numbers
description: Learn about the functionality for multiple (alternative) value-added tax (VAT) registration numbers.
author: altotovi
ms.topic: article
ms.reviewer: 
ms.search.keywords: VAT, multiple, alternative, customer, tax, value-added tax
ms.search.form: 212, 301, 
ms.date: 08/21/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Multiple VAT registration numbers 

For businesses with warehouses in multiple EU countries, managing VAT (Value Added Tax) can be challenging, as each warehouse location requires a different VAT number to comply with the specific regulations of each country. This article provides information about this requirement and explains the functionality for multiple value-added tax (VAT) registration numbers. This functionality allows users to set up tax registration numbers for their customers in different countries/regions.  

> [!NOTE]
> The *Multiple VAT numbers for customers* functionality is available only from Business Central 2024 release wave 2 (version 25).

## How to set up the alternative VAT registration numbers  

To set up the alternative VAT registration numbers for different countries/regions, follow these steps: 

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Alternative Customer VAT Registration**, and then select the related link. 
2. Add the customer in the **Customer No** field and the country/region related to this VAT registration in the **VAT Country/Region Code**.  
3. You must add the VAT number in the **VAT Registration No.** field. You must stick to the format when you use **Country/Region Code**. 
4. If you want to use different VAT or general posting groups, you can alternatively add them to the setup in the **VAT Bus. Posting Group** and **Gen. Bus. Posting Group** fields. 
5. Close the page.   

To create an alternative address for your customer, follow these steps:  

1. Open the **Customer** card for the customer you want to add new **Ship-to Address**. 
2. Select **Customer**, and choose the **Ship-to Addresses** action.   
3. The **Ship-to Address List** page opens, and select **New**. 
4. Fill in the information about your customer's ship-to destination.  
5. Choose the proper **Country/Region Code**.   
6. If you have already configured a new **VAT Registration No.** on the **Alternative Customer VAT Registration** for this country or region, nothing will happen. 
  - But if you didn't configure the **VAT Registration No.** previously on the **Alternative Customer VAT Registration** for this country or region, the following notification appears: **Click Add if you want to insert the Alternative VAT Registration for this Ship-To Country Code.**
  - Choose the **Add** action on the notification and the **Alternative Customer VAT Registration** page opens.
This page populates your **Customer No.** and the **VAT Country/Region Code**. So, you just need to add the setup that you want to use. 

## Work with the sales documents   

You can create new [sales invoice](sales-how-invoice-sales.md) or [sales order](sales-how-sell-products.md) in [!INCLUDE[prod_short](includes/prod_short.md)]. If you need to use a ship-to address that differs from the customer's address and is located in a different country, follow the steps:  

### Alternate shipping address  

1. Expand the **Shipping and Billing** FastTab.   
2. In the Ship-to field, choose the **Alternate Shipping Address** option. 
3. The **Ship-to Address List** page with available alternate addresses appears. 
4. Choose one of the addresses with a different **Country/Region Code**. 
5. The **Confirm Alternative Customer VAT Registration** dialog page appears with a list of fields that you have modified because of the **Alternative Customer VAT Registration** setup change. 
6. Select **OK** to confirm.   

> [!NOTE]
> If you don't want to confirm such a choice anymore, you can select the **Don't show again** field, and in the future you won't see this type of notification about changes. But if you want to enable it again, you can do it by enabling the **Confirm Alternative VAT Registration** field on the **VAT Setup**.  
   
7. Once you confirm, the values are overwritten with the values from the **Alternative Customer VAT Registration** setup. You can check all the VAT related fields that are under the **Invoice Details** FastTab.  
8. Post the document.  

### Custom address  

In case you don't have the ship-to address configured but still want to use a different address for shipping, you can use this option.  

1. Expand the **Shipping and Billing** FastTab.   
2. In the Ship-to field, choose the **Custom Address** option.  
3. Change the country in the **Country/Region** field.  
4. Once you change the country/region code to match the **VAT Country/Region Code** of the **Alternative Customer VAT Registration**, the **Confirm Alternative Customer VAT Registration** dialog page appears with a list of fields that have been changed. 
5. [!INCLUDE[prod_short](includes/prod_short.md)] will also change all the VAT related fields that are under the **Invoice Details** FastTab.  

### Work with no shipment 

If there's no shipment as a process, you still can leverage the **Alternative Customer VAT Registration** setup.

In the sales order or invoice, you can find the **VAT Country/Region Code** under the **Invoice Details** FastTab and specify the value that matches the **Alternative Customer VAT Registration** setup. You should see the same confirmation dialog page as above. 

In this situation, you can post a sales invoice with the proper **VAT Registration No.** for your customer even if you don't ship items with this document. 

### Work with the sales credit memo  

Once you post the invoice with a **Ship-to address** or **VAT Country/Region Code** that has different posting data, the corrective **Sales credit memo** takes the values from the **Posted sales invoice** header where these values are taken from the **Alternative customer VAT registration**, so no other actions required. 

## Related information

[VAT Management Overview](finance-manage-vat.md)    
[Set Up Value-Added Tax](finance-setup-vat.md)    
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)    
[Report VAT to a Tax Authority](finance-how-report-vat.md)    
[Local functionality in Business Central](about-localization.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
