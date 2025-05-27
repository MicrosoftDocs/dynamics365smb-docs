---
title: Create and Set up a Shopify Account
description: Learn how to get a Shopify account so you can demonstrate the workflow for integrating Shopify and Business Central.
ms.date: 03/04/2024
ms.topic: article
ms.service: dynamics-365-business-central
ms.search.form: 30101, 30102 
ms.reviewer: bholtorf
author: brentholtorf
ms.author: bholtorf
---

# Create and Set up a Shopify Account



If you're considering whether to use Shopify as your e-Commerce solution and need a Shopify account to validate integrated workflow, you have the following options:

- Get a trial version. This is the typical starting point for end-users.  
- Create development stores. This approach is for partners who do recurring demos, trainings, and provide support.

## Trial (End-User)

Go to the [Shopify website](https://www.shopify.com) and use your email account for the administrator account to sign up for a free trial. Learn more about how to create and personalize your online store at the [Shopify Help Center](https://help.shopify.com/).

In the **Shopify Admin** of the created shop, apply the following **Settings**:

- Select a plan in the [**Plan**](https://www.shopify.com/admin/settings/plan) settings to be able test the checkout process.

- Consider enabling the *Show login link in the header of onilne store and checkout* in the **Accounts in online store and checkout** section of the [**Customer accounts**](https://www.shopify.com/admin/settings/customer_accounts) settings in your **Shopify admin**.
- Consider selecting *New customer account* in the  **Accounts in online store and checkout** section of the Customer accounts settings.
- Consider enabling *Self-serve returns* in the **New customer accounts** section of the Customer accounts settings.

- Activate test payments. You have two options. Start by going to [**Payments**](https://www.shopify.com/admin/settings/payments) settings:  
  1. *(for testing) Bogus Gateway*. For more information, see [Activate Bogus Gateway for testing](https://help.shopify.com/en/manual/checkout-settings/test-orders#place-a-test-order-by-simulating-a-transaction).
  2. *Shopify payments* in test mode. For more information, see [Testing Shopify Payments](https://help.shopify.com/en/manual/payments/shopify-payments/testing-shopify-payments).

- Deactivate **Automatically archive the order** in the **Order Processing** section of the [**General**](https://www.shopify.com/admin/settings/general) settings in your **Shopify admin**.
- Consider selecting the *Company name - Optional* option in the **Customer information** section of the checkout settings.
- Enable the **Show tipping options at checkout** option in the **Tipping** section of the checkout settings, if you plan to demonstrate tipping.

> [!Important]  
> To avoid payments, remember to cancel your Shopify trial.

## Development store

Begin by joining the [Shopify Partner Program](https://help.shopify.com/partners/about). Afterwards, use the **Partner Dashboard** to create the development store. Learn more at [Creating development stores](https://help.shopify.com/partners/dashboard/managing-stores/development-stores).

After creating the store, in the **Shopify Admin** of the created shop, apply the following **Settings**:

- Consider enabling the *Show login link in the header of onilne store and checkout* in the **Accounts in online store and checkout** section of the [**Customer accounts**](https://www.shopify.com/admin/settings/customer_accounts) settings in your **Shopify admin**.
- Consider selecting *New customer account* in the  **Accounts in online store and checkout** section of the Customer accounts settings.
- Consider enabling *Self-serve returns* in the **New customer accounts** section of the Customer accounts settings.
  
- Activate test payments. You have two options. Start by navigating to [**Payments**](https://www.shopify.com/admin/settings/payments) settings:  
  1. *(for testing) Bogus Gateway*. For more information, see [Activate Bogus Gateway for testing](https://help.shopify.com/en/manual/checkout-settings/test-orders#place-a-test-order-by-simulating-a-transaction).
  2. *Shopify payments* in test mode. Learn more at [Testing Shopify Payments](https://help.shopify.com/en/manual/payments/shopify-payments/testing-shopify-payments).
     
- Deactivate **Automatically archive the order** in the **Order Processing** section of the [**General**](https://www.shopify.com/admin/settings/general) settings in your **Shopify admin**.
- Consider selecting the *Company name - Optional* option in the **Customer information** section of the checkout settings.
- If you plan to demonstrate tipping, enable the **Show tipping options at checkout** option in the **Tipping** section of the checkout settings.


> [!Note]  
> Development stores are usually password protected. When you try to open a specific page in your online store from [!INCLUDE [prod_short](../includes/prod_short.md)], for example to go to a specific product or order, you'll need to enter your password. While you're testing, to avoid having to enter your password, sign in to your Shopify admin and open your store from there. You won't need to enter the store password until you close your browser or your session expires.  

## Related information

[Get Started with the Shopify Connector](get-started.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)
