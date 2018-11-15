---
title: Manage users and roles | Microsoft Docs
description: Learn how to manage users and Role Centers in Business Central.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: profiles, users
ms.date: 10/24/2018
ms.author: edupont

---
# Understanding Users, Profiles, and Role Centers

In [!INCLUDE[d365fin](includes/d365fin_md.md)], users are added by an administrator who also gives users access to the areas of [!INCLUDE[d365fin](includes/d365fin_md.md)] that they need in their work.  

Access to functionality is managed through *user groups* and *profiles*. As an administrator, you can add and remove users as part of your [!INCLUDE[d365fin](includes/d365fin_md.md)] subscription, and you can assign users permissions through user groups.  

## Adding Users

To add users in [!INCLUDE[d365fin](includes/d365fin_md.md)] online, your company's Office 365 administrator must first create the users in the Office 365 Admin Center. For more information, see [Add Users to Office 365 for business](https://aka.ms/CreateOffice365Users).

Then, the administrator can assign permissions to each user and groups of users. For more information, see [Managing Users and Permissions](ui-how-users-permissions.md).  

The most powerful permissions that a user can have is the SUPER permission set. Each company must have at least one user with this permission set, but it is a best practice to give each user permissions that match their work needs in [!INCLUDE[prodshort](includes/prodshort.md)] and not more than that. This helps ensure that users only have access to data that is relevant to their work, for example.  

> [!TIP]
> It's a best practice to make sure that the Office 365 administrator also has the SUPER permission set in [!INCLUDE[prodshort](includes/prodshort.md)] because that makes many administrative tasks easier, including setting up integration with other apps.

### Users of on-premises deployments

For on-premises deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)], the administrator can choose between different credential authorization mechanisms for users. Then, when you create a user, you provide different information depending on the credential type that you are using in the specific [!INCLUDE[server](includes/server.md)] instance. For more information, see the [Authentication and Credential Types](/dynamics365/business-central/dev-itpro/administration/users-credential-types) in the Administration section of the developer and ITPro content for [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## Profiles

The people in your company who have access to [!INCLUDE[d365fin](includes/d365fin_md.md)] are all assigned a *profile* that gives them access to a *Role Center*.

Profiles are collections of [!INCLUDE[d365fin](includes/d365fin_md.md)] users who share the same Role Center. A Role Center is the entry point and home page for [!INCLUDE[d365fin](includes/d365fin_md.md)] that gives you quick access to your most important tasks and displays various insights and key performance indicators (KPIs) about your work.  

> [!NOTE]  
>  In the current version of [!INCLUDE[d365fin](includes/d365fin_md.md)] online, you cannot add, edit, or delete profiles.  

### <a name="CreateProfile"></a>Create a profile

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Profile List**, and then choose the related link.  

2.  On the **Profile List** page, choose the **New** action to open the **New Profile Card** window.  

3.  In the **Profile ID** field, enter a name that describes the intended role of the users.  

4.  In the **Description** field, enter a description of the Profile ID, for example, **Order Processor**.  

5.  Set the **Role Center ID** field to the Role Center that you want to assign to the profile.  

The procedure for modifying an existing profile is the same, except you select an existing profile in the **Profile List** page instead of choosing the **New** action.  


### Copying a profile
Copying a profile can save you time if you want to use similar settings on a profile and you only want to change a few settings.

1.  Open the profile that you want to copy, and then choose the **Copy Profile** action.

2.  In **New Profile ID** field, enter a name for the profile that you want to copy.

3.  Set the **New Profile Scope** field to one of the following:

    - **System** to make the new profile available to all tenant databases that use the application.
    - **Tenant** to make the new profile available to just the current tenant database.
4. Choose the **OK** button when done.

### <a name="ExportImportProfile"></a>Exporting and importing profiles

You can export and import profiles as XML files to and from the a [!INCLUDE[d365fin](includes/d365fin_md.md)] database. Exporting and importing a profile can save you time when configuring the user interface because you reuse an existing profile configuration instead of having to configure a profile from scratch. If you have a profile that is configured in a [!INCLUDE[d365fin](includes/d365fin_md.md)] database and you would like to reuse all or some of the same profile configurations in another database, you can export the profile to an XML file. Then, you can import the profile XML file into the other database.

-   To export a profile, you can either choose the **Export Profiles** action from the **Profile List** or **Profile Card** page or you can search for and open the **Export Profiles** page. Save the XML file to a location on your computer or network.

-   To import a profile, you can either choose the **Import Profile** action from the **Profile List** page, or you can search for and open the **Import Profiles** page. 

    > [!NOTE]  
    >  You cannot import a profile that already exists in the database, even though the XML file is named differently or has different content. You must delete the existing profile before you can import the new profile.


## Configuration and Personalization
<!--The concept of UI customization in [!INCLUDE[d365fin](includes/d365fin_md.md)] is divided in two:  

-   Configuration, performed by the administrator  

-   Personalization, performed by users  

The administrator configures the user interface for multiple users by customizing the user interface for a profile that the users are assigned to.  -->

Users personalize the user interface of their personal version by customizing the user interface under their own user logon. This personalization can be deleted by the administrator. For more information, see [Personalizing Your Workspace](ui-personalization-user.md).  

## See Also  
[Managing Users and Permissions](ui-how-users-permissions.md)  
[Managing Personalization as an Administrator](ui-personalization-manage.md)  
[Personalizing Your Workspace](ui-personalization-user.md)  
