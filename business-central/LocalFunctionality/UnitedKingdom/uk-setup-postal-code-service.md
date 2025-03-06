---
title: Set Up GetAddress.io Extension [UK]
description: Learn how to configure the GetAddress.io extension in the British version of Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: getaddress.io, postcodes, extension
ms.search.form: 9142
ms.date: 02/21/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up the GetAddress.io UK Postcodes extension in the British version

This extension makes it easy to enter addresses in the United Kingdom (UK) for entities like customers, contacts, employees, vendors, bank accounts, and so on.

The GetAddress.io UK Postcodes extension uses the **getAddress** API to find addresses in postcodes in the UK. To use the extension, you need to get a plan and an API Key for the **getAddress** API. We help you do that when you set up the GetAddress.io UK Postcodes extension. Plans are based on use, or what are sometimes referred to as "calls." A call, in this case, is when [!INCLUDE[prod_short](../../includes/prod_short.md)] displays a list of addresses in a postcode. Depending on how often you add addresses, choose the plan that is best for you. If you just choose **Get API Key** you'll use the **Free** plan, which lets you add 20 addresses per day, and is valid for 30 days.

## Set up the GetAddress.io UK Postcodes extension

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Connections**, and then choose the related link.  
1. On the **Service Connections** page, choose **UK Postcode Service**.
1. On the **Postcode provider configuration** page, choose **Disabled**.
1. On the **Postal code service selection** page, choose **GetAddress.io**.
1. On the **GetAddress.io Config** page, choose **Get API Key** to open the **Plans** page on the website for the **getAddress** API.  

    > [!NOTE]  
    > You might need to allow pop-ups in your browser.

1. Purchase a plan, or just choose **Get API Key**, and then provide your email address.
1. Open the email from getAddress.io, and copy the API key. The key is under the **Your API Key** heading.
1. On the **GetAddress.io Config** page, paste the API key in the **API Key** field, and then choose **OK**.
1. On the **Service Connections** page, verify that the **Address Provider** field shows **GetAddress.io**. If it does, the service is enabled.

## See also

- [United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
- [The GetAddress.io UK Postcodes Extension](ui-extensions-getaddressio.md)  
- [Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
