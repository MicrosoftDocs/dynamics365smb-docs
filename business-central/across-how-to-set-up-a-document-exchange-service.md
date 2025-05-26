---
title: How to Set Up a Document Exchange Service | Microsoft Docs
description: You use an external service provider to exchange electronic documents with your trading partners.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 06/11/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up a Document Exchange Service

As part of the Data Exchange Framework, you can exchange sales and purchase documents with your trading partners without extra steps, such as attaching the documents to email messages as PDF files. For example, when you're ready to invoice a customer, you can post the invoice and send it for payment as a file that your customer can receive in their business management application. For more information, see [Exchanging Data Electronically](across-data-exchange.md).

> [!NOTE]
> Setting up a document exchange service for Business Central on-premises requires some additional steps for authorization. For more information, see [Settings for Business Central On-Premises](#settings-for-business-central-on-premises).

## Connecting with Trading Partners

> [!IMPORTANT]
> Tradeshift integration is no longer supported in Business Central and is planned for deprecation. Instead, please try using the new E-Document functionality in Business Central https://aka.ms/bcedocuments.  

Exchanging electronic documents requires a connection to your trading partners. To make it easy to create a secure connection, [!INCLUDE[prod_short](includes/prod_short.md)] online is configured to use the Business Central Integration app. The app is available on the Tradeshift App Store, and all you and your business partners need to do is create a Tradeshift account and then enable the app. The Business Central Integration app comes in production and sandbox versions. For example, using the sandbox version is good for testing the document exchange. You can switch between production and sandbox versions by turning the **Sandbox** toggle on or off on the **Doc. Exch. Service Setup** page. When you do, the information on the **Service** FastTab is updated for you.

Alternatively, if you want to use another service, you must provide information to make the connection. For more information, see [To connect to a document exchange service](across-how-to-set-up-a-document-exchange-service.md#to-connect-to-a-document-exchange-service).

### To connect to the Business Central Integration app on Tradeshift

You can quickly create a Tradeshift account and get started with the Business Central Integration app from the **Doc. Exch. Service Setup** page. Choose either the **Activate App** link in the notification or the **App URL** field to go to the app in the Tradeshift app store. On the Login page for Tradeshift, either sign in or sign up.

> [!NOTE]
> After you sign in to your Tradeshift account, the site might not take you to the page where you activate the app. To do that, you can click the link on the **Doc. Exch. Service Setup** page in Business Central again to go directly to the app.

If you decide to stop using the Business Central Integration app, you should disable it in the Tradeshift app store. 

## To connect to a document exchange service

If you prefer to use another document exchange service, you must provide some information to connect to the service.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Document Exchange Service Setup**, and then choose the related link.  
2. Fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**User Agent**|Enter text that can be used to identify your company in document exchange processes.|  
    |**Enabled**|Specify whether the connection to the service is enabled.<br><br> **Note:**  When you enable the service at least two job queue entries are created to send and receive electronic documents. When you disable the service, the job queue entries are deleted.|  
    |**Sandbox**|Specify whether you are connecting to a sandbox version of the document exchange service.|
    |**Sign-up URL**|Specify the web page where you sign up for the document exchange service.|  
    |**App URL**|Choose the link to open the app store and turn the Business Central Integration app on or off.|
    |**Service URL**|Specify the address of the document exchange service, which will be called when you send and receive electronic documents.|  
    |**Sign-in URL**|Specify the URL for the page you use to sign in to the document exchange service. This is the page where you enter your company’s user name and password.|  
    
    > [!NOTE]  
    > Your sign in credentials are automatically encrypted. You cannot turn off encryption.

    > [!NOTE]
    > If you cannot connect to the document exchange service because of an authorization issue, it might be because [!INCLUDE[prod_short](includes/prod_short.md)] cannot automatically renew the access token. For example, this might occur if you have not used the service for some time. You can renew the token manually by using the **Renew Token** action.

### Settings for Business Central On-Premises

To connect Business Central on-premises, you must create an app on the Tradeshift App Store. When you do, use the redirect URL from the **Redirect URL** field on the **Document Exchange Service Setup** page. After you register your app, Tradeshift will provide a client ID and a client secret. In [!INCLUDE[prod_short](includes/prod_short.md)], enter those values on the **Authorization** FastTab on the **Document Exchange Service Setup** page.

If you prefer to store the app ID and secret in a different location, you can leave the Client ID and Client Secret fields blank and write an extension to fetch the ID and secret from the location. You can provide the secret at runtime by subscribing to the OnGetClientId and OnGetClientSecret events in codeunit 1410 "Doc. Exch. Service Mgt."

## Related information

[Setting Up Data Exchange](across-set-up-data-exchange.md)  
[Exchanging Data Electronically](across-data-exchange.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
