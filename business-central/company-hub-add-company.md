---
title: Add companies to your company hub
description: Learn how to add companies from other Business Central environments to your company hub so you can manage work across environments.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: accountant, accounting, company hub, add companies
ms.search.form: 1151, 1155, 1166, 1165
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Add companies to your company hub

With the company hub, you can access your work from across multiple companies from multiple [!INCLUDE [prod_short](includes/prod_short.md)] environments. You can add an environment and companies manually, if your companies don't show up automatically in the company hub.  

Right in the company hub landing page, you find the **Setup** menu, from where you can access the **Environment Links** page. Choose **New**, and then fill in the fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

> [!NOTE]
> You can connect the company hub to as many companies as you need. However, you can only connect the company hub to companies that are hosted in [!INCLUDE [prod_short](includes/prod_short.md)] online.

## Environment links

An environment link is a card where you specify the [!INCLUDE [prod_short](includes/prod_short.md)] environment that hosts one or more companies that you do work in. The data in the card for each environment is specified by you, and you can change it as needed. However, the **Environment Link** field is critical - this is how you can access each company in [!INCLUDE [prod_short](includes/prod_short.md)]. Use the **Test the connection** action in the ribbon to test that you entered the right link. The link that you must enter points at environment that hosts the company that you're adding, and it must include the Microsoft Entra ID, or the organization's domain name. For example, if they have specified a domain such as MyBusiness.com, then the link to their [!INCLUDE [prod_short](includes/prod_short.md)] is ```https://businesscentral.dynamics.com/mybusiness.com?redirectedfromsignup=1```. Otherwise, it looks something like this: ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```  

The link is used when you choose the company in the company hub.  

:::image type="content" source="media/company-hub-company-list-actions.png" alt-text="Actions for a company that is listed in the company hub.":::

> [!TIP]
> If you're working in the free trial version of [!INCLUDE [prod_short](includes/prod_short.md)], it's easy to add the companies in your tenant. You can find the environment link by copying the ID for Microsoft Entra from the **Troubleshooting** section of the Help & Support page. The environment name is probably the default value, PRODUCTION. Add this information to the **Environment Link** field, such as ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```, and then choose **Test the connection**. The evaluation company is added to the list.
>
> If you have moved to the thirty-day trial company, My Company, you can add that to the list by choosing the **Reload / Reload all Companies** action in the list.

## Load companies

When you have added your environments, your companies show up automatically. However, if you know that a new company has been added to an environment, you can choose the **Reload all companies** action to refresh the list. Use the same action to refresh data from across your companies.  

> [!TIP]
> In order to refresh the data in the company hub, you must have access to the data in the companies that the data comes from.

## Related information

[Manage Work across Multiple Companies in the Company Hub](company-hub.md)  
[Resources for Help and Support](product-help-and-support.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
