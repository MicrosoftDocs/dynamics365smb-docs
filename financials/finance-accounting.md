---
title: Financials accountant experience | Microsoft Docs
description: Learn about the accountant portal for Dynamics 365 for Financials and the Accountant Role Center that supports internal and external accountants in the client company.
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting, financial report
ms.date: 08/16/2017
ms.author: edupont

---
# Accountant Experiences in [!INCLUDE[d365fin](includes/d365fin_md.md)]
Any business must do its books and sign off on the accounting. Some businesses employ an external accountant, and others have an accountant on staff. No matter which type of accountant you are, you can use the **Accountant** Role Center as your Home in [!INCLUDE[d365fin](includes/d365fin_md.md)]. From here, you can access all windows that you need in your work.  

## Accountant Role Center
The Role Center is a dashboard with activity tiles that show you real-time key figures and give you quick access to data. In the ribbon at the top of the window, you have access to more actions, such as opening the most commonly used financial reports and statements in Excel. In the navigation pane to the left, you can quickly switch between the lists you use most often. If you expand the **Home** menu in the navigation pane, you will see other areas, such as **Posted Documents** with the various types of documents that the company has posted.  

If you are new to [!INCLUDE[d365fin](includes/d365fin_md.md)], you can launch a list of videos right from your Home page. You can also launch a **Getting Started** tour that points out key areas.  

> [!NOTE]  
>  This functionality requires that the experience is set to **Suite**. For more information, see [Customizing Your Financials Experience](ui-experiences.md).  

### Get Invited to a Client's [!INCLUDE[d365fin](includes/d365fin_md.md)]
A company who use [!INCLUDE[d365fin](includes/d365fin_md.md)] can invite you to [!INCLUDE[d365fin](includes/d365fin_md.md)] as their external accountant. This requires that they have set up SMTP mail, so they might want to contact their [!INCLUDE[d365fin](includes/d365fin_md.md)] partner for assistance. For more information, see [Invite Your External Accountant](finance-invite-external-accountant.md). Also, we recommend that you give them the email address that you plan to use for your accounting work - that way, you can choose if you want to use *me@accountant.com* or *me@client.com*  

As a result, you will receive email from your client with a link to their [!INCLUDE[d365fin](includes/d365fin_md.md)]  

You can then access their financial data from the **Accountant** Role Center. If you use the accountant portal, you can also add that client to your list of clients in the accountant portal dashboard.  

## Accountant Portal
If you are an accountant with several clients, you can use the accountant portal as your dashboard for a better overview of your clients. From there, you can access each client's tenant in [!INCLUDE[d365fin](includes/d365fin_md.md)] and use the Accountant Role Center as described above.  

The accountant portal is a dedicated version of [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can get access to the dashboard by signing up from [Financials for Accountants on Microsoft.com](https://www.microsoft.com/en-us/dynamics365/financial-insights-for-accountants).  

> [!TIP]  
>  When you sign up for the accountant portal, you must specify your work email address, such as *me@accountant.com*. We recommend that you use the same email address when you work in your clients' [!INCLUDE[d365fin](includes/d365fin_md.md)], so that you can easily switch between clients.  

When you first log in to the accountant portal, the dashboard shows a sample client to help you get started. Once you are comfortable, you can remove that sample client.  

### Working with Individual Clients
The dashboard shows the most important information about each client.  
[![Accountant Portal](./media/ui-extensions-accportal/accountant-portal.png)](https://go.microsoft.com/fwlink/?linkid=851257)

The **Company Name** column lists all companies that your clients have in [!INCLUDE[d365fin](includes/d365fin_md.md)], and the **Client Name** column shows the names of your clients. You can customize the dashboard to show the data points that you want to see by adding or removing columns. For example, you might want to see taxes that are due, how many open sales documents each client has, or the number of purchase invoices that are due next week. You can configure the view to suit your needs. If you have many clients, you can use filters to sort your view.  

Next to the company name, the ellipsis (...) reveals a short menu:

-   Refresh the current company and get fresh data for the client  
-   Go to the client's company  
-   Select more companies  

Similarly, you can use the **Client Summary** drop-down menu to refresh all companies or open the currently selected company, for example.  

#### Company Details
You can see more information about your clients' data by choosing the name of the company that you want to learn more about. This opens the **Company Details** pane, where you can see additional information, such as the following:  

-   Cash account balances  
-   Cash flow forecast  
-   Overdue purchase invoices  
-   Overdue sales invoices  

[![Client company details in Accountant Hub ](./media/finance-accounting/accountant-company-details.png)]

Technically, you have now logged into your client's [!INCLUDE[d365fin](includes/d365fin_md.md)], and data you see is live data. If you want to take a closer look at the data, such as an overdue purchase invoice, choose the link, and you are taken to the client company.  

> [!TIP]  
>  You can launch predefined Excel workbooks from the **Reports** tab in the ribbon. These Excel workbooks are designed to be ready to print key financial statements and reports, but you can also modify them to fit your needs. For more information, see [Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md).  

Otherwise, close the details pane and continue to the next client.  

## Working in the Client Company
If you want to do more work for a client, you can do this in the Accountant Role Center in their [!INCLUDE[d365fin](includes/d365fin_md.md)] - simply choose the **Go To Client** menu item, and you are logged in automatically.  

In the client's company, you have view and modify the data that you need in your work. 

> [!NOTE]  
>  If you do not intend to return to this client in a few minutes, we recommend that you close the browser tab.  

### Adding Clients
You can add a client by using the **Clients** window, which you can open by choosing the **Manage Clients** action in the ribbon. Simply choose **New** and then fill in the fields.  

The data in the card for each client is specified by you, and you can change it as needed. However, the **Client URL** field is critical - this is how you can access each client's [!INCLUDE[d365fin](includes/d365fin_md.md)]. Use the **Test Client URL** action in the ribbon to test that you entered the right link. The URL that you must enter points at the client's [!INCLUDE[d365fin](includes/d365fin_md.md)], such as *https://mybusiness.financials.dynamics.com*. This URL is then used when you choose the **Go To Company** menu item.  

<!--If you have been invited to a client's [!INCLUDE[d365fin](includes/d365fin_md.md)] and signed in with your work account, then the client will be added to your dashboard in the accountant portal. -->

## See Also
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Working with Dimensions](finance-dimensions.md)  
[Analyzing Financial Statements in Excel](finance-analyze-excel.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Invite Your External Accountant to Your [!INCLUDE[d365fin](includes/d365fin_md.md)](finance-invite-external-accountant.md)  
[Financials for Accountants on Microsoft.com](https://www.microsoft.com/en-us/dynamics365/financial-insights-for-accountants)  
[Setting Up Cash Flow Analysis](finance-setup-cash-flow-analyses.md)  
