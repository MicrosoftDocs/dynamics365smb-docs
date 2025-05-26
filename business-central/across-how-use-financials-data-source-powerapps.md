---
title: Use Your Data to Create an App| Microsoft Docs
description: You can make your Business Central data available as a data source and specify an OData URL of your web services to build a business app using Power Apps.
author: jswymer
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.search.keywords: OData, Power App, SOAP
ms.date: 05/15/2023
ms.author: jswymer
ms.reviewer: jswymer
---
# Connecting to Your Business Central Data to Build a Business App Using Power Apps

You can make your [!INCLUDE[prod_short](includes/prod_short.md)] data available as a data source in Power Apps.  

> [!TIP]  
> Business Central now offers development and operations support for Power Platform in AL-Go and samples to get you started creating your own apps with Power Apps. These features are currently in preview. To learn more, go to [Business Central and Power Apps](/dynamics365/business-central/dev-itpro/powerplatform/power-apps-overview) in the developer and IT pro help.

## Prerequisites

You must have a valid account with [!INCLUDE[prod_short](includes/prod_short.md)] and with Power Apps.  

## Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power Apps

These steps add a Business Central table, like customers or items, as the data source of a Power Apps app.

1. In your browser, go to [powerapps.microsoft.com](https://powerapps.microsoft.com/), and then sign in.
2. In the navigation pane on the left side, select **+ Create**, and then select **More data sources** on the **Create app** page.
  
   <!-- This step opens Power Apps canavs. On first sign-in, you must specify the country/region.  -->
3. The **Connections** the list shows any existing data connections you have.

   - If there's a **Business Central** connection already, select it, and then select **Create**.

   - If you don't see a Business Central connection, select **+ New connection**, search for and select **Business Central**, and then select **Create**.

   > [!NOTE]
   > If you want to connect to [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, then you must choose the **Business Central (on-premises)** connector.  
  
4. Power Apps connects to your [!INCLUDE[prod_short](includes/prod_short.md)]. Sign in using the Business Central account name and password. If you aren't an administrator of your [!INCLUDE[prod_short](includes/prod_short.md)], you may have to sign in with another account.  
5. Once you've signed in, Power Apps displays a list of *Environments and companies* that are available from [!INCLUDE[prod_short](includes/prod_short.md)]. Choose the environment and company that contains the data you want to connect to, such as *PRODUCTION - My Company*.  
6. Next, you're presented with a list of tables that are exposed as part of the API for your environment. Select the table that you want to connect to, and then choose **Connect**.

These so-called tables are exposed as endpoints by the [!INCLUDE[prod_short](includes/prod_short.md)] connector for Power Apps.  

> [!NOTE]
> If you want to include data from other tables in [!INCLUDE[prod_short](includes/prod_short.md)] in your app, then you must work with a developer to define a custom API in [!INCLUDE[prod_short](includes/prod_short.md)].  

At this point, you have successfully connected to your [!INCLUDE[prod_short](includes/prod_short.md)] data and are ready to begin building your Power App. You can always add more screens and connect to more data. Learn more at [Create a canvas app from a sample in Power Apps](/powerapps/maker/canvas-apps/open-and-run-a-sample-app).  

When you have designed and built your app, you can share it with your colleagues. For more information, see [Save and publish a canvas app in Power Apps](/powerapps/maker/canvas-apps/save-publish-app).  

<!--
## Sample apps to get started

As a preview version, Business Central offers several sample apps that you can use as a starting point for building your own apps that use Business Central data. These sample apps are available in the [Business Central Demos](https://github.com/BusinessCentralDemos) repo on GitHub. For a quick overview on the apps, go to [Power Apps samples for Business Central](/dynamics365/business-central/dev-itpro/powerplatform/power-apps-samples).

## Develop and maintain apps application lifecycle management

As an app developer, you may already be familiar with Business Central AL-Go. AL-Go is set of tools on GiHub that enables you to maintain professional DevOps processes for your Business Central AL projects. AL-Go supports source control and activities, like building, testing, and deploying. As a preview, Business Central now offers an Al-Go version that supports for Power Platform solutions. The preview, for example, includes workflows that let you push and pull Power Platfrom changes to and from enviroments. You can access the tools at [https://github.com/BusinessCentralDemos/AL-Go-PTE](https://github.com/BusinessCentralDemos/AL-Go-PTE). For more information, see [Application lifecycle management for Power Apps in Business Central](/dynamics365/business-central/dev-itpro/powerplatform/power-apps-alm).-->

## Related information

[Create a canvas app from a template in Power Apps](/powerapps/maker/canvas-apps/get-started-test-drive)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Getting Started Developing Connect Apps for Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
