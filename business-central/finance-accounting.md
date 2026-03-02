---
title: Accountant experiences in Business Central
description: Learn about the Accountant Role Center and the Company Hub that support internal and external accountants in the client company.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: accountant, accounting, financial report
ms.search.form: 100, 1156, 1157, 1314, 1315, 1316, 9027
ms.date: 06/12/2025
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.custom:
  - bap-template
  - sfi-image-nochange
---
# Accountant experiences in Business Central

Any business must do its books and sign off on the accounting. Some businesses employ an external accountant, and others have an accountant on staff. No matter what type of accountant you are, you can use the **Accountant** Role Center as your Home in [!INCLUDE[prod_short](includes/prod_short.md)]. From here, you can access all pages that you need in your work.  

## Accountant Role Center

The Role Center is a dashboard with activity tiles that show you real-time key figures and give you quick access to data. The ribbon at the top of the page gives you access to more actions. For example, to open financial reports and statements in Excel. In the navigation bar at the top, you can quickly switch between the lists you use most often. Here, there are other areas, such as **Posted Documents** with the various types of documents that the company posted.  

If you're new to [!INCLUDE[prod_short](includes/prod_short.md)], select **Product Videos** to watch videos or **Get Started** for a tour of key areas in the Role Center.

## Company Hub

If you work in multiple [!INCLUDE [prod_short](includes/prod_short.md)] companies, use the **Company Hub** page to keep track of work. For more information, see [Manage Work across Multiple Companies in the Company Hub](company-hub.md).  

## <a name="inviteaccountant"></a>Inviting a third-party accountant to your [!INCLUDE[prod_short](includes/prod_short.md)]

If a third-party accountant manages your books and financial reporting, your administrator can invite them to your [!INCLUDE[prod_short](includes/prod_short.md)] so they can work with you on your fiscal data. Both the Premium and Essentials [!INCLUDE[prod_short](includes/prod_short.md)] licenses let you procure up to three **External Accountant** licenses per customer tenant. The licenses are free, but you do need to procure them like you would other licenses. To learn more about licensing, download the [Microsoft Dynamics 365 Business Central Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544).

After your accountant can access your [!INCLUDE[prod_short](includes/prod_short.md)], they can use the **Accountant** Role Center for easy access to the pages for their work. They can also use the company hub in their own [!INCLUDE [prod_short](includes/prod_short.md)] to manage their work. Learn more in [Manage Work across Multiple Companies in the Company Hub](company-hub.md).  

