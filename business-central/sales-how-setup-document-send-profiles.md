---
title: Set Up Preferred Methods of Sending Sales Documents | Microsoft Docs
description: Describes how to set up each customer's preferred method of sending sales documents, for example, email, PDF, electronic document, and so on.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: email, PDF, electronic document
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up Document Sending Profiles
You can set each customer up with a preferred method of sending sales documents, so that you do not have to select a sending option every time you choose the **Post and Send** action.

On the **Document Sending Profiles** page, you set up different sending profiles that you can select from in the **Document Sending Profile** field on a customer card. You can select the **Default** check box to specify that the document sending profile is the default profile for all customers, except for customers where the **Document Sending Profile** field is filled with another sending profile.

When you choose the **Post and Send** action on a sales document, the **Post and Send Confirmation** dialog box shows the sending profile used, either the one set up for the customer or the default for all customers. In the dialog box, you can change the sending profile for the sales document. For more information, see [Invoice Sales](sales-how-invoice-sales.md).
<br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=b0524480-cac0-4382-be29-954a70bbee34]

## To set up a document sending profile
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Document Sending Profiles**, and then choose the related link.
2. On the **Document Sending Profiles** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To specify a sending profile on a customer card
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the card of the customer who you want to set up a sending profile for.
3. In the **Document Sending Profile** field, select a profile that you have set up as described in the previous procedure.

## Related information
[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
