---
title: Access with Microsoft 365 Licenses FAQ
description: Get answers to common questions about accessing Business Central with Microsoft 365 licenses. 
author: mikebc
ms.author: mikebc
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: faq
ms.date: 09/28/2023
ms.custom: bap-template 
---
# Access with Microsoft 365 Licenses FAQ

[!INCLUDE [2023rw1-sec-group-short](includes/2023rw1-sec-group-short.md)]

Users can access Business Central data in Microsoft Teams using their Microsoft 365 license. This article answers frequently asked questions from administrators, consultants and others. Developers should refer to the Developer FAQ. For questions about integrating Business Central with Microsoft Teams, go to [Teams FAQ](teams-faq.md).

## [Permissions](#tab/permissions) 

### Can I proactively configure different starting permissions for different groups of users?

Not at this time. Business Central only allows configuring one group of permissions that are assigned to all Microsoft 365 users when they sign into Business Central for the first time.

### Can I proactively configure permissions, profiles, and settings for individual users before they sign in?

Yes. It can be achieved through security groups. By applying a security group to an environment, you define the total set of users that have access to that environment. This security group can include users with a Business Central license and users with a Microsoft 365 license. When you next update users from Microsoft 365 in the **Users** list, the Microsoft 365 user records will be created. You can then assign user groups, permissions, profiles, and other settings before they've signed in.

### After a user signs in, can I change which objects they have access to?

Yes. After a user has signed in for the first time and their user record has been provisioned, administrators manage those users just like any other Business Central user. For example, they can add or remove permissions to different objects. If you change the permission sets assigned to the Microsoft 365 license in the License Configuration page, the change will only affect the next users that sign in for the first time.

### How do I prevent access to sensitive tables?

Business Central offers a powerful and flexible permission model where administrators can define permission sets that grant access to specific objects, business processes or entire roles. To prevent access to sensitive tables, you can create custom permission sets that exclude permission to sensitive objects. For more information about exclude permissions, see [Create a permission set](ui-define-granular-permissions.md).  

### Instead of customizing the License Configuration, can I customize a user group?

Yes. Adding permission sets to the Microsoft Teams Internal Users user group in Business Central, has the same net effect as adding permission sets to the Microsoft 365 license, as long as the Microsoft 365 license continues to map to this user group. This approach has the added benefit that permission sets are always synchronized with members of the group whenever you modify the user group.

### When a Business Central user shares a record in Teams, do they grant new permissions?

No. This action isn't the same as sharing a link to a SharePoint document where the person sharing the document can choose to grant permission to others. In Business Central, only administrators can configure and assign permissions. When compared to sharing SharePoint documents, it's the equivalent of choosing the option to “Share to people with existing access”.

### Does this feature support row-level security?

Yes. Even though a person accessing a record in Teams with their Microsoft 365 license may have the correct table and page object permissions, row-level permissions will be enforced if it' been implemented for that table.  

### If I configure permissions that include write access, will users be able to write in Teams?

If you configure Business Central to assign a permission set that includes insert, modify, or delete access to one or more objects, users with that permission set will still not be able to write in Teams when they only have a Microsoft 365 license. The Business Central service enforces read-only access no matter what insert, modify, or delete permission you assign.  

Even though Business Central provides this level of protection, we still recommend that you avoid permission sets with write access. Doing so prevents issues further downstream when users change role or acquire new licenses.  

## [Setup and Configuration](#tab/setup)

### Why is the setting to enable access not available for my environment?

Enabling access with Microsoft 365 licenses is only available for Business Central environments of platform version 21.1 or later. When your environment is upgraded to this minimum version, the setting automatically becomes available. To check the version of your environment, go to the environment details page for the environment in the Business Central admin center. Or, sign in to the environment, and go to the **Help & Support** page from the **Help** menu.

### Can I access Business Central on premises with Microsoft 365 licenses?

No, it's not supported. Business Central displays an error when users try to access Business Central on premises records in Teams.

