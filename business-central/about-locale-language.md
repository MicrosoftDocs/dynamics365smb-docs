---
title: Multilanguage and Localization
description: Learn how language and region influence your experience in Business Central. Change the language of the user interface in My Settings.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: language, locale, localization, culture, region, regional settings
ms.date: 04/01/2021
ms.author: edupont

---
# Changing Language and Region

[!INCLUDE[prod_short](includes/prod_short.md)] is available in a number of markets and languages around the World. In the markets where [!INCLUDE[prod_short](includes/prod_short.md)] is available, a set of regulatory features are available to assist companies with regulatory burdens. [!INCLUDE[prod_short](includes/prod_short.md)] can present itself in different languages and you can change the language that is used to display texts, and the change is immediate, once you have been automatically signed out and in again. The setting applies to you and not to everyone else in your company.  

For example, if you are using the Canadian version of [!INCLUDE[prod_short](includes/prod_short.md)], you can see the user interface in English, German, French, or another language, but it is still the Canadian version of [!INCLUDE[prod_short](includes/prod_short.md)] in all other aspects. It is not the same as, say, [!INCLUDE[prod_short](includes/prod_short.md)] in the United Kingdom where functionality has been adapted towards that market's requirements.  

To change the language of the user interface, go to the **My Settings** page. For more information, see [Change Basic Settings](ui-change-basic-settings.md#language). 

> [!NOTE]  
> The choice of languages will be reset to your setting on your Microsoft 365 profile if your administrator synchronizes users from Microsoft 365 to [!INCLUDE[prod_short](includes/prod_short.md)].

Changing the texts that are stored as application data is not part of the multilanguage capability. This is an application design issue. Examples of such texts are the names of items in the inventory or the comments for a customer. In other words, these types of text are not translated.  

> [!NOTE]  
> [!INCLUDE[prod_short](includes/prod_short.md)] only supports a single character set for data. Therefore some characters may not be supported in your environment, and you may experience problems when retrieving data that was entered using a different character set. For instance, your environment may support only English and Russian characters and if you enter data in a different language, it may not be stored correctly. You should contact your system administrator to make sure you understand which languages are supported for your [!INCLUDE[prod_short](includes/prod_short.md)].  

## Changing the region
Region is different from both language and legal requirements in local markets. Region determines how your data presents itself in terms of comma separator, aligned to the left or to the right, and certain other settings. The region also determines some of the system elements in the browser, such as the action to create a new item in a list, for example.  

You can change the region in the browser tab that you are using to work in [!INCLUDE[prod_short](includes/prod_short.md)]. The change applies only to you and not to the other users in your company.  The choice of region will be reset to your setting on your Microsoft 365 profile if your administrator synchronizes users from Microsoft 365 into [!INCLUDE[prod_short](includes/prod_short.md)].

> [!IMPORTANT]  
> When you change the region, you will see a long list of languages and regions. However, the language is not influenced by the choice of region.  

To change the region, go to the **My Settings** page. For more information, see [Change Basic Settings](ui-change-basic-settings.md).  

## Application Version

In the **Help and Support** page, you can see the version of [!INCLUDE[prod_short](includes/prod_short.md)] that your company is based on. If you want to base a company on a different version, your administrator can create a new production environment. For more information, see [Create a new production environment](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#create-a-new-production-environment) in the developer- and IT Pro content.  

## Languages of the [!INCLUDE[prod_short](includes/prod_short.md)] Help

The Help content for the core functionality in [!INCLUDE[prod_short](includes/prod_short.md)] publishes to the Microsoft Docs site and available in a number of different languages. If you access the docs from inside [!INCLUDE[prod_short](includes/prod_short.md)], the content will display in your language. If a particular page is not available in your language yet, it will be shown in English.

### How do I change the language of the Microsoft Docs site?

It's simple - scroll to the bottom of the browser page and choose the globe symbol in the bottom left corner.

> [!NOTE]  
> The list shows all languages that are supported by the Microsoft Docs site. [!INCLUDE[prod_short](includes/prod_short.md)] is available in a limited number of countries/regions, and the [!INCLUDE [prod_short](includes/prod_short.md)] Help content is not available in all languages that the Microsoft Docs site supports.

## See Also

[Resources for Help and Support](product-help-and-support.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]