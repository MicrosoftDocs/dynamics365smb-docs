---
title: Managing Personalization as an Administrator in Business Central | Microsoft Docs
description: Learn how to customize the user interface to suit your way of working.
services: project-madeira
documentationcenter: ''
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.date: 04/01/2019
ms.author: jswymer

---
# Managing Personalization as an Administrator

Users can personalize their workspace to suit their own preferences. As an administrator, you control and manage personalization by:

-   Enabling or disabling the personalization feature for the entire the application (on-premises installation only).
-   Enabling or disabling the personalization feature for users of a specific profile.
-   Clearing any page personalizations that users have made.

## <a name="EnablePersonalization"></a>Enable/Disable Personalization (On-Premises Only)

By default, personalization is not enabled in the client. You enable or disable personalization by modifying the configuration file (navsettings.json) of the Business Central Web Server instance that serves the clients.

1. To enable personalization, add the following line in the navsettings.json file:

    ```
    "PersonalizationEnabled": "true"
    ```
    
    To disable personalization, remove this line or change it to:
    
    ```
    "PersonalizationEnabled": "false"
    ```
    
    For more information about how to modify the navsettings.json file, see [Modify the navsettings.json file directly](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/configure-web-server?branch=master#Settings).
    
2. Generate and download the application symbols.

    This step is optional, and not required to enable personalization. However, it ensures that new pages that are created by developers can be personalized.

    1. First, you generate the symbols by running finsql.exe with `generatesymbolreference` command. The finsql.exe file is located in the installation folder for the [!INCLUDE[server](includes/server.md)] and Dynamics NAV Development Environment (CSIDE). To generate the symbols, open a command prompt, change to the directory where the file is store, and the run the following command:

        ```
        finsql.exe Command=generatesymbolreference, Database="<Database Name>", ServerName=<SQL Server Name\<Server Instance>
        ```
    For example:

        ```
        finsql.exe Command=generatesymbolreference, Database="Demo Database BC", ServerName=MySQLServer\BCDEMO
        ```

    For more information, see [Running C/SIDE and AL Side-by-Side](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-running-cside-and-al-side-by-side).

    2. Configure [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance to **Enable loading application symbol references at server startup** (EnableSymbolLoadingAtServerStartup). For more information, see [Configuring Business Central Server](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/configure-server-instance#development-settings).

## Disable personalization for a profile

You can prevent all users that belong to a specific profile from being able to personalize their pages.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Profiles**, and then choose the related link.
2. Select the profile in the list that you want to modify.
3. Select the **Disable personalization** check box, and then choose the **OK** button.

## Clear user personalizations

Clearing page personalization changes the page back to its original layout before any personalization was made. There are two ways to clear the personalizations that users have made to pages: using the **Delete User Personalization** page and using the **User Personalization Card** page.

### Clear user personalizations by using the Delete User Personalization page

The **Delete User Personalization** page enables you to clear personalizations on a per-page basis for each user individually.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete User Personalization**, and then choose the related link.

    The page lists all the pages that have been personalized and the user it belongs to.

    >[!NOTE]
    > A check mark in the **Legacy Personalization** columns indicates that the personalization was done in an older version of [!INCLUDE[d365fin](includes/d365fin_md.md)], which handled personalization different than it does now. Users who try to personalize these pages are locked from doing so unless they choose to unlock the page. For more information, see [Why a page is locked from personalizing](ui-personalization-locked.md).

2. Select the entry that you want to delete, and then choose the **Delete** action.

    The user will see the changes the next time they sign-in.

### Clear user personalizations by using the User Personalization Card page

The **User Personalization Card** page enables you to clear the personalization on all pages for specific user. This requires write permission to Table 2000000072 **Profile**.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Personalization**, and then choose the related link.

    The **User Personalization** page lists all users who potentially have personalized pages. If you cannot find a user in the list, this means that they do not have any personalized pages.

2. Select the user from the list, and then choose the **Edit** action.

3. On the **Actions** tab, choose **Clear Personalized Pages**.

    The user will see the changes the next time they sign-in.

## See Also
[Personalizing Your Workspace](ui-personalization-user.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Changing Basic Settings](ui-change-basic-settings.md)  
[Changing Which Features are Displayed](ui-experiences.md)  
