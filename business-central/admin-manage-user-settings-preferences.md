---
title: Manage user settings and preferences as the administrator
description: Manage user settings and preferences in Dynamics 365 Business Central.
author: sorenfriisalexandersen
ms.topic: get-started
ms.devlang: al
ms.reviewer: bholtorf
ms.search.keywords: user settings, preferences, language, region, time zone, regional settings
ms.search.form: 9204, 9200
ms.date: 07/27/2024
ms.author: soalex
ms.service: dynamics-365-business-central
---
# Manage user settings and preferences

As an administrator, you can configure user settings in [!INCLUDE[prod_short](includes/prod_short.md)], similar to how individual users can manage their own preferences in the **My Settings** page.  

Get an overview of all users in the **Users** list, and change individual settings by selecting the **User Settings** action for the relevant user.

> [!TIP]
> The **User Settings** list shows the current settings for each user. To view or edit individual users, select the **View** or **Edit** action.

The **User Settings** card page is similar to the **My Settings** page that each user has access to, and it's a powerful tool for you as the administrator for setting default settings and clearing personalized pages, for example.  

## Types of user settings

*User settings* isn't the same as *user setup*, which is about the user as an entity and the user's access in the system. Furthermore, the user settings have nothing to do with a user's personalization, such as lightweight changes to the user interface. User settings determine the predefined settings for each user in various aspects of the way the application presents itself to the user. The following paragraph lists the five types of user settings and preferences that can be set by the individual or centrally by the administrator:

* **Company**  

  This setting determines the company to be logged into at the next sign-in. A user can have access to multiple companies and can be active in several companies.

* **Role**  

  The role, or profile, describes the user's function in the company, such as *Sales Manager*, *Bookkeeper*, or *Purchasing Agent*. The profile then determines the user's role center, the home page that users experience when they sign in. The profile doesn't impact access rights to functionality in [!INCLUDE[prod_short](includes/prod_short.md)].  

* **Language**  

  Defines the application language that [!INCLUDE[prod_short](includes/prod_short.md)] presents text, captions, and error messages in. If [!INCLUDE[prod_short](includes/prod_short.md)] users are synchronized from Microsoft 365, the language settings from Microsoft 365 are used, assuming that the user wants to use the same settings in Office products and [!INCLUDE[prod_short](includes/prod_short.md)]. The administrator can change the default setting, and each user can choose between available languages in the My Settings page. But they'll be reset to the value from Microsoft 365 once the next synchronization is performed.

  If the language setting from Microsoft 365 matches a supported language in [!INCLUDE[prod_short](includes/prod_short.md)], this language is chosen for the user.  

  > [!NOTE]
  > You may have to install a language app for [!INCLUDE[prod_short](includes/prod_short.md)] to properly display the language. Therefore, it's a good practice to install the necessary language apps before any user logs in the first time so that they have a good experience from their first day. For more information, see the list of [supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations).  
  
* **Region**  

  Defines how dates and numbers are presented in the [!INCLUDE[prod_short](includes/prod_short.md)] client, such as whether to use European or American date formats, or how to display the decimal sign and thousand separators in amounts. If [!INCLUDE[prod_short](includes/prod_short.md)] users are synchronized from Microsoft 365, the regional settings from Microsoft 365 are used, assuming that the user wants to use the same settings in Office products and [!INCLUDE[prod_short](includes/prod_short.md)]. An administrator or user can change these settings manually in [!INCLUDE[prod_short](includes/prod_short.md)], but they'll be reset to the value from Microsoft 365 once the next synchronization is performed.

* **Time zone**  

  Defines the time zone in which the user is located. Currently this setting isn't synchronized from Microsoft 365 and must be set manually.  

* **Teaching tips**

  [!INCLUDE [ua-teachingtips](includes/ua-teachingtips.md)] As an administrator, you can switch off teaching tips for all users, such as if you are in process of onboarding users who are already familiar with [!INCLUDE [prod_short](includes/prod_short.md)].  

> [!NOTE]
> If a Microsoft 365 user synchronization is made while users are logged into [!INCLUDE[prod_short](includes/prod_short.md)], these users must refresh the browser or sign out and back in to [!INCLUDE[prod_short](includes/prod_short.md)] to see a potential different language set by the synchronization action.

## Overview of all user-specific changes

As the administrator, you can get an overview of individual changes to [!INCLUDE [prod_short](includes/prod_short.md)] that each user might have made to various pages in [!INCLUDE [prod_short](includes/prod_short.md)]. As users make changes to their experience in [!INCLUDE [prod_short](includes/prod_short.md)], these changes are reflected in the **Personalized Pages** list. <!--Administrators can also set these settings for users before they log in the first time, so users do not have to do it themselves, providing them a better *getting started* experience.-->

<!-- >[!NOTE]
> User personalizations do not have anything to do with the *personal* lightweight changes a user can make to the user experience.-->

## Review or delete user personalizations

1. Select the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Personalized Pages**, and then select the related link.
2. This shows the list of users and their personalized pages. To clear a user's personalization, click the relevant row, or select **Manage**, and then select **Delete**.

This task deletes the personalization, and the user's experience of the relevant page returns to the default state.

## Related information

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  
[Changing Language and Locale](about-locale-language.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
