---
title: Using the PayPal Payments Standard Extension
description: This article describes how to use the standard extension to enable customers to make payments with PayPal.
author: brentholtorf
ms.author: bholtorf
ms.topic: concept-article
ms.search.keywords: app, add-in, manifest, customize
ms.search.form: 1070, 1071, 1073, 1074
ms.date: 07/09/2024
ms.custom: bap-template

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# The PayPal Payments Standard extension

The PayPal Payments Standard extension can help you increase your customer service levels by making it easier for your customers to pay their bills.

As an alternative to collecting payments through bank transfer or credit cards, customers can pay through their PayPal account. When you send a sales invoice by email, there's a PayPal link in the email body and in the attached PDF document. If the customer chooses the link, the service page for their PayPal account opens and shows the payment details. The customer can then pay the invoice as any other PayPal payment.

The PayPal Payments Standard service provides the following benefits:

* Customer payments arrive faster in your bank account.
* Customers have more ways to pay invoices.
* PayPal offers a trustworthy payment service, which customers prefer to entering credit card information on web sites.
* PayPal offers multiple ways of handling payments, including credit card processing, PayPal accounts, and other sources.
* The PayPal link can be added automatically to sales documents or manually by the user.
* The PayPal Payments Standard service doesn't involve monthly fees or setup fees.
* Because it's an extension, you can easily enable the PayPal Payment Standard service when and if your business requires it.  

To learn more about how to set up the extension, go to [Enable Customer Payment Through PayPal](sales-how-enable-payment-service-extensions.md).

## Register payments automatically for business accounts

[!INCLUDE [prod_short](includes/prod_short.md)] can register payments automatically if you have a Business Merchant account for the PayPal Commerce Platform. When your customers use the PayPal link to pay an invoice, [!INCLUDE [prod_short](includes/prod_short.md)] posts the entries and close the document.

To use this capability, on the **Payment Registration Setup** page in [!INCLUDE [prod_short](includes/prod_short.md)], turn on the **Register payments automatically** toggle and verify the accounts you'll use for the payments. If you decide that you don't want to register payments automatically, you can turn it off again.

> [!TIP]
> Developers can use sandbox accounts to test the setup. To do that, change the PayPal URL to **sandbox.paypal.com**. [!INCLUDE [prod_short](includes/prod_short.md)] uses the PayPals Instant Payment Notification (IPN) through notify_url.

## Related information

[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
