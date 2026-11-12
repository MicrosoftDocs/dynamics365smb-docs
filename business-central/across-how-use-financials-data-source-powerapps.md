---
title: Build a Power Apps Canvas App with Business Central Data
description: Connect a Power Apps canvas app to Business Central APIs to work with customers, items, and other business data in an app for your organization.
author: jswymer
ms.topic: how-to
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
ms.search.keywords: OData, Power App, SOAP
ms.date: 11/12/2026
ms.author: jswymer
ms.reviewer: v-soumramani
---

# Build a Power Apps canvas app with Business Central data

You can make your [!INCLUDE[prod_short](includes/prod_short.md)] data available as a data source in Power Apps.  

> [!TIP]  
> Business Central now offers development and operations support for Power Platform in AL-Go and samples to get you started creating your own apps with Power Apps. These features are currently in preview. Learn more in [Business Central and Power Apps](/dynamics365/business-central/dev-itpro/powerplatform/power-apps-overview) in the developer and IT pro help.

## Prerequisites

You must have a valid account with [!INCLUDE[prod_short](includes/prod_short.md)] and with Power Apps.  

## Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power Apps

These steps add data exposed by a Business Central API, like customers or items, as a data source in a canvas app.

1. In [Power Apps](https://make.powerapps.com/), create a blank canvas app or open an existing canvas app for editing. Learn more in [Create a blank canvas app](/powerapps/maker/canvas-apps/create-blank-app).
1. In Power Apps Studio, select **Data** in the app authoring menu on the left.
1. Select **Add data**, search for `Business Central`, and select the connector.
1. Select an existing connection, or select **Add a connection** to create one. When prompted, sign in using the same username and password you use for [!INCLUDE[prod_short](includes/prod_short.md)].
1. In the **Choose a table** pane, select the Business Central environment, company, API category, and table that contains the data you want to use.

> [!NOTE]
> For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, use the separate **Business Central (on-premises)** connector. Learn more in [Dynamics 365 Business Central (on-premises) connector](/connectors/dynamicssmbonprem/).

The connector exposes API endpoints as tables in Power Apps. Learn more in [Add a data connection to a canvas app in Power Apps](/powerapps/maker/canvas-apps/add-data-connection) and [Dynamics 365 Business Central connector](/connectors/dynamicssmbsaas/).

> [!NOTE]
> If the data you need isn't available through an existing API, work with a developer to expose it through a custom API. Learn more in [Developing a custom API](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api).

At this point, you have successfully connected to your [!INCLUDE[prod_short](includes/prod_short.md)] data and are ready to begin building your Power App. You can always add more screens and connect to more data. Learn more in [Create a canvas app from a sample in Power Apps](/powerapps/maker/canvas-apps/open-and-run-a-sample-app).  

When you have designed and built your app, you can share it with your colleagues. Learn more in [Share a canvas app in Power Apps](/powerapps/maker/canvas-apps/share-app).  

## Related information

[Create a canvas app from a template in Power Apps](/powerapps/maker/canvas-apps/get-started-test-drive)  
[Import Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Get Started Developing Connect Apps for Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
