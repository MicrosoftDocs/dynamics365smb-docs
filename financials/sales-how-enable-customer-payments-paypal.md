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
# How to: Enable Customer Payments Through PayPal and WorldPay
As an alternative to collecting payments through bank transfer or credit cards, your customers can pay you through payment services like PayPal or WorldPay. The PayPal Payments Standard and WorldPay payment services are installed as extensions to [!INCLUDE[d365fin](includes/d365fin_md.md)], and are ready to go. You just need to get an account from the service provider, and then enable the extension. For more information, see [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md).

After you enable a payment service, a link to the service displays on a sales invoice or sales order document, letting the customer make the payment directly from the document.

## To enable a payment service
1. In the top right corner, choose the **Search for Page or Report** icon, **Payment Services**, and then choose the related link.  
2. In the **Payment Services** window, choose the **New** action.
3. Select the payment service, and then close the window.
4. In the **Payment Services** window, choose the **Setup** action.
5. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. To display a link to the payment service on all sales documents, choose the **Always Include on Documents** check box.

## To manually choose a payment service on a sales document
1. On the Home page, choose **Sales Invoices**.
2. Open the sales invoice that you want to enable PayPal payments for.
3. In the **Payment Service** field, choose the payment service.

**Note**: The **Payment Service** field is only visible if the PayPal Payments Standard service is enabled.   

## See Also
[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
