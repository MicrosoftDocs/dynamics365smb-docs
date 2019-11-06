---
title: Assign or Edit User Permissions  | Microsoft Docs
description: Describes how to add Office 365 users to Business Central, and then assign permissions, access rights, and security settings.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: access, right, security
ms.date: 11/06/2019
ms.author: sgroespe

---
# Manage Users and Licenses - Define who can sign in to Business Central
The process of managing licenses and users is different from online and on-premises deployments. The following  

## Users and license in online deployments
In [!INCLUDE[d365fin](includes/d365fin_md.md)] online number of users is defined in subscription added by partner to your tenant in Microsoft Partner Center. For more information, see [add a customer](https://docs.microsoft.com/partner-center/add-a-new-customer) and create [new subscriptions](https://docs.microsoft.com/partner-center/create-a-new-subscription)

To define who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)] the product licenses should be assigned to users accordingly to roles they should perform in [!INCLUDE[d365fin](includes/d365fin_md.md)]:
- Your company's Office 365 administrator can do it in [Microsoft 365 Admin center](https://admin.microsoft.com). For more information, see [Add Users to Office 365](https://aka.ms/CreateOffice365Users).  
- Partner can assign licenses in Microsoft 365 Admin center or in Microsoft Partner Center. For more information, see [assign licenses to users](https://docs.microsoft.com/partner-center/assign-licenses-to-users).
For more information, see: [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration) in the Administration section of the developer and ITPro content for [!INCLUDE[d365fin](includes/d365fin_md.md)].

Once users with [!INCLUDE[d365fin](includes/d365fin_md.md)] license are created in Office 365, they can be imported into the **Users** page in [!INCLUDE[d365fin](includes/d365fin_md.md)] by using the **Get Users from Office 365** action.

### To add a user in Business Central
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Choose the **Get Users from Office 365** action.

Any new user that has been created for your Office 365 subscription will be added on the **Users** page. Users are assigned permission sets depending on the license assigned to the user in Office 365. You can then proceed to assign granular permissions to users and to organize them in user groups. For more information, see [To assign permission sets to users](ui-define-granular-permissions.md#to-assign-permission-sets-to-users).

### To remove a user's access to the system
As an administrator, you can remove a user's access to the system by setting the **State** field to **Disabled**. All references to the user will be retained, but the user can no longer sign in to the system, and active sessions for the user will be terminated. To give the user access again, set the **State** field to **Enabled**.

You can remove, or unassign, licenses from users in Office 365 Admin Center. Users without license can no longer sign in to the system, see [Unassign licenses from users](https://docs.microsoft.com/office365/admin/manage/remove-licenses-from-users).

### Changing assigned license for user
Sometimes you may need to change license assigned to users. For example, you decided to use Service Management module and therefore you upgrade all Essential licenses to Premium. Another case is when user’s responsibility has changed and you need to replace Team Member license with Essential.
1. Change license in Office 365 Admin Center. For more information, see [Add Users to Office 365](https://aka.ms/CreateOffice365Users).
2. Sign is as an administrator in to [!INCLUDE[d365fin](includes/d365fin_md.md)].
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
4. On the **Users** page, choose the **Refresh all User Groups** action.
The users will be moved to a proper user group and the permission sets will be updated. For more information, see [To manage permissions through user groups](ui-define-granular-permissions.md#to-manage-permissions-through-user-groups).

> [!NOTE]
> All regular users in a solution must be assigned the same license, Essential or Premium.
> For information about licensing, see [Microsoft Dynamics 365 Business Central Licensing Guide](https://aka.ms/BusinessCentralLicensing).

## Users and license in on-premises deployments
For on-premises deployments number of licensed users is specified in license file (*.flf). Once administrator or partner uploads the licensing file, administrator can specify users who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)].
For on-premises deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)], the administrator creates, edits, deletes users directly from **Users** page.

### To edit or delete a user On-Premises
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to edit, and then choose the **Edit** action.
3. On the **User Card** page, change the information as necessary.    
4. To delete a user, select the user that you want to delete, and then choose the **delete** action.

> [!NOTE]
> For on-premises deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)], the administrator can choose between different credential authorization mechanisms for users. Then, when you create a user, you provide different information depending on the credential type that you are using in the specific [!INCLUDE[server](includes/server.md)] instance.<br /><br />
> For more information, see the [Authentication and Credential Types](/dynamics365/business-central/dev-itpro/administration/users-credential-types) in the Administration section of the developer and ITPro content for [!INCLUDE[d365fin](includes/d365fin_md.md)].

When users are created in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can then proceed to assign specific permissions to users through permission sets and to organize users in user groups for easy permission management. For more information, see [Define Granular Permissions](ui-define-granular-permissions.md).

## See Also
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Office 365 for business](https://aka.ms/CreateOffice365Users)  
[Microsoft Dynamics 365 Business Central Licensing Guide](https://aka.ms/BusinessCentralLicensing)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help
