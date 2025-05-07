---
title: Enable Customer Payments with Payment Services
description: Make it easier for customers to pay their invoices by enabling customer payments through payment services.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: online payment
ms.search.forms: 1060, 1061, 1062
ms.date: 06/25/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Enable Customer Payments Through Payment Services

As an alternative to collecting payments through bank transfer or credit cards, your customers can pay you through their account with payment services, such as PayPal or WorldPay.  

After you enable a payment service in [!INCLUDE[prod_short](includes/prod_short.md)], a link to the service is available on sales documents that you send by email to your customers. Customers can use the link to go to the payment service and pay the bill, directly from the sales document. If you don't want to include the link, for example, if a customer will pay with cash, you can remove the payment service from the invoice before posting.  

The PayPal Payments Standard and WorldPay Payments Standard extensions are installed in [!INCLUDE[prod_short](includes/prod_short.md)], and are ready for you to enable.  

> [!CAUTION]
> The WorldPay Payments Standard extension will be deprecated. The code is market as obsolete starting in 2023 release wave 2. The app will be active for the next three major releases and then it will be removed.   

## To enable a payment service in [!INCLUDE[prod_short](includes/prod_short.md)]

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Services**, and then choose the related link.  
2. On the **Payment Services** page, choose the **New** action.  
3. Select the payment service, and then close the page.  
4. On the **Payment Services** page, choose the **Setup** action.  
5. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
6. Close the page.  

## To select a payment service on a sales invoice

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.  
2. Open the sales invoice that you want to pay by using the payment service.  
3. In the **Payment Service** field, choose the payment service.  

    > [!NOTE]  
    > The **Payment Service** field is available only if you've enabled the payment service.  

## Related information

[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
