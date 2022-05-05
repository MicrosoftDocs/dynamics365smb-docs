---
title: Getting started with connector to Shopify
description: First steps when configuring connection between Business Central and Shopify
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
manager: 
---

# Getting Started

In order to use Shopify with Business Central, you need to fullfil some requirements. This page will serve as a guide to complete the integration of your Shopify store with Business Central.

## Prerequisites for Shopify

You need to have the following:

- Shopify account
- Shopify store

To create a new Shopify Account or sign up for a free 14-day trial navigate to <https://www.shopify.com/>. For more information on how to create and personalize your online store, see <https://help.shopify.com/>.
  
- Additional sales channels are supported for e.g. Shopify POS.

### Recommended settings

- Deactivate **Automatically archive the order** in the **Order Processing** section of the [**Checkout**](https://www.shopify.com/admin/settings/checkout) settings in your **Shopify admin**.
- Enable **Automatically fulfill only the gift cards of the order** in the **Order Processing** section of the [**Checkout**](https://www.shopify.com/admin/settings/checkout) settings in your **Shopify admin**.

### Settings for trial and demo scenarios

- Activate *(for testing) Bogus Gateway* as test payment provider in the [**Payments**](https://www.shopify.com/admin/settings/payments) settings in your **Shopify admin**.
- Add Gift Card into Products - Gift cards, if you plan to demonstrate Gift card scenario.
- Consider selecting *Accounts are optional* in the **Customer accounts** section of the Checkout setting.
- Consider selecting *Company name* - *Optional* in the **Customer information** section of the Checkout setting.
- Enable **Show tipping options at checkout** in the **Tipping** section of the Checkout settings if you plan to demonstrate Tipping scenario.

## Prerequisites for [!INCLUDE[prod_short](../includes/prod_short.md)]

- Make sure **Connect to Shopify for [!INCLUDE[prod_short](../includes/prod_short.md)]** extension is installed

Extension is pre-installed for all new sign ups and trials. If you need to install extensions from Market place, visit [Installing and Uninstalling Extensions](../ui-extensions-install-uninstall.md#installing-an-extension). Follow the steps listed below if you don't have [!INCLUDE[prod_short](../includes/prod_short.md)].

## Installing **Dynamics 365 Business Central** app to your Shopify online store

For existing [!INCLUDE[prod_short](../includes/prod_short.md)] this step is optional and can be skipped.

1. Find [Dynamics 365 Business Central](https://fwlink?=TDB) app on the [Shopify AppStore](https://apps.shopify.com/)
2. Choose **Add App** button. Login into your Shopify account if prompted. Select online shop if you have more than one.
3. After reviewing privacy and permissions, choose **Install App** button.
  You can find and open installed **Dynamics 365 Business Central** app in the **Apps** section on the sidebar of **Shopify admin**.
4. Choose **Sign up now** to start [!INCLUDE[prod_short](../includes/prod_short.md)] trial or **Sign in** if you already have [!INCLUDE[prod_short](../includes/prod_short.md)]. You'll be redirected to your [!INCLUDE[prod_short](../includes/prod_short.md)] at <https://businesscentral.dynamics.com/>.
5. Next steps should be done in [!INCLUDE[prod_short](../includes/prod_short.md)].

## Connecting [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify online store

1. Go to search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop** and choose the related link.
2. Choose the **New** action.  
3. Fill in the **Code** field.  
4. Type in the URL of your desired online shop in **Shopify URL** field.
5. Choose the **Request Access** action.
6. If prompted, login into your Shopify account. After reviewing privacy and permissions, choose **Install App** button.

Repeat steps 2-6 for all online shops you want to connect to.

### Next steps

Now your online shop is connected to [!INCLUDE[prod_short](../includes/prod_short.md)]. In next steps you will define how and what to synchronize.

- [Synchronize Items](synchronize-items.md)
- [Synchronize Customers](synchronize-customers.md)
- [Synchronize Orders](synchronize-orders.md)
