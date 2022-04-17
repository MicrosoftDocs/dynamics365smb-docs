---
title: 
description: 
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
manager: 
---

# Getting Started

## Prerequisites
### For Shopify
- Shopify account and online store.

  To create a new Shopify Account or sign up for a free 14-day trial navigate to https://www.shopify.com/. For more information on how to create and personalize your online store, see https://help.shopify.com/.
  
- Addional sales channel, like Shopify POS, are supported.

#### Recomended settings
- Disable **Automatically archive the order** in the **Order Processing** section of the [**Checkout**](https://www.shopify.com/admin/settings/checkout) settings in your **Shopify admin**.

### For [!INCLUDE[prod_short](../includes/prod_short.md)]
- **Connect to Shopify for [!INCLUDE[prod_short](../includes/prod_short.md)]** extension is installed

  Extension is pre-installed for all new signups and trials. If you need to install extensions from Market place, see [Installing and Uninstalling Extensions](../ui-extensions-install-uninstall.md#install). Follow steps below if you don't have [!INCLUDE[prod_short](../includes/prod_short.md)].

## Install **Dynamics 365 Business Central** app to your Shopify online store
For existing [!INCLUDE[prod_short](../includes/prod_short.md)] this is optional step and can be skipped.
1. Find [Dynamics 365 Business Central](https://fwlink?=TDB) app on the [Shopify AppStore](https://apps.shopify.com/)
2. Choose **Add App** button. Login into your Shopify account if prompted. Select online shop if you have more than one.
3. Review privacy and permissions details and choose **Install App** button.
  You can find and open installed **Dynamics 365 Business Central** app in the **Apps** section on the sidebar of **Shopify admin**.
4. Choose **Sign up now** to start [!INCLUDE[prod_short](../includes/prod_short.md)] trial or **Sign in** if you already using [!INCLUDE[prod_short](../includes/prod_short.md)]. You'll be redirected to your [!INCLUDE[prod_short](../includes/prod_short.md)] at https://businesscentral.dynamics.com/. 
5. Next steps should be done in [!INCLUDE[prod_short](../includes/prod_short.md)].

## Connecting [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify online store
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Choose the **New** action.  
3. Fill in the **Code** field.  
4. Fill in **Shopify URL** field with url to online shop your want to connect to.
5. Choose the **Request Access** action.
6. If prompted login into your Shopify account, review privacy and permissions details and choose **Install App** button.
 
Repeat steps 2-6 for all online shops you want to connect.

### Next steps
Now your online shop is connected to [!INCLUDE[prod_short](../includes/prod_short.md)]. Now need to define how and what you want to syncronize.
- Synchronize items. For more information, see [Synchronize Items](synchronize-items.md)
- Synchronize customers. For more information, see [Synchronize Customers.md](synchronize-customers.md)
- Synchronize orders. For more information, see [TBD]
- Other settins. For more information, see [TBD]

