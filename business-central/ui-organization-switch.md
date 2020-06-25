---
title: Switching to Another Company or Environment | Microsoft Docs
description: If you do work for multiple organizations, you can quickly switch between the environments and companies.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: environments, companies, tenants, organization
ms.date: 06/25/2020
ms.author: bholtorf

---

# Switching to Another Company or Environment

People sometimes support more than one company and need to easily switch from working in one company to another. For example, a business might have sales offices in multiple countries, so it has created a separate company for each office. Because some companies are geographically closer to each other than others, some are in the same environment while others are not. 

What's an environment? Companies in [!INCLUDE[d365fin](includes/d365fin_md.md)] exist in what are referred to as *environments*. There are two types of environments, **Production** and **Sandbox**. In short, production environments contain live business data, and sandbox environments are used as a safe place to test things like new business processes or features. For more information, see [Types of environments](dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#types-of-environments). If you have access to a company you have access to the environment it's in. If you have access to more than one company, and those companies are in different environments, when you sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)] you must specify the environment you want to work in. 

What's a company? Think of a company as a container that holds information about a legal entity. Using the example above, the business has a sales office in Seattle and another in New York, so it creates a company in [!INCLUDE[d365fin](includes/d365fin_md.md)] for each office so that it can manage operations for each office separately. For more information, see [Creating New Companies](about-new-company.md).

> [!TIP]
> If you often switch between companies it can be easy to lose track of where you are. To get around that you can add a badge that will display the company name, so you can quickly verify that you are in the right place. For more information, see [To display a company badge for quick access to company information](ui-change-basic-settings.md#to-display-a-company-badge-for-quick-access-to-company-information).

## Switch to Another Environment
When you are signed-in to [!INCLUDE[d365fin](includes/d365fin_md.md)], the environments that you can access are available on the Dynamics 365 Home page. You can open the page by choosing the **App Launcher** icon ![App Launcher](media/app-launcher-icon.png "The App Launcher provides access to more features") and choosing **Dynamics 365**. To go to your default company in that environment, choose the tile. There will be one tile for each type of environment. If you have more than one environment of a certain type, when you choose the tile you can choose the environment to access.

The following image shows tiles for accessing production and sandbox environments on the Dynamics 365 Home page.

:::image type="content" source="media/app-picker-environments.png" alt-text="The Dynamics 365 Home page showing production and sandbox environments.":::

## Switch to Another Company
When you are signed in to [!INCLUDE[d365fin](includes/d365fin_md.md)], you can quickly switch to another company. After you make the switch, the company you choose becomes your default company and will display the next time you sign in.

1. In the top right corner, choose the **Settings** icon ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then choose the **My Settings** action.

    > [!TIP]
    > You can also use the Alt+T keyboard shortcut to quickly open the My Settings page.

2. On the **My Settings** page, in the **Company** field, select the company. 
3. Choose the **OK** button.

> [!TIP]
> A good way to go directly to your default company when you sign in, and avoid having to specify an environment, is to add the the URL to your list of favorites after you sign in.

## See Also

[The Business Central Administration Center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center)  
[Change Basic Settings](ui-change-basic-settings.md)