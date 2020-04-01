---
title: Multilanguage and Localization | Microsoft Docs
description: Learn how language and locale influence your experience in Business Central.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: language, locale, localization, culture
ms.date: 04/01/2020
ms.author: edupont

---
# Changing Language and Locale

[!INCLUDE[d365fin](includes/d365fin_md.md)] is supported in a number of markets and available in the languages that those markets require. This is a result of support for multiple languages at runtime in combination with support for legal requirements in the supported markets. This means that [!INCLUDE[d365fin](includes/d365fin_md.md)] can present itself in different languages. You can change the language that is used to display texts, and the change is immediate, once you have been automatically signed out and in again. The setting applies to you and not to everyone else in your company.  

For example, if you are using the Canadian version of [!INCLUDE[d365fin](includes/d365fin_md.md)], you can see the user interface in English and in French, but it is still the Canadian version of [!INCLUDE[d365fin](includes/d365fin_md.md)] in all other aspects. It is not the same as, say, [!INCLUDE[d365fin](includes/d365fin_md.md)] in the United Kingdom.  

To change the language of the user interface, go to the **My Settings** page. For more information, see [Change Basic Settings](ui-change-basic-settings.md#language).  

Changing the texts that are stored as application data is not part of the multilanguage capability. This is an application design issue. Examples of such texts are the names of items in the inventory or the comments for a customer. In other words, these types of text are not translated.  

> [!NOTE]  
> [!INCLUDE[d365fin](includes/d365fin_md.md)] only supports a single character set for data. Therefore some characters may not be supported in your tenant, and you may experience problems when retrieving data that was entered using a different character set. For instance, your tenant may support only English and Russian characters and if you enter data in a different language, it may not be stored correctly. You should contact your system administrator to make sure you understand which languages are supported for your [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## Changing the Locale
Locale is different from both language and legal requirements in local markets. Locale determines how your data presents itself in terms of comma separator, aligned to the left or to the right, and certain other settings. The locale also determines some of the system elements in the browser, such as the action to create a new item in a list, for example.  

You can change the locale in the browser tab that you are using to work in [!INCLUDE[d365fin](includes/d365fin_md.md)]. the change applies only to you and not to the other users in your company.  

> [!IMPORTANT]  
>  When you change the locale, you will see a long list of languages and locales. However, only the locale setting is used in the current version of [!INCLUDE[d365fin](includes/d365fin_md.md)].  

To change the locale, go to the **My Settings** page. For more information, see [Change Basic Settings](ui-change-basic-settings.md).  

## Application Version

In the **Help and Support** page, you can see the version of [!INCLUDE [prodshort](includes/prodshort.md)] that your company is based on. If you want to base a company on a different version, your administrator can create a new production environment. For more information, see [Create a new production environment](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#create-a-new-production-environment) in the developer- and IT Pro content.  

## Languages of the [!INCLUDE[d365fin](includes/d365fin_md.md)] Help
The Help content for the core functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)] publishes to the Microsoft Docs site and available in a number of different languages. If you access the docs from inside [!INCLUDE[d365fin](includes/d365fin_md.md)], the content will display in your language. If a particular page is not available in your language yet, it will be shown in English.

### How Do I Change the Language?
It's simple - scroll to the bottom of the browser page and choose the globe symbol in the bottom left corner.

> [!NOTE]  
> The list shows all languages that are supported by the Microsoft Docs site. [!INCLUDE[d365fin](includes/d365fin_md.md)] is available in a limited number of countries/regions, but the Help content is made available in more languages. However, the Help content is not available in all languages that the Microsoft Docs site supports.

## See Also

[Resources for Help and Support](product-help-and-support.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Getting Started](product-get-started.md)  
