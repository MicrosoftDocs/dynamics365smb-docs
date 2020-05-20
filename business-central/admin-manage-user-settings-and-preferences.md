---
title: Manage user settings and preferences in Dynamics 365 Business Central | Microsoft Docs
description: Manage user settings and preferences in Dynamics 365 Business Central.
documentationcenter: ''
author: sorenfriisalexandersen

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: user settings, preferences, language, region, time zone, regional settings
ms.date: 05/19/2020
ms.author: soalex

---
# Manage user settings and preferences

This page describes how to manage user settings in [!INCLUDE[d365fin](includes/d365fin_md.md)], similar to the ones users can set individually in the **My Settings** page.  

## What is user settings?
**User settings** is not the same as **User Setup** which is about the user as an entity and the user's access in the system. Furthermore, user settings has nothing to do with a user's personalization as in the ability to make lightweight changes to the user interface. User settings are used to determine user's preferences in various aspects of the way the application presents itself to the user. The following paragraph lists the user settings and preferences that can be set by the individual or centrally by the administrator:

* **Company**  
This setting determines the company to be logged into at the next login. A user can have access to multiple companies and can be active in several companies.

* **Profile (Roles)**  
Thre profile describes the user's function in the company. For example "Sales Manager", "Bookkeeper" or "Purchasing Agent". The profile in turn determines the user's role center, the home page that users will see when they have signed in. The profile does not impact access rights to functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)]. 

* **Locale ID (Regional settings)**  
Defines how dates and numbers are presented in the [!INCLUDE[d365fin](includes/d365fin_md.md)] client, for example to use European or American date formats and how to display decimal sign and thousand separators in amounts. If [!INCLUDE[d365fin](includes/d365fin_md.md)] users are synchronized from Office 365 the regional settings from Office 365 will be used, assuming the user wants to use the same settings in and [!INCLUDE[d365fin](includes/d365fin_md.md)]. An administrator or user can change these settings manually in [!INCLUDE[d365fin](includes/d365fin_md.md)] but they will be reset to the value from Office 365 once the next syncronization is performed.

 * **Language**  
 Defines the application language in which [!INCLUDE[d365fin](includes/d365fin_md.md)] presents text, captions and error messages. If [!INCLUDE[d365fin](includes/d365fin_md.md)] users are synchronized from Office 365 the language settings from Office 365 will be used, assuming the user wants to use the same settings in and [!INCLUDE[d365fin](includes/d365fin_md.md)]. An administrator or user can change these settings manually in [!INCLUDE[d365fin](includes/d365fin_md.md)] but they will be reset to the value from Office 365 once the next syncronization is performed.
 If the language setting from Office 365 matches a supported language in [!INCLUDE[d365fin](includes/d365fin_md.md)] this language will be chosen for the user. Note that a language app may need to be installed for [!INCLUDE[d365fin](includes/d365fin_md.md)] to properly display the language. Therefore it is a good practice to install the necessary language apps before any user logs in the first time, to ensure they have a good experience. See a list of [supported languages here](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). 
  
* **Time Zone**  
Defines the time zone in which the user is located. Currently this is not synchronized from Office 365 and must be set manually.

> [!NOTE]
> If a Office 365 user synchronization is made while users are logged into [!INCLUDE[d365fin](includes/d365fin_md.md)] these users need to refresh the client or log out and back in to [!INCLUDE[d365fin](includes/d365fin_md.md)] to see a potential different language set by the synchronization action.

## Overview of all user settings
Administrators have the option to set or change these settings for users in each company. This is done on the **User Personalizations** (deep link here) page. Records on this page will reflect the individual user's choices for the above settings, one record per user. As users make changes to their settings in the **My Settings** page they will be reflected in the **User Personalizations** list. Administrators can also set these settings for users before they log in the first time, so users do not have to do it themselves, providing them a better *getting started* experience.

> [!NOTE]
> **User Personalizations** does not have anything to do with the *personal* lightweight changes a user can make to the user experience. 

## Review or make changes to user settings

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Personalizations**, and then choose the related link.
2. This shows the list of users and their settings. To modify a user's settings, click the **User ID** or choose **Manage** and then **Edit**.
3. The **User Personlization** card for the specific user's settings is shown and desired changes can be made. 

## See Also
[Getting Started](product-get-started.md)  
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  
[Changing Language and Locale](about-locale-language.md) 
