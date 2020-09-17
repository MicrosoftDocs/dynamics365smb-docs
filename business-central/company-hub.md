---
title: Manage Work across Multiple Companies in the Company Hub
description: Learn about the company hub in Dynamics 365 Business Central that you use to manage your work across multiple companies.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: accountant, accounting, financial report
ms.date: 09/14/2020
ms.author: bholtorf
---

# Manage Work across Multiple Companies in the Company Hub

Some people work in multiple companies in [!INCLUDE [prodshort](includes/prodshort.md)], and some also work in more than one organization, or *tenant*, such as external accountants, or employees of corporations with multiple subsidiaries.<!-- (e.g. Internal Accountant, Different Managers, CEO and etc…)--> For these users, and many others, the company hub serves as a landing page for managing work across the various environments that they work in, across companies, environments, and regions.  

## Company hub home page

From the company hub landing page, you see a list of companies that you have access to, including information about key point of interest (KPI) data, and links to open each company. You can customize the dashboard to show the data points that you want to see by adding or removing columns. For example, you might want to see taxes that are due, how many open sales documents each company has, or the number of purchase invoices that are due next week. You can configure the view to suit your needs. If you have added many companies, you can use filters to sort your view.  

> [!TIP]
> To access a specific company in [!INCLUDE [prodshort](includes/prodshort.md)], choose the **Go To Company** menu item - you are logged in automatically.

You can add new companies, such as when you get a new client, or when your corporation adds a new subsidiary.

## Company details

You can see more information about each company by choosing the name of the company that you want to learn more about. This opens the **Company Details** pane, where you can see additional information, such as the following:  

* Cash account balances  
* Cash flow forecast  
* Overdue purchase invoices  
* Overdue sales invoices  

> [!TIP]
> You can launch predefined Excel workbooks from the **Reports** tab in the ribbon. These Excel workbooks are designed as ready-to-print key financial statements and reports, but you can also modify them to fit your needs. For more information, see [Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md).  

Otherwise, close the details pane and continue to the next company.  

## Assigned tasks

In [!INCLUDE [prodshort](includes/prodshort.md)], you can assign tasks to yourself and others, and others can assign tasks to you. Your dashboard in the company hub gives you an overview of assigned tasks for each company, and you can also access a list of all assigned tasks by choosing **My User Tasks** on the **Home** page.  

In the client company, you also have cues that call out tasks assigned to you in this particular client.

### My user tasks

The **My User Tasks** list helps you prioritize your day by showing more information about tasks assigned to you across all your companies.  

You can sort by due date, for example, or any other type of data that helps you prioritize your day. By default, the list shows all tasks that are assigned to you, but you can set up filters to only show tasks that are marked as high priority, for example.  

To pick up a task, simply choose it from the list of pending user tasks. In the ribbon, the link **Go to Task Item** opens the page where you can do the work.  

When you have completed a task, simply mark it as completed.  

For more information about companies and environments, see [Environment links](company-hub-add-company.md#environment-links).  

## Get the company hub

You can access the company hub in two different ways:

* A dedicated role center
* A page run from the page search

In both cases, you must make sure that the *Company Hub* extension is available in your [!INCLUDE [prodshort](includes/prodshort.md)]. The company hub is available by default in [!INCLUDE [prodshort](includes/prodshort.md)] trials, and you can add it to your paid [!INCLUDE [prodshort](includes/prodshort.md)] from the **Extension Management** page. For more information, see [Customizing Business Central Using Extensions](ui-extensions.md).  

## Set up the company hub

To start using the company hub, you must add one or more companies to your dashboard. For more information, see [Add Companies to Your Company Hub](company-hub-add-company.md).  

But to add a company, you must have been given access to one or more instances of [!INCLUDE [prodshort](includes/prodshort.md)] in addition to the company that you use the company hub in.  

For example, if you are an accountant, your clients can invite you to their [!INCLUDE [prodshort](includes/prodshort.md)]. For more information, see [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant).  

Administrators can use the same assisted setup guide to add you to their [!INCLUDE [prodshort](includes/prodshort.md)], or they can add you to the relevant Azure AD account in the Microsoft 365 admin center. For more information, see [Manage users and groups](/microsoft-365/admin/add-users/?view=o365-worldwide&preserve-view=true).  

You switch between countries using the **My Settings** page.

## See also

[Add companies to your company hub](company-hub-add-company.md)  
[Accountant Experiences in Business Central](finance-accounting.md)  
[The Company Hub for Business Central Extension](ui-extensions-company-hub.md)  
