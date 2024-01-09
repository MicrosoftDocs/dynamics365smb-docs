---
title: Company information overview
description: The Company Information page specifies basic information for a business entity, such as name, addresses, and shipping information. 
author: jswymer
ms.topic: conceptual
ms.search.form: 1
ms.date: 09/24/2023
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics365-business-central
ms.custom: bap-template
---

# Company information overview

[!INCLUDE[prod_short](includes/prod_short.md)] organizes business entities in *companies*. For each company, you must fill in some of the basic company details and relevant information on the **Company Information** page. The information on the [**Company Information**](https://businesscentral.dynamics.com/?page=1) page is used in documents, such as invoice headers. You can set up more than one company, such as a parent company and a subsidiary.  

If the company's inventory warehouse is located at a different address than the company headquarters, you can complete the various ship-to fields and the **Location Code** field on the **Shipping** FastTab. The information in these fields is then printed on purchase orders, for example, so vendors will ship items to the correct location.  

For each company you set up, you must fill in the **Company Information** page, together with the **General Ledger Setup** page. You must also set up each area in [!INCLUDE [prod_short](includes/prod_short.md)], such as the **Sales & Receivables Setup** page, for each company. Learn more at [Overview of Tasks to Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md).  

The **Company Information** page contains different fields and FastTabs, depending on your country/region. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] The following table describes the most common FastTabs.

[!INCLUDE [admin-company-info-fasttabs](includes/admin-company-info-fasttabs.md)]

Once you have completed filling in the information, you can close the page.  

## Working with multiple companies

If your [!INCLUDE [prod_short](includes/prod_short.md)] includes multiple companies, your users might want to use *company badges* to help them quickly identify and keep track of which company they're currently working in. For more information, see [Display a company badge](#badge).

There are a few features you can use to switch among companies as you work, like the company switcher (<kbd>Ctrl</kbd>+<kbd>O</kbd>). Learn more at [Switch to Another Company or Environment](ui-organization-switch.md).

## <a name="badge"></a>Display a company badge

When there's more than one company or environment, you'll see the company switcher on the upper-right side of the app bar, near the search icon in the app bar. By default, the company switcher uses a standard company icon, like ![company icon Launcher.](media/ui-experience/company-icon.png "Displays the company switcher icon used when there is a single environment") and ![company-icon-mult-env](media/ui-experience/company-icon-multi-env.png "Displays the company switcher icon used when there are multiple environments").

:::image type="content" source="media/ui-experience/company-switch-2.png" alt-text="Shows the company switcher icon in the heading of the Business Central client.":::  

Starting in 2023 release wave 2, version 23, the company badge appears in the browser tab when using the web client. It's also included in page links that you [copy and paste](across-share-data-features.md#copying-a-link) in rich text editors, like Word, Outlook, and Teams.
 
### Set the company badge

Using the **Company Information** page, you can replace the standard company icon with a custom badge on a per-company basis if the company badge makes it easier for users to identify the company they're working in.

1. On the **Company Badge** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
2. When done, refresh the browser (select <kbd>Ctrl</kbd>+<kbd>F5</kbd>) to update the badge in the client.  

> [!NOTE]
> The company switcher was introduced in 2022 release wave 2, version 21. In earlier releases, the company badge isn't used for switching companies. It's shown in the upper-right corner of most pages, even when there's only one company. Selecting it will show the full company name and environment name.

## Change company display name

The company name is always displayed at the top left corner and works as an action that you can choose to go back to the Role Center. You can change this name on the **Company Information** page.

1. Choose the ![Sprocket icon to open the Settings menu.](media/ui-experience/settings_icon_small.png) icon, and then choose the **Company Information** action.
2. In the **Name** field, enter the new company name.
3. Leave the page. The system restarts and displays the new company in the top-left corner.

## Experience

The default user experience in a [!INCLUDE [prod_short](includes/prod_short.md)] trial doesn't reveal all capabilities. You can switch on the full experience on the **Company Information** page. For more information, see [Change Which Features are Displayed](ui-experiences.md).  

## See also

[Overview of Tasks to Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Company Information Quick Start](quick-start-company-information.md)  
[Set Up Company Information in Italy](LocalFunctionality/Italy/how-to-set-up-company-information.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Creating New Companies](about-new-company.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
