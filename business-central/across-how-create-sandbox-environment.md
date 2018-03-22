---
title: Create a Sandbox Environment| Microsoft Docs
description: Create an environment for exploring, learning, demoing, developing, and testing.
author: SusanneWindfeldPedersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sandbox, demo, develop
ms.date: 08/18/2017
ms.author: solsen

---
[!INCLUDE[d365fin_early_release](includes/d365fin_early_release.md.md)]

# Create a Sandbox Environment
A sandbox environment (Preview) is a non-production instance of [!INCLUDE[d365fin](includes/d365fin_md.md)]. Isolated from production, a sandbox environment is the place to safely explore, learn, demo, develop, and test the service without the risk of affecting the data and settings of your production environment.

## To create a sandbox environment
You must have a subscription to [!INCLUDE[d365fin](includes/d365fin_md.md)] to be able to create a sandbox environment. There can only be one sandbox environment per subscription.

1. Sign in to your production instance of the [!INCLUDE[d365fin](includes/d365fin_md.md)] service.
2. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sandbox Environment**, and then choose the related link.
![Sandbox Environment Setup](./media/across-sandbox/sandbox-environment-setup.png)
3. Select **Create**.  
  Another tab in your browser will open for finishing the setup of your sandbox environment.
> [!NOTE]  
>  If you have pop-up blocker enabled in your browser, change it to allow URLs from the *.financials.dynamics.com address.   

4. When the sandbox environment is ready, you will be redirected to sandbox environment's Welcome wizard.
![Sandbox Welcome Wizard](./media/across-sandbox/sandbox-wizard.png)

5. Choose **Learn more** to read about scenarios that you can try in a sandbox environment. Or, choose **Close** to continue to the Role Center of your [!INCLUDE[d365fin](includes/d365fin_md.md)] sandbox instance.
6. At the top of the Role Center, a notification appears to inform you that this is a sandbox environment. You can also see the type of the environment in the title bar of the client.
![Sandbox RoleCenter Notification](./media/across-sandbox/sandbox-rolecenter-notification.png)  
In the sandbox environment, a brand-new tenant has been created. This tenant is loaded with default demonstration data for the CRONUS company. No data is copied or otherwise transferred from the production environment during the sandbox creation.
7.	At any time, you can return to the **Sandbox Environment** page, and reset the sandbox environment.
> [!NOTE]  
>  Resetting the sandbox environment will remove it completely, and then create it again with the default demonstration data.  

8.	To switch between your production and sandbox environments, you can use the Business Central app launcher.
![Sandbox Dynamics365 Menu](./media/across-sandbox/sandbox-dynamics365-menu.png)

9.	It is possible for an administrator or another user to limit or even block access for some users to the sandbox environment. This can be done by using the standard security features of the product, such as the User card, User Groups, and Permission Sets.

![Sandbox Permission Sets](./media/across-sandbox/sandbox-permission-sets.png)

## Advanced functionality in the sandbox environment
### The in-client designer
In a sandbox environment, you will find the in-client designer feature enabled, which you can activate by selecting the design icon ![Designer](./media/across-sandbox/sandbox-inclient-design-icon.png) on a page.

![In-client Designer](./media/across-sandbox/sandbox-inclient-designer.png)

### Enable the advanced user experience
It is possible to enable and try the advanced (full) functionality of [!INCLUDE[d365fin](includes/d365fin_md.md)] in a sandbox tenant by setting the **Experience** field on the **Company Information** page.

![Sandbox Environment Advanced](./media/across-sandbox/sandbox-advanced.png)

![Sandbox Production](./media/across-sandbox/sandbox-production.png)

After you’ve enabled the advanced functionality in a sandbox tenant, you get access to all the standard Profiles and Role Centers. You can also create an evaluation company that is fully set up, including demonstration data and access to the advanced areas of the product.

![Sandbox New Company](./media/across-sandbox/sandbox-newcompany.png)


## See Also
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
