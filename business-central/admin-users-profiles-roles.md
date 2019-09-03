---
title: Manage users and roles | Microsoft Docs
description: Learn how to manage users and Role Centers in Business Central.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: profiles, users
ms.date: 09/04/2019
ms.author: sgroespe

---
# Managing Profiles (Roles)
The employees in your company who have access to [!INCLUDE[d365fin](includes/d365fin_md.md)] are all assigned a role that gives them access to a Role Center.

The technical representation of a role is a profile. Profiles are collections of [!INCLUDE[d365fin](includes/d365fin_md.md)] users who share the same role. A Role Center is the entry point, or home page, for [!INCLUDE[d365fin](includes/d365fin_md.md)] that gives the user quick access to their daily tasks and displays various insights and key performance indicators about their work.

On the **Profiles (Roles)** page, you create and manage profiles. Each profile has a card where you make various settings, such as the name of the role as users see it, which Role Center it uses, and whether users assigned the role can personalize their pages. Here, you also initiate page customizations for the profile.

## Users and Permissions
Before you can administrate users' profiles, the users must be created and added, through the Office 365 Admin Center. Then, you can assign permissions to each user or user group to define which features they are allowed to view and/or edit. For more information, see [Managing Users and Permissions](ui-how-users-permissions.md).

## To create a profile
If you cannot copy an existing profile, you can create a new one manually.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Profiles (Roles)**, and then choose the related link.  
2. On the **Profiles (Roles)** page, choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To activate a profile
When a profile is created, you can select different check boxes that define if, where, and how the profile and its information is made available to users.

1. On the **Profile (Role)** page, select the following check boxes:
    - **Enabled** to specify if the related role is visible in the **Available Roles** page for users to choose from.  
    - **Use as default profile** to specify the profile that applies to users who are not assigned a specific role.
    - **Disable personalization** to specify if users of the related role can personalize their workspace. Note that this applies to users of the profile only. In on-premises installations, you can make such as setting for all users in the system. For more information, see [To enable or disable personalization (on-premises only)](admin-users-profiles-roles.md#EnablePersonalization).
    - **Show in Role Explorer** to specify if menu items to business features included in the profile are displayed on the **My Business Central** page. For more information, see [Finding and Navigating Pages with the Role Explorer](ui-role-explorer.md).

## To copy a profile
To save time, you can create a new profile by copying an existing one. Copy one that has similar settings to the one you want to create.

1. On the **Profiles (Roles)** page, select the line for the profile that you want to copy, and then choose the **Copy profile** action.
2. Fill in the **Profile ID** and **Display Name** fields, and then choose the **OK** button.
3. On the **Profiles (Roles)** page, open the newly created profile card, and then edit other fields as necessary.

## To define user settings for a profile
On the **My Settings** page, users can define basic behavior of their account, such as the Role Center, the language, and which notifications they get. For more information, see [Change Basic Settings](ui-change-basic-settings.md).

As an administrator, you can define these setting for a profile to thereby apply the settings to all users of the related role.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Profiles (Roles)**, and then choose the related link.
2. Select the line for the profile that you want to change user settings for, choose the **Navigate** action, and then choose the **User Personalizations** action.
3. On the **User Personalizations** page, open the card for the user whose settings you want to change.
4. On the **User Personalization Card** page, edit the fields as necessary.

## To customize pages for a profile
You customize the workspace for a profile so that all users that are assigned the related role will see the customized pages. As an administrator, you customize the role's workspace by using the same functionality as users do when they personalize. For more information, see [Customize the Workspace for Profiles (Roles)](ui-personalization-manage.md).

## To export user-created profiles
You can export profiles that have been changed either by you by users, as indicated by **(User-creted)** in the **Source** field. The profile is exported to a zip file containing XML files that can be reused in other [!INCLUDE[d365fin](includes/d365fin_md.md)] companies.

* On the **Profiles (Roles)** page, choose the **Export User-Created Profiles** action.

A zip file is exported containg XML files for profiles where the **Source** field contains **(User-creted)**.

## To delete all personalizations made by a user
You can delete all changes that a user has made to pages that make up their workspace. This may be useful, for example, if an employee has changed role and no longer needs the personalizations. Clearing users' personalizations changes the page layout back to what is defined by the profile.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Personalizations**, and then choose the related link.

    The **User Personalizations** page lists all users who have made personalizations.

2. Open the card for a user whose personalizations you want to delete.
3. On the **User Personalization Card** page, choose the **Clear Personalized Pages** action, and then accept the message that appears.

The user will see the changes the next time they sign in.

## To delete personalizations for specific pages
You can delete changes that one or more users users have made to specific pages that make up their workspace. This may be useful, for example, if a popular if a changed business process means that a personalization must no longer be used by users. Clearing users' personalizations changes the page layout back to what is defined by the profile.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Page Personalizations**, and then choose the related link.

    The **User Page Personalizations** page lists all the pages that have been personalized and the user that they belong to.

    > [!Note]
    > A check mark in the Legacy Personalization columns indicates that the personalization was done in an older version of Business Central, which handled personalization different than it does now. Users who try to personalize these pages are locked from doing so unless they choose to unlock the page. For more information, see Why a page is locked from personalizing.

2. Select the line for the page personalization that you want to delete, and then choose the **Delete** action.

The user will see the changes the next time they sign-in.    

## <a name="EnablePersonalization"></a>To enable or disable personalization (On-Premises Only)

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

## See Also  
[Managing Users and Permissions](ui-how-users-permissions.md)  
[Customize the Workspace for Profiles (Roles)](ui-personalization-manage.md)  
[Personalize Your Workspace](ui-personalization-user.md)  
