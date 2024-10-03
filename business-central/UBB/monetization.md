---
title: Pricing and billing 
description: You can use pricing and billing in usage based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Pricing and billing

The use of **DYCE Usage Based Billing** is charged as a fixed monthly fee. However, in advance it is possible to test the full functionality for a limited time. Please refer to the <a href="https://www.singhammer.com/en/solutions/dyce-usage-based-billing/" title="DYCE Usage Based Billing">DYCE Usage Based Billing website</a> for current pricing. Regardless of this, the pricing is based on the claim to make it as fair as possible. This includes, above all, only charging for the actual benefit or added value. Since the app is an extension of **DYCE Subscription & Recurring Billing**, only the additional functionality should be the basis for billing.

Activation is done using the app called **DYCE Monetization**. This application manages usage data for all DYCE subscriptions. Once activated, it continuously determines both activation status and usage data (e.g., number of users or transaction volume).


## Download, installation and activation
**DYCE Usage Based Billing** is provided via <a href="https://appsource.microsoft.com/en-us/marketplace/apps?product=dynamics-365-business-central&search=dyce&page=1" title="Microsoft AppSource Business Central">Microsoft AppSource</a> for Microsoft Dynamics 365 Business Central. The <a href="https://www.singhammer.com/en/solutions/dyce-usage-based-billing/" title="DYCE Usage Based Billing">DYCE Usage Based Billing website</a> also provides a corresponding <a href="https://appsource.microsoft.com/en-us/product/dynamics-365-business-central/PUBID.singhammeritconsultingag1598359803264%7CAID.1005%7CPAPPID.882b7b1e-2a19-4e1a-988d-b8a7cd3254fd?tab=overview" title="DYCE Usage Based Billing on AppSource">link</a>. In addition, AppSource can also be accessed directly through Business Central. To do this, search for *Extension Marketplace* (*Alt+Q*) and then for ***DYCE Usage Based Billing***. <br/>
Before downloading, Microsoft will request information for registration. If AppSource is opened directly through Business Central, this data is pre-filled based on the client's **Company Information**. <br/>

In addition to registration in Microsoft AppSource, the app must be activated. The full range of functionality is only available once activation has been completed. In the Role Center of **DYCE Subscription & Recurring Billing** and in the pages **Usage Data Suppliers** and **Usage Data Imports** a corresponding notification appears as long as the activation has not yet taken place. To activate an app click on *Activate now* in the notification banner:
1. Start the activation wizard by clicking *Next*.
2. Enter your company information and register at **<a href="https://www.singhammer.com/" title="Singhammer IT Consulting AG">Singhammer IT Consulting AG</a>**.
3. Select your Microsoft Dynamics 365 Business Central partner and payment method.
4. Accept end-user license agreement and finish activation.


## Allowing HTTP requests for DYCE Monetization
After installation, a prompt appears asking if *HttpClient requests* are allowed. This immediately affects the *Allow HttpClient Requests* setting in **DYCE Monetization**. For the correct working of the app, make sure that *Allow HttpClient Requests* is set to *YES* (see below). We use HTTP requests to log your usage. We do not save any other data. Follow the steps to check or re-enable this option:
1. Go to the Extension Management page by typing *extension* in the search (*Alt+Q*).
2. Search for **DYCE Monetization** by **Singhammer IT Consulting AG** and click on *View* action (either via the three dots or via action group *Manage*).
3. Allow HttpClient requests.


## Activation of the functionality
The **[Usage Data Imports](/docs/ubb/processing-usage-data/imports-processing.md)** can basically be opened by all users and the data can be viewed (assuming appropriate [access rights](/ubb/setup/general.md#permissions)). Also the import of usage data and the creation of **Imported Lines** can be done by any user. However, the app must be activated for the subsequent creation of **Usage Data Billing**. An explicit activation of individual users is not necessary. Only the activation forms the basis for the determination of the [usage data](#usage-data) on which the billing is based.


## Usage data
With the installation of **DYCE Subscription & Recurring Billing** and **DYCE Usage Based Billing** the additional app ***DYCE Monetization*** is installed (productive and sandbox environments). Once activated, it continuously determines the activation status of the app. If this data reveals that the app is being used in a productive environment, it will be [billed](#billing) on a monthly basis.

:::caution Uninstalling DYCE Monetization
After uninstalling the app ***DYCE Monetization***, **DYCE Subscription & Recurring Billing** and **DYCE Usage Based Billing** can still be used for a maximum of 24 hours. After that, the activation status will be reset. This means that the full functionality of the apps is no longer available.
:::


## Billing
When using the app in a productive environment, usage is billed based on the current prices per month. Depending on the business relation, this will be done either directly or via your <a href="https://www.singhammer.com/en/become-a-partner/" title="Becoming a DYCE Partner">DYCE Partner</a>.