---
title: Business Central accountant experience | Microsoft Docs
description: Learn about the accountant portal for Business Central and the Accountant Role Center that supports internal and external accountants in the client company.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting, financial report
ms.date: 12/02/2019
ms.author: edupont

---
# Accountant Experiences in [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]
Any business must do its books and sign off on the accounting. Some businesses employ an external accountant, and others have an accountant on staff. No matter which type of accountant you are, you can use the **Accountant** Role Center as your Home in [!INCLUDE[d365fin](includes/d365fin_md.md)]. From here, you can access all pages that you need in your work.  

## Accountant Role Center
The Role Center is a dashboard with activity tiles that show you real-time key figures and give you quick access to data. In the ribbon at the top of the page, you have access to more actions, such as opening the most commonly used financial reports and statements in Excel. In the navigation bar at the top, you can quickly switch between the lists you use most often. Here, you will see other areas, such as **Posted Documents** with the various types of documents that the company has posted.  

If you are new to [!INCLUDE[d365fin](includes/d365fin_md.md)], you can launch a list of videos right from your Role Center. You can also launch a **Getting Started** tour that points out key areas.  

## <a name="inviteaccountant"></a>Inviting Your External Accountant to Your [!INCLUDE[d365fin](includes/d365fin_md.md)]
If you use an external accountant to manage your books and financial reporting, you can invite them to your [!INCLUDE[d365fin](includes/d365fin_md.md)] so they can work with you on your fiscal data.

Once your accountant has gained access to your [!INCLUDE[d365fin](includes/d365fin_md.md)], they can use the **Accountant** Role Center that gives easy access to the most relevant pages for their work.  

We have made it easy for you to invite your external accountant. Simply open the **Users** page, and then choose the **Invite External Accountant** action in the ribbon. An email is made ready for you, just add your accountant's work email, and send the invitation.  
> [!Note]  
> This requires that you have set up SMTP email. For more information, see [Set Up Email](admin-how-setup-email.md).   

![Invite your accountant](./media/finance-invite-accountant/invite-accountant.png)

> [!IMPORTANT]  
> The accountant's email address must be a work address that is based on Azure Active Directory. If the accountant uses another type of email, then the invitation cannot be sent.  

### Behind the scenes
[!INCLUDE[d365fin](includes/d365fin_md.md)] includes three licenses of type External Accountant. If your company use an external accountant, you can give access to your [!INCLUDE[d365fin](includes/d365fin_md.md)] by assigning them such a license. For more information about licensing, see the [Microsoft Dynamics 365 Busincess Central Licencing Guide](https://go.microsoft.com/fwlink/?LinkId=871590). 

If your subscription still has an available license, your administrator or reselling partner can add external user via Azure Portal and assign this user the External Accountant license. For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).

You can then invite the accountant from inside [!INCLUDE[d365fin](includes/d365fin_md.md)] by using the **Invite External Accountant** assisted setup guide. However, because this task requires access to managing users and licenses in Azure Active Directory, the user who sends this invitation must be assigned the **Global admin** role or **User admin** role in the Office 365 admin center. For more information, see [About admin roles](/office365/admin/add-users/about-admin-roles) in the Office 365 admin content. 

## Accountant Hub
If you are an accountant with several clients, you can use [!INCLUDE[d365acc_long](includes/d365acc_long_md.md)] for a better overview of your clients. From there, you can access each client's tenant in [!INCLUDE[d365fin](includes/d365fin_md.md)] and use the Accountant Role Center as described above. For more information see [Welcome to [!INCLUDE[d365acc_long](includes/d365acc_long_md.md)]](/dynamics365/accountants/index).  

> [!NOTE]
> [!INCLUDE [d365acc_long_md](includes/d365acc_long_md.md)] is currently in public preview in a limited number of markets.

## See Also
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Working with Dimensions](finance-dimensions.md)  
[Analyzing Financial Statements in Excel](finance-analyze-excel.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Setting Up Cash Flow Analysis](finance-setup-cash-flow-analyses.md)  
[Welcome to [!INCLUDE[d365acc_long](includes/d365acc_long_md.md)]](/dynamics365/accountants/index)  
[Dynamics 365 - Accountant Hub on Microsoft.com](https://www.microsoft.com/dynamics365/financial-insights-for-accountants)  
