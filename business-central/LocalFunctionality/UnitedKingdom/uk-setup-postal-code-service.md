---
title: 'Set Up the GetAddress.io UK Postcodes Extension | Microsoft Docs'
description: Describes the general functionality you use to interact with data in Business Central, such as entering values, sorting data, and changing views.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: getaddress.io, postcodes, extension
ms.date: 04/01/2020
ms.author: bholtorf

---
# Set Up the GetAddress.io UK Postcodes Extension
This extension makes it easy to enter addresses in the United Kingdom (UK) for entities like customers, contacts, employees, vendors, bank accounts, and so on.

The GetAddress.io UK Postcodes extension uses the getAddress API to find addresses in postcodes in the UK. To use the extension, you need to get a plan and an API Key for the getAddress API. We help you do that when you set up the GetAddress.io UK Postcodes extension. Plans are based on use, or what are sometimes referred to as "calls." A call, in this case, is when [!INCLUDE[d365fin](../../includes/d365fin_md.md)] displays a list of addresses in a postcode. Depending on how often you add addresses, choose the plan that is best for you. If you just choose **Get API Key** you will use the **Free** plan, which lets you add 20 addresses per day, and is valid for 30 days.

##To set up the GetAddress.io UK Postcodes extension
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Connections**, and then choose the related link.  
2. On the **Service Connections** page, choose **UK Postcode Service**.
3. On the **Postcode provider configuration** page, choose **Disabled**.
4. On the **Postal code service selection** page, choose **GetAddress.io**.
5. On the **GetAddress.io Config** page, choose **Get API Key** to open the **Plans** page on the website for the getAddress API.  

    > [!NOTE]  
    >   You might need to allow pop-ups in your browser.

6. Purchase a plan, or just choose **Get API Key**, and then provide your email address.
7. Open the email from getAddress.io, and copy the API key. The key is under the **Your API Key** heading.
8. On the **GetAddress.io Config** page, paste the API key in the **API Key** field, and then choose **OK**.
9. On the **Service Connections** page, verify that the **Address Provider** field shows **GetAddress.io**. If it does, the service is enabled.

## See Also
[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
[The GetAddress.io UK Postcodes Extension](../../ui-extensions-getaddressio.md)  
[Customizing [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Using Extensions](../../ui-extensions.md)  
[Working with [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)  