### What is the Employee profile?

The **Employee** profile displayed in the **Profiles (Roles)** list page was introduced with Update 21.1. It's the default profile assigned to users that access Business Central with their Microsoft 365 license. This profile's intended for people in an organization who don't have a specific role in Business Central and only need to view data that was shared with them.

### What is the Teams Users user group?

The **Microsoft Teams Internal Users** group displayed in the **User Groups** page was introduced with Update 21.1. This group is the default user group assigned to users that access Business Central with their Microsoft 365 license. The user group's intended for people within the same organization where Business Central is hosted that collaborate in Microsoft Teams.  

### Do users that only have a Microsoft 365 license show up in the Users list in Business Central?

Yes. If you apply security groups to environments, those users will show up in the Users list after you use the Update Users from Microsoft 365 action from the **Users** list. If you don't apply security groups, user records appear in the Users list after the first time they access a Business Central record.

### Does this feature work for embed ISV solutions?

Yes. Users with only a Microsoft 365 license can also access records in environments that run under the *.bc.dynamics.com domain.

## [Licensing](#tab/license)

### Can a customer use this feature if they don't have Business Central?

Accessing Business Central with a Microsoft 365 license is intended for organizations that already subscribe to Business Central and operate one or more Business Central environments with licensed Business Central users. It provides no new functionality or use rights to Microsoft 365 customers that don't have a Business Central plan.

### How does this help me manage subscription costs in my organization?

To maximize productivity and streamline their operations, SMBs often purchase Dynamics 365 Business Central together with Microsoft 365. In which case, most people receive a Microsoft 365 license, but only specific roles or people receive a Business Central license. Business Central provides licensing flexibility so that customers pay only for what they need:

- Users requiring full access to Business Central are typically assigned a Business Central Essentials or Business Central Premium license. 
- Users requiring limited write access are typically assigned a Business Central Team Member license.
- All other employees across the organization that only need to occasionally read business data that is shared with them, can do so if they have a Microsoft 365 license. They don't have to be assigned a Team Member license. Other licensing options are available. For more information, download and read the [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).

### Is this 100% free of charge?
 
No. Accessing Business Central data in Microsoft Teams requires each user to have either a Business Central license or a Microsoft 365 license from the list of supported plans.

### Does this work with Microsoft 365 trials and Business Central trials?

Yes. If a user is assigned a Microsoft 365 license from a trial of a supported plan, they can also access Business Central records in Teams. It's then possible for customers to try Microsoft productivity and business apps working together, and allows partner salespeople and consultants to easily demonstrate this feature. For example, partners can provision their own Microsoft Entra tenants from [https://aka.ms/CDX](https://aka.ms/CDX) that include Microsoft 365 trials and Business Central trials for demonstrating Business Central.

### The list of licenses in Business Central shows a Microsoft 365 license. What's that?

The **License Configuration** page in Business Central displays the different types of licenses that can provide access to the Business Central service. In version 21, Microsoft added Microsoft 365 to this list as a new way to access Business Central. This list of licenses doesn't imply that your organization has purchased subscriptions to any of these licenses or your organization has enabled access through those licenses.

### Do I need to acquire a new type of Microsoft 365 license for this feature to work?  

Microsoft hasn't created new licenses or new plans to power this feature. This feature relies entirely on existing Microsoft 365 plans and licenses. If you already subscribe to one of the supported Microsoft 365 plans, then you already have this new use right. Learn more about the supported plans in [Business Central access with Microsoft 365 licenses](admin-access-with-m365-license.md#requirements-for-individual-users-to-access-data-in-teams). Otherwise, if you don't subscribe to Microsoft 365 today, you can sign up for Microsoft 365 Business Premium or similar plan. Learn more in [Try or buy a Microsoft 365 for business subscription](/microsoft-365/commerce/try-or-buy-microsoft-365).

### How do I find out which users have only a Microsoft 365 license?

