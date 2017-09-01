---
title: Multilanguage and Localization | Microsoft Docs
description: Learn how language and locale influence your experience in Dynamics 365.
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:language, locale, localization, culture
ms.date: 09/01/2017
ms.author: edupont

---
# Language and Locale
[!INCLUDE[d365fin](includes/d365fin_md.md)] is supported in a number of markets and available in the languages that those markets require. This is a result of support for multiple languages at runtime in combination with support for legal requirements in the supported markets. This means that [!INCLUDE[d365fin](includes/d365fin_md.md)] can present itself in different languages. You can change the language that is used to display texts, and the change is immediate, once you have been automatically signed out and in again. The setting applies to you and not to everyone else in your company.  

For example, if you are Canadian, you can see the user interface in English and in French, but it is still the Canadian version of [!INCLUDE[d365fin](includes/d365fin_md.md)] in all other aspects. It is not the same as, say, [!INCLUDE[d365fin](includes/d365fin_md.md)] in the United Kingdom.  

> [!NOTE]  
>  Changing the language is currently not supported in [!INCLUDE[d365fin](includes/d365fin_md.md)].

Changing the texts that are stored as application data is not part of the multilanguage capability. This is an application design issue. Examples of such texts are the names of items in the inventory or the comments for a customer. In other words, these types of text are not translated.  

> [!NOTE]  
>  [!INCLUDE[d365fin](includes/d365fin_md.md)] only supports a single character set for data. Therefore some characters may not be supported in your tenant, and you may experience problems when retrieving data that was entered using a different character set. For instance, your tenant may support only English and Russian characters and if you enter data in a different language, it may not be stored correctly. You should contact your system administrator to make sure you understand which languages are supported for your [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## Changing the Locale
Locale is different from both language and legal requirements in local markets. Locale determines how your data presents itself in terms of comma separator, aligned to the left or to the right, and certain other settings. The locale also determines some of the system elements in the browser, such as the action to create a new item in a list, for example.  

You can change the locale in the browser tab that you are using to work in [!INCLUDE[d365fin](includes/d365fin_md.md)]. the change applies only to you and not to the other users in your company.  

> [!IMPORTANT]  
>  When you change the locale, you will see a long list of languages and locales. However, only the locale setting is used in the current version of [!INCLUDE[d365fin](includes/d365fin_md.md)].  

To change the locale, go to the **My Settings** window. For more information, see [Changing Basic Settings](ui-change-basic-settings.md).  

## See Also  
[Languages of the Docs](about-languages.md)  
[Changing Basic Settings](ui-change-basic-settings.md)  
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
