---
title: User Settings Dynamics 365 Business Central | Microsoft Docs
description: Manage user settings for Business Central.
documentationcenter: ''
author: sorenfriisalexandersen

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: user settings, language, region
ms.date: 05/19/2020
ms.author: soalex

---
# User Settings in [!INCLUDE[d365fin](includes/d365fin_md.md)]

User settings, also known as user *personlizations*, are used in [!INCLUDE[d365fin](includes/d365fin_md.md)] to determine various aspects of the way the application presents itself to the user. Every user can choose their own settings for the following:

* **Company**  
The legal entity/company into which the user logs in. A user can have access to multiple companies but only be active in one company at a time.

* **Role**  
Defines the user's role center, visibile to the user when logged in. The role does not impact access rights to functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)]. 

* **Region**  
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
> Even though it sounds like it, the name **User Personalizations** does not have anything to do with the *personal* changes a user can make to hide and show fields throughout [!INCLUDE[d365fin](includes/d365fin_md.md)]. We are working on changing the name of the **User Personalization** page to reflect that it allows for administrators to review or change user settings. 

## Review or make changes to user settings

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Personalizations**, and then choose the related link.
2. This shows the list of users and their settings. To modify a user's settings, click the **User ID** or choose **Manage** and then **Edit**.
3. The **User Personlization** card for the specific user's settings is shown and desired changes can be made. 

## See Also
[Getting Started](product-get-started.md)  
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  
[Changing Language and Locale](about-locale-language.md) 
