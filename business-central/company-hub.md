---
title: Manage Work Across Multiple Companies in the Company Hub
description: Use the Business Central company hub to view company summaries, open connected companies, and prioritize assigned tasks across online environments.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords: accountant, accounting, financial report
ms.search.form: 1151, 1154, 1165, 1166
ms.date: 11/10/2026
ms.author: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Manage work across multiple companies in the Company Hub

Some people work in multiple companies in [!INCLUDE [prod_short](includes/prod_short.md)], and some also work in more than one organization, such as external accountants, or employees and managers of corporations with multiple subsidiaries. For these users, and many others, the company hub serves as a landing page that gives a financial overview across companies and environments. It provides users with a tool for managing work across the various environments that they work in, across companies, environments, and regions.  

You can access the company hub by switching to the **Company Hub** role in **My Settings**, or by opening the **Company Hub** page directly. You can do the same work in both places, but actions are placed slightly different in menus.  

:::image type="content" source="media/company-hub.png" alt-text="Shows the company hub page that lists all companies." lightbox="media/company-hub.png":::

> [!NOTE]
> You can connect the company hub to as many companies as you need. However, you can only connect the company hub to companies that are hosted in [!INCLUDE [prod_short](includes/prod_short.md)] online.

## Company Hub home page

If you use the **Company Hub** role, your home page shows a list of connected companies, including key performance indicator (KPI) data and links to open each company. <!--You can customize the dashboard to show the data points that you want to see by adding or removing columns. For example, you might want to see taxes that are due, how many open sales documents each company has, or the number of purchase invoices that are due next week. You can configure the view to suit your needs. If you have added many companies, you can use filters to sort your view.--> Choose the **Company Hub** action to open the company hub, where you can work more closely with each company.

> [!TIP]
> To access a specific company in [!INCLUDE [prod_short](includes/prod_short.md)], choose the name of the company, or choose the **Go To Company** menu item. The company opens in a new browser tab. You might need to sign in.

:::image type="content" source="media/company-hub-company-list-actions.png" alt-text="Actions for a company that is listed in the company hub.":::

You can add new companies, such as when you get a new client, or when your corporation adds a new subsidiary. Learn more in [Add Companies to Your Company Hub](company-hub-add-company.md).  

> [!TIP]
> To refresh the data in the company hub, you must have access to the data in the companies that the data comes from.

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

In [!INCLUDE [prod_short](includes/prod_short.md)], you can assign tasks to yourself and others, and others can assign tasks to you. The company hub gives you an overview of assigned tasks for each company. Choose **My User Tasks** on the **Home** page to see incomplete tasks assigned to you.

<!--In the client company, you also have cues that call out tasks assigned to you in this particular client.  -->

### My user tasks

The **My User Tasks** list helps you prioritize your day by showing more information about tasks assigned to you across all your companies.  

You can sort by due date, for example, or any other type of data that helps you prioritize your day. By default, the list shows incomplete tasks that are assigned to you. You can add filters to only show tasks that are marked as high priority, for example.

To pick up a task, select its **Title** in the list of pending user tasks to open the linked page. You can also use **Go To Company** to open the user task list in the source company.

When you have completed a task, select **Mark Task Complete**.

Learn more in [Environment links](company-hub-add-company.md#environment-links) for information about companies and environments.

## Access the company hub

[!INCLUDE [2023rw1-sec-group-short](includes/2023rw1-sec-group-short.md)]

To access the company hub, you need the **D365 COMPANY HUB** permission set or equivalent permissions. An administrator can assign permissions directly or through a security group. You must also have access to the connected companies that you want to open or refresh. Learn more in [Create Users According to Licenses](ui-how-users-permissions.md).

> [!IMPORTANT]
> Your company overview shows links assigned to you and any sample entries. A company link doesn't grant access to that company's data. Your permissions in the connected company determine which data you can access and refresh.

If you can't find the company hub, and you know that you have been granted access to it, then check with your administrator if the company hub is listed in the **Extension Management** page. Learn more in [Customizing Business Central Using Extensions](ui-extensions.md).  

## Set up the company hub

To start using the company hub, you must add one or more companies to your dashboard. Learn more in [Add Companies to Your Company Hub](company-hub-add-company.md).  

But to add a company, you must have been given access to one or more instances of [!INCLUDE [prod_short](includes/prod_short.md)] in addition to the company that you use the company hub in.  

For example, if you're an accountant, your clients can invite you to their [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more in [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant).  

Your administrator must set up your access in the connected environment and assign the permissions you need in each company. Learn more in [Create users according to licenses](ui-how-users-permissions.md).

## Related information

[Add companies to your company hub](company-hub-add-company.md)  
[Accountant Experiences in Business Central](finance-accounting.md)  
[The Company Hub for Business Central Extension](ui-extensions-company-hub.md)  
[Change Basic Settings](ui-change-basic-settings.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