There are multiple ways. In the Microsoft 365 admin center, go to the **Active Users** list and refer to the **Licenses** column. In Business Central, go to the **Users** list, choose any of the users and view the **Licenses** FactBox.  

### How do I filter the Users list in Business Central to see users that only have a Microsoft 365 license?

This task is currently not possible using a filter or list view. However, you can select a user in the list and view the Licenses FactBox that will include only Microsoft 365, if the user only has a Microsoft 365 license.

### What about users that have both a Microsoft 365 license and a Business Central license?

When multiple licenses are assigned to a user, the greater license use rights win over lesser license use rights when accessing Business Central. In this case, Business Central license entitles the user to more user rights. So, users can read and write Business Central records in Teams and access the Business Central web client in the browser, just like any other Business Central license-holder. If specific permission sets have been configured for the Microsoft 365 license, the user gets the configured permission sets combined with the permission sets from the Business Central license or that have already been assigned to the user.

### Is this licensing related to the Business Central Team Member license?

There's no relation between Business Central Team Member licenses and accessing Business Central in Microsoft Teams using Microsoft 365 licenses. Although Microsoft Teams and its documentation refer to people in a team as *team members*, it's a collective term for a group of Microsoft Teams users. It doesn't refer to Business Central licenses.

### Does Business Central enforce any of the constraints?

Yes, all of the platform constraints and minimum requirements, including licensing requirements, are enforced by the Business Central platform. This guides users with specific error messages to help them troubleshoot their setup, and prevent abuse. For example, if a user that only has a Microsoft 365 license attempts to access the Business Central web client in the browser, access will be denied and a guiding error message will be displayed. 

## [Usage](#tab/usage)
 
### Can I access records on Teams for iOS and Teams for Android? 

Currently, it isn't possible to access Business Central data on the Teams mobile using only a Microsoft 365 license. Microsoft is working on enabling this capability shortly. 

### How do users change their personal settings in My Settings? 

When a user accesses Business Central for the first time using only their Microsoft 365 license, their user settings such as language, time zone and regional settings are automatically set based on their operating system or browser settings. Administrators can modify these settings from Business Central for each user. 

### What determines the choice of language when you sign in for the first time? 

The language with which you experience Business Central is set based on various factors, including the Teams client through which you accessed Business Central the first time. For Teams desktop app, Teams for iOS and Teams for Android, the operating system language is applied. For Teams for the web, the browser language is applied. In all cases, the Teams language isn't considered. 

### Why can’t I activate some of the colored links in tabs and card details?

Actionable links on Business Central pages are often shown as a bold hyperlinks that can be activated to go elsewhere or run some operation. At a technical level, these links are typically implemented as field values with no caption that trigger some code and where the choice of style often reflects state. When users access Business Central pages with their Microsoft 365 license, the links are styled as if they're actionable. But they can't be activated because this license doesn't offer use rights to run actions.  

### Why can’t I activate page notification actions?

Contextual notifications shown on pages are often accompanied by actionable links. When users access Business Central pages with their Microsoft 365 license, these links are displayed, but can't be activated because this license doesn't offer use rights to run actions. At a technical level, these links are implemented as actions.

### Can Microsoft 365 users remove tabs?

Yes. Anyone in the chat or channel can remove tabs created by others. Removing a tab doesn't remove or affect data in Business Central, but the tab will be removed for all users in the chat or channel.

### If I can't filter, will I still see a filtered list that was created by others?

Users accessing Business Central with their Microsoft 365 license don't have the use rights to filter using the filter pane or apply list views. But, if another user has created a tab containing a filtered list page, Microsoft 365 users will also view those filters applied to the tab.

---

## Related information

[Overview of Business Central Access with Microsoft 365 licenses](admin-access-with-m365-license.md#minimum-requirements)  
[Set Up Access with Microsoft 365 Licenses](admin-access-with-m365-license-setup.md)  
