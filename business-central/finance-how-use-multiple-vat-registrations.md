---
title: Multiple VAT Registration Numbers
description: Learn about the functionality for multiple (alternative) value-added tax (VAT) registration numbers.
author: altotovi
ms.topic: conceptual
ms.reviewer: 
ms.search.keywords: VAT, multiple, alternative, customer, tax, value-added tax
ms.search.form: 212, 301, 
ms.date: 08/20/2024
ms.author: altotovi

ms.service: dynamics-365-business-central
---

# Multiple VAT Registration Numbers Numbers  

For businesse with warehouses in multiple EU countries, managing VAT (Value Added Tax) can be particularly challenging, as each warehouse location requires a different VAT number to comply with the specific regulations of each country. This article provides information about this requirements and it explain the functionality for multiple value-added tax (VAT) registration numbers. This functionality lets users set up the tax registration numbers for its customers in different countries/regions.  

> [!NOTE]
> The _Multiple VAT numbers for customers_ functionality is available only from Business Central 2024 release wave 2 (version 25).

## How to setup the alternative VAT registration numbers  

To set up the alternative VAT registration numbers for different countries/regions, follow the steps: 

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Alternative Customer VAT Registration**, and then select the related link. 
2. Add the customer in the **Customer No** field and country/region related to this VAT registration in the **VAT Country/Region Code**.  
3. You have to add the VAT number in the **VAT Registration No.** field. Keep in mind you need to use proper format for the **Country/Region Code** you used. 
4. If you want to use different VAT or general posting groups, you can alternavely add them to the setup in the **VAT Bus. Posting Group** and **Gen. Bus. Posting Group** fields. 
5. Close the page.   

To create alternative address to your customer, follow the steps:  

1. Open the **Customer** card for the customer you want to add new **Ship-to Address**. 
2. Select **Customer** and click to the **Ship-to Addresses** action.   
3. The **Ship-to Address List** page will be opened and you need to click **New**. 
4. Fill in information about your customer ship-to destination.  
5. Choose the proper **Country/Region Code**.   
6. If you already configured new **VAT Registration No.** in the **Alternative Customer VAT Registration** for this country or region, nothing will happen. 
7. But if you didn't previously configured the **VAT Registration No.** in the **Alternative Customer VAT Registration** for this country or region, the following notification will appear: **Click Add if you want to insert the Alternative VAT Registration for this Ship-To Country Code.** 
8. This notification will appear as a warning you should add new VAT number. To do so, you need to click the **Add** action in the notification and the **Alternative Customer VAT Registration** page will be opened. 
9. This page will already have populated your **Customer No.** and the **VAT Country/Region Code**. So, you just need to add set up you want to use. 

## Working with the sales documents   

You can create new [sales invoice](sales-how-invoice-sales.md) or [sales order](sales-how-sell-products.md) in Business Central. If you need to use a ship-to address that differs from the customer's address and is located in a different country, follow these steps:  

### Alternate shipping address  

1. Expand the **Shipping and Billing** FastTab.   
2. In the **Ship-to** field choose the **Alternate Shipping Address** option. 
3. The **Ship-to Address List** page with available alternate addresses will appear. 
4. Choose one of the ddresses with different **Country/Region Code**. 
5. The **Confirm Alternative Customer VAT Registration** dialog page will appear with a list of fields that have been changed due to setup in the **Alternative Customer VAT Registration** you already made. 
6. Click **OK** to confirm.   

> [!NOTE]
> If you do not want to confirm such a choice anymore, you can select the **Don't show again** field and in the future you will not see this type of notification about changes. But if you want to enable it again, you can do it enabling the **Confirm Alternative VAT Registration** field in the **VAT Setup**.  
   
7. Once you confirm, the values will be overwritten with the values from the **Alternative Customer VAT Registration** setup. You can check all the VAT related fields are under the **Invoice Details** FastTab.  
8. Post the document.  

### Custom address  

In a case you do not have the ship-to address configured but still want to use different addresse for shipping, you can use this option.  

1. Expand the **Shipping and Billing** FastTab.   
2. In the **Ship-to** field choose the **Custom Address** option.  
3. Change the country in **Country/Region** field.  
4. Once you change the country/region code to match the **VAT Country/Region Code** of the **Alternative Customer VAT Registration** you can see the **Confirm Alternative Customer VAT Registration** dialog page with a list of fields that have been changed. 
5. Business Central will also change all the VAT related fields are under the **Invoice Details** FastTab.  

### Working with no shipment 

If there is no shipment as a process, you still can leverage from the **Alternative Customer VAT Registration** setup.

In the sales order or invoice you can find the **VAT Country/Region Code** under the **Invoice Details** FastTab and specify the value that matches the **Alternative Customer VAT Registration** setup. And you should see the same confirmation dialog page as above. 

In this situation you can post sales invoice with the proper **VAT Registration No.** for your customer even if you do not ship items with this document. 

### Working with the sales credit memmo  

Once you post the invoice with a **Ship-to address** or **VAT Country/Region Code** that has different posting data, the corrective **Sales credit memo** takes the values from the **Posted sales invoice** header where these values are taken from the **Alternative customer VAT registration**, so no other actions required. 

## See Also

[VAT Management Overview](finance-manage-vat.md)
[Set Up Value-Added Tax](finance-setup-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Local functionality in Business Central](about-localization.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
