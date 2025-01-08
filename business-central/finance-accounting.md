---
title: Accountant experiences in Business Central
description: Learn about the Accountant Role Center and the Company Hub that support internal and external accountants in the client company.
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: accountant, accounting, financial report
ms.search.form: 100, 1156, 1157, 1314, 1315, 1316, 9027
ms.date: 11/28/2024
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Accountant experiences in Business Central

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Any business must do its books and sign off on the accounting. Some businesses employ an external accountant, and others have an accountant on staff. No matter what type of accountant you are, you can use the **Accountant** Role Center as your Home in [!INCLUDE[prod_short](includes/prod_short.md)]. From here, you can access all pages that you need in your work.  

## Accountant Role Center

The Role Center is a dashboard with activity tiles that show you real-time key figures and give you quick access to data. The ribbon at the top of the page gives you access to more actions. For example, to open financial reports and statements in Excel. In the navigation bar at the top, you can quickly switch between the lists you use most often. Here, you see other areas, such as **Posted Documents** with the various types of documents that the company posted.  

If you're new to [!INCLUDE[prod_short](includes/prod_short.md)], you can launch a list of videos right from your Role Center. You can also launch a **Getting Started** tour that points out key areas.  

## Company Hub

If you work in multiple [!INCLUDE [prod_short](includes/prod_short.md)] companies, you might find it useful to use the **Company Hub** page to keep track of work. Learn more in [Manage Work across Multiple Companies in the Company Hub](company-hub.md).  

## <a name="inviteaccountant"></a>Inviting a third-party accountant to your [!INCLUDE[prod_short](includes/prod_short.md)]

If a third-party accountant manages your books and financial reporting, your administrator can invite them to your [!INCLUDE[prod_short](includes/prod_short.md)] so they can work with you on your fiscal data. Both the Premium and Essentials [!INCLUDE[prod_short](includes/prod_short.md)] licenses let you procure up to three **External Accountant** licenses per customer tenant. The licenses are free, but you do need to procure them like you would other licenses. To learn more about licensing, download the [Microsoft Dynamics 365 Business Central Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544).

After your accountant can access your [!INCLUDE[prod_short](includes/prod_short.md)], they can use the **Accountant** Role Center for easy access to the pages for their work. They can also use the company hub in their own [!INCLUDE [prod_short](includes/prod_short.md)] to manage their work. Learn more in [Manage Work across Multiple Companies in the Company Hub](company-hub.md).  

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4Fnyw?rel=0]

It's easy to invite your external accountant. In [!INCLUDE [prod_short](includes/prod_short.md)], open the **Users** page, and then select the **Invite external accountant** action. [!INCLUDE [prod_short](includes/prod_short.md)] prepares an email for you. Just add your accountant's work email, and send the invitation.  

> [!Note]  
> This action requires that you set up email in your [!INCLUDE [prod_short](includes/prod_short.md)] to use SMTP. Learn more in [Set Up Email](admin-how-setup-email.md).  

> [!IMPORTANT]  
> The accountant's email address must be a work address that is based on Microsoft Entra ID. If the accountant uses another type of email, then the invitation cannot be sent.
>
> This task requires access to managing users and licenses in Microsoft Entra ID. The user who sends this invitation must be assigned at least the [User Administrator](/entra/identity/role-based-access-control/permissions-reference#user-administrator) role in the Microsoft 365 admin center. Learn more in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) in the Microsoft 365 admin content.  

### Add your accountant to your Microsoft 365 in the Azure portal

If your administrator or reselling partner doesn't want to use the **Invite External Accountant** guide, they can add an external user in Microsoft Azure portal and assign them the **External Accountant** license. Learn more in [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal).

#### Add your accountant as a guest user

1. Open the [Microsoft 365 admin center](https://admin.microsoft.com).
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

The accountant receives an email that notifies them that they have access to your Microsoft Entra ID. Next, you must give them access to the right company in [!INCLUDE[prod_short](includes/prod_short.md)].

#### To add the accountant to the right company

1. Open the [!INCLUDE[prod_short](includes/prod_short.md)] company that you want to give the accountant access to at [https://businesscentral.dynamics.com](https://businesscentral.dynamics.com).
2. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then chose the related link.  
3. Select the **Get New Users from Microsoft 365** action.

This action imports the user account that you created in the Azure portal to the company. Learn more in [To add a user in Business Central](ui-how-users-permissions.md#adduser).  

If you want to give access to multiple companies, then you must log into each company and repeat this process. Alternatively, you can update the permission groups for the accountant's user profile in [!INCLUDE[prod_short](includes/prod_short.md)], such as assigning them the *D365 Bus Premium* user group. Learn more in [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

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
