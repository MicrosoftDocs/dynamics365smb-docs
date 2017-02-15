---
title: 'How to: Enable Customer Payments Through PayPal| Microsoft Docs'
description: 'How to: Enable Customer Payments Through PayPal'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/18/2016
ms.author: sgroespe

---
# How to: Enable Customer Payments Through PayPal
As an alternative to collecting payments through bank transfer or credit cards, you can offer your customers to pay you through their PayPal account.

When a customer chooses the PayPal link on a sales invoice or sales order document, the service page for their PayPal account appears showing the payment details for the sale. The customer can then pay the invoice as any other PayPal payment.

To enable customer payments through PayPal, you must do the following:

1. Set up PayPal Payments Standard as a payment service in the **Payments Services** window.
2. Select PayPal Payments Standard in the **Payment Service** field on the sales document in question.

The PayPal Payments Standard service is installed as an extension to Financials and ready to be enabled. For more information, see [Customizing Dynamics 365 for Financials Using Extensions ](ui-extensions.md).

## To enable the PayPal Payments Standard service
1. In the top right corner, choose the **Search for Page or Report** icon, **Payment Services**, and then choose the related link.  
2. In the **Payment Services** window, choose the **New** action.
3. Select **PayPal Standard**, and then close the window.
4. In the **Payment Services** window, choose the **Setup** action.
5. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
   
    **Note**: Select the **Always Include on Documents** check box if the hyperlink for the PayPal payment service should always be visible on sales documents where payment through PayPal is enabled.
6. Close the window.

## To select PayPal Payments Standard on a sales invoice
1. On the Home page, choose **Sales Invoices**.
2. Open the sales invoice that you want to enable PayPal payments for.
3. In the **Payment Service** field, choose PayPal Payments Standard.

**Note**: The **Payment Service** field is only visible if the PayPal Payments Standard service is enabled.   

## See Also
[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Customizing Dynamics 365 for Financials Using Extensions](ui-extensions.md)  
[Working With Financials](ui-work-product.md)

