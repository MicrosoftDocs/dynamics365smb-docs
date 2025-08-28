---
title: Manage Work across Multiple Companies in the Company Hub
description: Learn about the company hub in Dynamics 365 Business Central that you use to manage your work across multiple companies.
author: brentholtorf
ms.topic: article
ms.search.keywords: accountant, accounting, financial report
ms.search.form: 1151, 1154, 1165, 1166
ms.date: 08/11/2025
ms.author: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Manage Work across Multiple Companies in the Company Hub

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Some people work in multiple companies in [!INCLUDE [prod_short](includes/prod_short.md)], and some also work in more than one organization, such as external accountants, or employees and managers of corporations with multiple subsidiaries. For these users, and many others, the company hub serves as a landing page that gives a financial overview across companies and environments. It provides users with a tool for managing work across the various environments that they work in, across companies, environments, and regions.  

You can access the company hub by switching to the **Company Hub** role in My Settings, or by opening the **Company Hub** page directly. You can do the same work in both places, but actions are placed slightly different in menus.  

[![Shows the company hub page that lists all companies.](media/company-hub.png)](media/company-hub.png#lightbox)  

> [!NOTE]
> You can connect the company hub to as many companies as you need. However, you can only connect the company hub to companies that are hosted in [!INCLUDE [prod_short](includes/prod_short.md)] online.

## Company hub home page

If you use the **Company Hub** role, your home page shows a list of companies that you have access to, including information about key point of interest (KPI) data, and links to open each company. <!--You can customize the dashboard to show the data points that you want to see by adding or removing columns. For example, you might want to see taxes that are due, how many open sales documents each company has, or the number of purchase invoices that are due next week. You can configure the view to suit your needs. If you have added many companies, you can use filters to sort your view.--> Choose the **Company Hub** action to open the company hub, where you can work more closely with each company.  

> [!TIP]
> To access a specific company in [!INCLUDE [prod_short](includes/prod_short.md)], choose the name of the company, or choose the **Go To Company** menu item - you're logged in automatically in a new browser tab.

:::image type="content" source="media/company-hub-company-list-actions.png" alt-text="Actions for a company that is listed in the company hub.":::

You can add new companies, such as when you get a new client, or when your corporation adds a new subsidiary. Learn more in [Add Companies to Your Company Hub](company-hub-add-company.md).  

> [!TIP]
> In order to refresh the data in the company hub, you must have access to the data in the companies that the data comes from.

<!--## Company details

In the **Company Hub** page, you can see more information about each company by choosing the name of the company that you want to learn more about. This opens the **Company Details** pane, where you can see additional information, such as the following:  

* Cash account balances  
* Cash flow forecast  
* Overdue purchase invoices  
* Overdue sales invoices  

> [!TIP]
> You can launch predefined Excel workbooks from the **Reports** tab in the ribbon. These Excel workbooks are designed as ready-to-print key financial statements and reports, but you can also modify them to fit your needs. For more information, see [Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md).  

Otherwise, close the details pane and continue to the next company.  -->

## Assigned tasks

In [!INCLUDE [prod_short](includes/prod_short.md)], you can assign tasks to yourself and others, and others can assign tasks to you. The company hub gives you an overview of assigned tasks for each company, and you can also access a list of all assigned tasks by choosing **My User Tasks** on the **Home** page.  

<!--In the client company, you also have cues that call out tasks assigned to you in this particular client.  -->

### My user tasks

The **My User Tasks** list helps you prioritize your day by showing more information about tasks assigned to you across all your companies.  

You can sort by due date, for example, or any other type of data that helps you prioritize your day. By default, the list shows all tasks that are assigned to you, but you can set up filters to only show tasks that are marked as high priority, for example.  

To pick up a task, choose it from the list of pending user tasks. In the ribbon, the link **Go to Task Item** opens the page where you can do the work.  

When you have completed a task, mark it as completed.  

Learn more in [Environment links](company-hub-add-company.md#environment-links) for information about companies and environments.

## Access the company hub

[!INCLUDE [2023rw1-sec-group-short](includes/2023rw1-sec-group-short.md)]

In order to access the company hub, you must have access through either the *D365 COMPANY HUB* user group or through the *D365 COMPANY HUB*  permission set. You must also have access to the companies that are listed in your company hub, which means that you must be a user in those companies. Learn more in [Create Users According to Licenses](ui-how-users-permissions.md).  

> [!IMPORTANT]
> The company hub is a company-wide list, so any user who is granted access to the company hub can see all companies in their own [!INCLUDE [prod_short](includes/prod_short.md)] tenant, and all KPIs for the companies that they have access to.

If you can't find the company hub, and you know that you have been granted access to it, then check with your administrator if the company hub is listed in the **Extension Management** page. Learn more in [Customizing Business Central Using Extensions](ui-extensions.md).  

## Set up the company hub

To start using the company hub, you must add one or more companies to your dashboard. Learn more in [Add Companies to Your Company Hub](company-hub-add-company.md).  

But to add a company, you must have been given access to one or more instances of [!INCLUDE [prod_short](includes/prod_short.md)] in addition to the company that you use the company hub in.  

For example, if you're an accountant, your clients can invite you to their [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more in [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant).  

Administrators can use the same assisted setup guide to add you to their [!INCLUDE [prod_short](includes/prod_short.md)], or they can add you to the relevant Microsoft Entra account in the Microsoft 365 admin center. Learn more in [Manage users and groups](/microsoft-365/admin/add-users/?view=o365-worldwide&preserve-view=true).  

## Related information

- [Add companies to your company hub](company-hub-add-company.md)  
- [Accountant Experiences in Business Central](finance-accounting.md)  
- [The Company Hub for Business Central Extension](ui-extensions-company-hub.md)  
- [Change Basic Settings](ui-change-basic-settings.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
