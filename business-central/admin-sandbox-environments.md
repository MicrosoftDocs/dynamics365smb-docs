---
title: Sandbox environments
description: Learn about how a dedicated environment can help you safely explore, learn, demo, develop, troubleshoot, and test Business Central.
author: brentholtorf
ms.topic: reference
ms.reviewer: bholtorf
ms.devlang: al
ms.search.keywords: sandbox, demo, develop
ms.date: 12/20/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Sandbox Environments in [!INCLUDE[prod_short](includes/prod_short.md)]

With [!INCLUDE[prod_short](includes/prod_short.md)] online, you can easily get a safe environment where you can test, train, or troubleshoot without disturbing your company's work processes or business data. Such a non-production environment is called a *sandbox*. Isolated from production, a sandbox environment is the place to safely explore, learn, demo, develop, and test the service without the risk of affecting the data and settings of your production environment.  

> [!TIP]
> Did you land on this article after you chose the name of your [!INCLUDE [prod_short](includes/prod_short.md)] environment in the top bar? Currently, you cannot change the name or the environment that way. Instead, you must ask your admin to change the name, or ask them to share the link to another environment.

Your administrator manages sandbox environments in the [administration center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments?toc=/dynamics365/business-central/toc.json).  

For example, if you want to create a sandbox for benchmarking, your administrator can create a dedicated environment in the administration center. For more information, see [Production and Sandbox Environments](/dynamics365/business-central/dev-itpro/administration/environment-types) in the developer and administration content.  

You can also safely use sandboxes for training, such as for following a learning path from [Microsoft training](/training/dynamics365/business-central?WT.mc_id=dyn365bc_landingpage-docs), because it's a safe environment to experiment with. If anything goes wrong, you just delete the sandbox and start over.  

Once you're done, you can remove the sandbox, using the administration center.  

> [!NOTE]
> Technically, sandbox environments are very different from production environments. Your administrator can create a sandbox that includes production data, but it is still a sandbox, and you cannot request a database export, for example. For more information, see [Sandbox environments](/dynamics365/business-central/dev-itpro/administration/environment-types#sandbox-environments) in the developer and administration content.

The sandbox environment is not least useful because it includes a couple of handy features:

* [Advanced user experience](#advanced-user-experience)  
<!--* [Complete sample data](#complete-sample-data)  -->
* [Designer](#designer)  

## Advanced user experience

It is possible to enable and try the full functionality of the standard version of [!INCLUDE[prod_short](includes/prod_short.md)] in a sandbox tenant by setting the **Experience** field on the **Company Information** page to *Premium*. Find the **Company Information** page in the :::image type="content" source="media/ui-experience/settings_icon_small.png" alt-text="Settings icon."::: menu.  

After you have enabled the *Premium* user experience, you get access to all the standard profiles (roles) and Role Centers in the standard version. Alternatively, contact a reselling partner for a demonstration of the capabilities. For more information, see [How do I find a reselling partner?](across-faq.yml#how-do-i-find-a-reselling-partner).  

### Complete sample data

For situations where you need additional sample data, please talk to your reselling partner.
<!-- In the sandbox environment, you can also create a new company with the **Advanced Evaluation - Complete Sample Data** option so that you can take training or step through walkthroughs that require additional sample data, such as [Walkthrough: Receiving and Putting Away in Basic Warehouse Configurations](walkthrough-receiving-and-putting-away-in-basic-warehousing.md).   -->

<!--#### To create a company with complete sample data in a sandbox

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Companies**, and then choose the related link.  
2. Choose the **New** action, and then choose **Create New Company**.  
3. In the **Assisted Setup for Creating a Company** page, choose **Next**.  
4. Specify a name for the new company, and then, in the **Select the data and setup to get started** field, choose **Advanced Evaluation - Complete Sample Data**.  
5. Complete the rest of the assisted setup guide.  

When the assisted setup guide completes, you can start exploring the new company with the complete sample data. For more information, see [Creating New Companies in [!INCLUDE[prod_short](includes/prod_short.md)]](about-new-company.md).  -->

## Designer

In a sandbox environment, you will find the **Designer** enabled. You can activate Designer by selecting the design icon ![Designer.](./media/across-sandbox/sandbox-inclient-design-icon.png) on a page, or by choosing the **Design** menu item in the ![Settings](media/ui-experience/settings_icon_small.png) Settings menu.  

For more information, see [Use Designer](/dynamics365/business-central/dev-itpro/developer/devenv-inclient-designer) in the developer and admin content (in English only).  

<!-- ![In-client Designer.](./media/across-sandbox/sandbox-inclient-designer.png) -->

## Related information

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[[!INCLUDE[prod_long](includes/prod_long.md)] Trials and Subscriptions](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions)  
[Managing Environments in the Business Central administration center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments)  
[Production and Sandbox Environments](/dynamics365/business-central/dev-itpro/administration/environment-types)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