> [!Video https://learn-video.azurefd.net/vod/player?id=7ba6427f-cdf0-480d-8c98-b51f65437146]

It's easy to invite your external accountant. In [!INCLUDE [prod_short](includes/prod_short.md)], open the **Users** page, and then select the **Invite external accountant** action. [!INCLUDE [prod_short](includes/prod_short.md)] prepares an email for you. Just add your accountant's work email, and send the invitation.  

> [!Note]  
> This action requires that you set up email in your [!INCLUDE [prod_short](includes/prod_short.md)] to use SMTP. Learn more in [Set Up Email](admin-how-setup-email.md).  

> [!IMPORTANT]  
> The accountant's email address must be a work address based on Microsoft Entra ID. If the accountant uses another type of email, the invitation can't be sent.
>
> This task requires access to managing users and licenses in Microsoft Entra ID. The user who sends this invitation must be assigned at least the [User Administrator](/entra/identity/role-based-access-control/permissions-reference#user-administrator) role in the Microsoft 365 admin center. Learn more in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) in the Microsoft 365 admin content.  

### Add your accountant to your Microsoft 365 tenant

If your admin or reselling partner prefers not to use the **Invite External Accountant** guide, you can add an external user to the Microsoft Entra tenant used by [!INCLUDE [prod_short](includes/prod_short.md)] and assign them the *External Accountant* license. You can add a user using the Microsoft 365 admin center, Microsoft Entra admin center, or Azure portal. The following procedure uses the Microsoft admin center. Learn about using the Microsoft Entra admin center at [Quickstart: Add a guest user and send an invitation](/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal).

#### Add your accountant as a guest user

1. Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) as at least a [User Administrator](/entra/identity/role-based-access-control/permissions-reference#user-administrator).
1. In the navigation pane, select **Users**.
1. On the **Users** page, select **New user**, and then **Invite external user**.
1. On the **Invite external user** page, add the accountant's email address and other information about them.  

   Optionally, include a personal welcome message to let the accountant know that you're adding them to your [!INCLUDE[prod_short](includes/prod_short.md)].

1. When you're finished, select **Review + Invite**.
1. Review the information, and then choose **Invite**.

After you send the invitation, the external user receives an email invitation to join your organization. After they accept the invitation, the user account is added as a guest.

Next, assign the guest user a license to [!INCLUDE[prod_short](includes/prod_short.md)].

#### Give your accountant access to your [!INCLUDE[prod_short](includes/prod_short.md)]

1. In the [Microsoft admin center](https://admin.microsoft.com), **Users** > **Guest users**.
1. Select the accountant's guest user account in the list, then select **Manage product licenses** to open the guest user profile pane.
1. Under **Licenses and apps**, select **Dynamics 365 Business Central External Accountant** license.  

   If this license isn't available, contact your reselling partner to add the license to your subscription.

   Specifically for evaluation purposes in a trial tenant, you can use an available **Dynamics 365 Business Central for IWs** license instead. However, you can't use this type of license if you already purchased [!INCLUDE[prod_short](includes/prod_short.md)].
1. Select **Save changes**.

If successful, the license is assigned to the guest user, and the guest account is created.

### Import the new user into [!INCLUDE[prod_short](includes/prod_short.md)]

The accountant receives an email notifying them that they have access to your Microsoft Entra ID. Next, give them access to the correct company in [!INCLUDE[prod_short](includes/prod_short.md)].

#### Add the accountant to the correct company

1. Sign in to [Business Central](https://businesscentral.dynamics.com).
1. Open company that you want to give the accountant access to. Learn more in [Switching to Another Company or Environment](ui-organization-switch.md).
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Users**, and then select the related link.  
1. Select the **Get New Users from Microsoft 365** action.

This action imports the user account that you created in the Azure portal to the company. Learn more in [To add a user in Business Central](ui-how-users-permissions.md#adduser).  

If you want to give access to multiple companies, then you must sign in to each company and repeat this process. Alternatively, you can update the permission groups for the accountant's user profile in [!INCLUDE[prod_short](includes/prod_short.md)], such as assigning them the *D365 Bus Premium* user group. Learn more in [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

### Inform your external accountant how to sign in to Business Central

Unlike internal users who access Business Central using the common URL `https://businesscentral.dynamics.com`, guest users must use the fully qualified domain name. The fully qualified domain name has the format `https://businesscentral.dynamics.com/<tenant ID or domain name>`, such as `https://businesscentral.dynamics.com/aaaabbbb-0000-cccc-1111-dddd2222eeee` or `https://businesscentral.dynamics.com/contoso.com`.

Guest users can sign in using two methods. They can open their browser, enter the fully qualified domain name in the address bar, and sign in using their username and password. Alternatively, they can:

1. Enter `https://businesscentral.dynamics.com` in the browser address bar.
1. Select **Sign in options**.
1. Select **Sign in to an organization**.
1. Enter the domain name of your organization, for example `contoso.com`, and then select **Next**.
1. Sign in using their username and password.

Learn more in [B2B collaboration invitation redemption](/entra/external-id/redemption-experience).

## Related information

[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Work with Dimensions](finance-dimensions.md)  
[Analyzing Financial Statements in Excel](finance-analyze-excel.md)  
[Manage Work across Multiple Companies in the Company Hub](company-hub.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Setting Up Cash Flow Analysis](finance-setup-cash-flow-analyses.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
