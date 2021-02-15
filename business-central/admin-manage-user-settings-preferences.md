---
title: Manage user settings and preferences in Dynamics 365 Business Central
description: Manage user settings and preferences in Dynamics 365 Business Central.
author: sorenfriisalexandersen

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: user settings, preferences, language, region, time zone, regional settings
ms.date: 10/01/2020
ms.author: soalex

---
# Manage user settings and preferences

As an administrator, you can user settings in [!INCLUDE[prod_short](includes/prod_short.md)], similar to how individual users can manage their own preferences in the **My Settings** page.  

## Types of user settings

*User settings* is not the same as *user setup*, which is about the user as an entity and the user's access in the system. Furthermore, user settings has nothing to do with a user's personalization, such as lightweight changes to the user interface. User settings determine the user's preferences in various aspects of the way the application presents itself to the user. The following paragraph lists the five types of user settings and preferences that can be set by the individual or centrally by the administrator:

- **Company**  

  This setting determines the company to be logged into at the next login. A user can have access to multiple companies and can be active in several companies.

- **Profile (Roles)**  

  The profile describes the user's function in the company, such as *Sales Manager*, *Bookkeeper*, or *Purchasing Agent*. The profile then determines the user's role center, the home page that users will see when they sign in. The profile does not impact access rights to functionality in [!INCLUDE[prod_short](includes/prod_short.md)].  

- **Locale ID (Regional settings)**  

  Defines how dates and numbers are presented in the [!INCLUDE[prod_short](includes/prod_short.md)] client, such as whether to use European or American date formats, or how to display the decimal sign and thousand separators in amounts. If [!INCLUDE[prod_short](includes/prod_short.md)] users are synchronized from Microsoft 365, the regional settings from Microsoft 365 are used, assuming that the user wants to use the same settings in Office products and [!INCLUDE[prod_short](includes/prod_short.md)]. An administrator or user can change these settings manually in [!INCLUDE[prod_short](includes/prod_short.md)], but they will be reset to the value from Microsoft 365 once the next synchronization is performed.

- **Language**  

  Defines the application language that [!INCLUDE[prod_short](includes/prod_short.md)] presents text, captions, and error messages in. If [!INCLUDE[prod_short](includes/prod_short.md)] users are synchronized from Microsoft 365, the language settings from Microsoft 365 are used, assuming that the user wants to use the same settings in Office products and [!INCLUDE[prod_short](includes/prod_short.md)]. An administrator or user can change these settings manually in [!INCLUDE[prod_short](includes/prod_short.md)], but they will be reset to the value from Microsoft 365 once the next synchronization is performed.

  If the language setting from Microsoft 365 matches a supported language in [!INCLUDE[prod_short](includes/prod_short.md)], this language will be chosen for the user.  

  > [!NOTE]
  > You may have to install a language app for [!INCLUDE[prod_short](includes/prod_short.md)] to properly display the language. Therefore, it is a good practice to install the necessary language apps before any user logs in the first time so that they have a good experience from their first day. For more information, see the list of [supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations).  
  
- **Time zone**  

  Defines the time zone in which the user is located. Currently this is not synchronized from Microsoft 365 and must be set manually.  

> [!NOTE]
> If a Microsoft 365 user synchronization is made while users are logged into [!INCLUDE[prod_short](includes/prod_short.md)], these users must refresh the browser or log out and back in to [!INCLUDE[prod_short](includes/prod_short.md)] to see a potential different language set by the synchronization action.

## Overview of all user settings

Administrators have the option to set or change these settings for users in each company. This is done on the **User Personalizations** page. Records on this page will reflect the individual user's choices for the above settings, one record per user. As users make changes to their settings in the **My Settings** page, these changes will be reflected in the **User Personalizations** list. Administrators can also set these settings for users before they log in the first time, so users do not have to do it themselves, providing them a better *getting started* experience.

> [!NOTE]
> User personalizations do not have anything to do with the *personal* lightweight changes a user can make to the user experience.

## To review or make changes to user settings

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Personalizations**, and then choose the related link.
2. This shows the list of users and their settings. To modify a user's settings, click the **User ID** or choose **Manage** and then **Edit**.
3. The **User Personlization** card for the specific user's settings is shown and desired changes can be made.  

## See Also

[Getting Started](product-get-started.md)  
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  
[Changing Language and Locale](about-locale-language.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]