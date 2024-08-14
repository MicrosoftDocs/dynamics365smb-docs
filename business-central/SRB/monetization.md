---
title: Pricing and Billing
hide_title: true
sidebar_label: Pricing and Billing
slug: /srb/monetization
---

# Pricing and billing
The use of **DYCE Subscription & Recurring Billing** is billed based on usage including a monthly fee. However, it is possible to test the full functionality for a limited time in advance. Please refer to the <a href="https://www.singhammer.com/en/solutions/subscription-recurring-billing/" title="DYCE Subscription & Recurring Billing">DYCE Subscription & Recurring Billing website</a> for current pricing. Regardless of this, the pricing is based on the claim to make it as fair as possible. This includes, above all, only charging for the actual benefit or added value.

Activation is done using the app called **DYCE Monetization**. This application manages usage data for all DYCE subscriptions. Once activated, it continuously determines both activation status and usage data (e.g., number of users or transaction volume).


## Benefit and added value
The benefits of **DYCE Subscription & Recurring Billing** are explained in [this](/docs/srb/purpose.md) part of the DYCE documentation. The value added calculation is therefore primarily hung on the use of the **Recurring Billing** page and the generation of the resulting contract invoices. Billing is therefore based on transaction volume per month.


## Download, installation and activation
**DYCE Subscription & Recurring Billing** is provided via <a href="https://appsource.microsoft.com/en-us/marketplace/apps?product=dynamics-365-business-central&search=dyce&page=1" title="Microsoft AppSource Business Central">Microsoft AppSource</a> for Microsoft Dynamics 365 Business Central. The <a href="https://www.singhammer.com/en/solutions/subscription-recurring-billing/" title="DYCE Subscription & Recurring Billing">DYCE Subscription & Recurring Billing website</a> also provides a corresponding <a href="https://appsource.microsoft.com/en-us/product/dynamics-365-business-central/PUBID.singhammeritconsultingag1598359803264%7CAID.1001%7CPAPPID.c12f11e8-b5a0-4450-a3f5-110b6cd46d1e?tab=Overview" title="DYCE Subscription & Recurring Billing on AppSource">link</a>. In addition, AppSource can also be accessed directly through Business Central. To do this, search for *Extension Marketplace* (*Alt+Q*) and then for ***DYCE Subscription & Recurring Billing***. <br/>
Before downloading, Microsoft will request information for registration. If AppSource is opened directly through Business Central, this data is pre-filled based on the client's **Company Information**. <br/>

In addition to registration in Microsoft AppSource, the app must be activated. The full range of functions is only available once activation has been completed. In the Role Center of **DYCE Subscription & Recurring Billing** and in the **Recurring Billing** page, a corresponding notification appears as long as the activation has not yet taken place. To activate an app click on *Activate now* in the notification banner:
1. Start the activation wizard by clicking *Next*.
2. Enter your company information and register at **<a href="https://www.singhammer.com/" title="Singhammer IT Consulting AG">Singhammer IT Consulting AG</a>**.
3. Select your Microsoft Dynamics 365 Business Central partner and payment method.
4. Accept end-user license agreement and finish activation.


## Allowing HTTP requests for DYCE Monetization
After installation, a prompt appears asking if *HttpClient requests* are allowed. This immediately affects the *Allow HttpClient Requests* setting in **DYCE Monetization**. For the correct working of the app, make sure that *Allow HttpClient Requests* is set to *YES* (see below). We use HTTP requests to log your usage. We do not save any other data. Follow the steps to check or re-enable this option:
1. Go to the Extension Management page by typing *extension* in the search (*Alt+Q*).
2. Search for **DYCE Monetization** by **Singhammer IT Consulting AG** and click on *View* action (either via the three dots or via action group *Manage*).
3. Allow HttpClient requests


## Activation of the functionality
The page **[Recurring Billing](/docs/srb/recurring-billing.md)** can basically be opened by all users and the data can be viewed (assuming appropriate [access rights](/docs/srb/setup/permissions.md)). The creation of a Billing Proposal and the resulting posting documents can also be done by any user. However, the app must be activated for the subsequent posting of the posting documents. Explicit activation of individual users is not necessary. Only the activation forms the basis for determining the [usage data](#usage-data) on which the billing is based.


## Usage data
With the installation of **DYCE Subscription & Recurring Billing** the additional app ***DYCE Monetization*** is installed (productive and sandbox environments). Once activated, it continuously determines both the activation status of the app and the totals of posted contract invoices and credits. The data from the production environment is aggregated on a monthly basis. In doing so, the amounts of the credit notes are subtracted from those of the invoices. This data forms the basis for [billing](#billing).

:::caution Uninstalling DYCE Monetization
After uninstalling the ***DYCE Monetization*** app, **DYCE Subscription & Recurring Billing** can still be used for a maximum of 24 hours. After that, the activation status will be reset. This means that the full functionality of the app is no longer available.
:::


## Billing
The aggregated usage data is billed based on the current prices per month. Depending on the business relation, this is done either directly or via your <a href="https://www.singhammer.com/en/become-a-partner/" title="Becoming a DYCE Partner">DYCE Partner</a>.