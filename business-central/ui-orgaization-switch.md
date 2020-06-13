---
title: Switching to Another Orgaization | Microsoft Docs
description: If you do work for multiple organizations, you can quickly switch between the environments and companies.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: environments, companies, tenants, organization
ms.date: 04/01/2020
ms.author: bholtorf

---

# Switching to Another Organization
People sometimes support more than one company and need to be able to easily switch from working in one company to another, even if the companies are not in the same environment. For example, a business might have subsidiary offices in multiple regions, so it has created a separate company for each office. Because some offices are closer to each other geographically than others, some offices are in the same environment while others are not. People like the CFO or the business's account need access to all of the companies.

Companies in [!INCLUDE[d365fin](includes/d365fin_md.md)] exist in what are referred to as *emvironments*. There are two types of environments, **Production** and **Sandbox**. In short, production environments contain live business data, and sandbox environments are used as a safe place to test things like new business processes or features. For more information, see [Types of environments](/dev-itpro/administration/tenant-admin-center-environments.md#types-of-environments).

If you have access to a company you have access to the environment it's in. If you have access to more than one company, and those companies are in different environments, when you sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)] you must specify the environment you want to work in. 

## Switch to Another Environment
When you are signed-in to [!INCLUDE[d365fin](includes/d365fin_md.md)], the environments that you can access are available on the Dynamics 365 Home page. You can open the Home page by choosing the **App Picker** icon in the upper left and choosing **Dynamics 365**. To go to your default company in that environment, click the tile.

The following image shows one production and one sandbox environment.

:::image type="content" source="media/app-picker-environments.png" alt-text="The Dynamics 365 Home page showing production and sandbox environments.":::

## Switch to Another Company
1. In the top right corner, choose the **Settings** icon ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then choose the **My Settings** action.
2. On the **My Settings** page, in the **Company** field, select the company that you want to use by default. 
3. Choose the **OK** button.

> [!TIP]
> A good way to go directly to your default company when you sign in, and avoid having to specify an environment, is to add the the URL to your list of favorites.

## See Also
[The Business Central Administration Center](/business-central/dev-itpro/administration/tenant-admin-center.md)