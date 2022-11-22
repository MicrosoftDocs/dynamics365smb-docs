---
title: Create and Set Up a Shopify Account
description: Learn how to get a Shopify account so you can demonstrate the workflow for integrating Shopify and Business Central.
ms.date: 06/21/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.reviewer: solsen
author: AndreiPanko
ms.author: andreipa
---

# Create and Set Up a Shopify Account

If you're considering whether to use Shopify as your e-Commerce solution and need a Shopify account to validate integrated workflow, you have the following options:

- Get a trial version. This is the typical starting point for end-users.  
- Create development stores. This approach is for partners who do recurring demos, trainings, and provide support.

## Trial (End-User)
Go to the [Shopify website](https://www.shopify.com) and use your email account for the administrator account to sign up for a free trial. Learn more about how to create and personalize your online store at the [Shopify Help Center](https://help.shopify.com/).

In the **Shopify Admin** of the created shop, apply the following **Settings**:

* Deactivate **Automatically archive the order** in the **Order Processing** section of the [**Checkout**](https://www.shopify.com/admin/settings/checkout) settings in your **Shopify admin**.
* Consider enabling the *Show login link in storefront and checkout* in the **Customer account settings** section of the checkout settings.
* Consider selecting the *Company name - Optional* option in the **Customer information** section of the checkout settings.
* Enable the **Show tipping options at checkout** option in the **Tipping** section of the checkout settings, if you plan to demonstrate tipping.
* Activate test payments. You have two options. Start by going to [**Payments**](https://www.shopify.com/admin/settings/payments) settings:  
  1. *(for testing) Bogus Gateway*. For more information, see [Activate Bogus Gateway for testing](https://help.shopify.com/en/manual/checkout-settings/test-orders#place-a-test-order-by-simulating-a-transaction).
  2. *Shopify payments* in test mode. For more information, see [Testing Shopify Payments](https://help.shopify.com/en/manual/payments/shopify-payments/testing-shopify-payments).

* Select a plan in the [**Plan**](https://www.shopify.com/admin/settings/plan) settings to be able test the checkout process.

> [!Important]  
> To avoid payments, remember to cancel your Shopify trial.

## Development store

Begin by joining the [Shopify Partner Program](https://help.shopify.com/partners/about). Afterward, use the **Partner Dashboard** to create the development store. Learn more at [Creating development stores](https://help.shopify.com/partners/dashboard/managing-stores/development-stores).

After creating the store, in the **Shopify Admin** of the created shop, apply the following **Settings**:

* Deactivate **Automatically archive the order** in the **Order Processing** section of the [**Checkout**](https://www.shopify.com/admin/settings/checkout) settings in your **Shopify admin**.
* Consider enabling the *Show login link in storefront and checkout* in the **Customer account settings** section of the checkout settings.
* Consider selecting the *Company name - Optional* option in the **Customer information** section of the checkout settings.
* If you plan to demonstrate tipping, enable the **Show tipping options at checkout** option in the **Tipping** section of the checkout settings.
* Activate test payments. You have two options. Start by navigating to [**Payments**](https://www.shopify.com/admin/settings/payments) settings:  
  1. *(for testing) Bogus Gateway*. For more information, see [Activate Bogus Gateway for testing](https://help.shopify.com/en/manual/checkout-settings/test-orders#place-a-test-order-by-simulating-a-transaction).
  2. *Shopify payments* in test mode. Learn more at [Testing Shopify Payments](https://help.shopify.com/en/manual/payments/shopify-payments/testing-shopify-payments).

## See Also

[Get Started with the Shopify Connector](get-started.md)
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)
