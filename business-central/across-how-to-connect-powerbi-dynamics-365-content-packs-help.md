---
title: How to Connect Power BI to Business Central | Microsoft Docs
description: Getting insight, business intelligence, and KPIs from your Business Central data is easy with Power BI and the Business Central content packs.
author: SusanneWindfeldPedersen

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 04/03/2018
ms.author: solsen
redirect_url: admin-powerbi

---
# Connecting Power BI to Dynamics 365 Business Central Content Packs
Getting insights into your Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] data is easy with Power BI and the Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] content packs. Power BI retrieves your data then builds an out-of-the-box dashboard and reports based on that data.

You must have a valid account with Dynamics 365 and with Power BI. Also, you must download [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) if you wish to create your own Power BI reports. Power BI content packs require permissions to the tables where data is retrieved from. More details on the requirements are described below.  

## How to Connect
1. Select **Get Data** at the bottom of the left navigation pane.  
![Navigating to Get Data](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-get-data.png)

You may also get starting from within Dynamics 365 Business Edition. From the role center, navigate to **Report Selection** in the Power BI Role Center part. Select either **Service** or **My Organization** from the ribbon. When either of these actions are selected, you will be taken to either the Organization gallery in Power BI or to the services library in Power BI, which will also be filtered to only display content packs related to [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)].

2. In the **Services** box, select **Get**. This will open a window with the **AppSource** and **Apps for Power BI apps**.  
![Choose content packs from online services](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-online-services-get.png)
3. Select **Apps** from the **Apps for Power BI apps** tab, choose the **Microsoft Dynamics 365 Business Central** content pack that you want to use, and then select **Get it now**.  
![Select Dynamics 365 Business Central and select Get it now](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-dynamics365-for-financials-get-it-now.png)
4. When prompted, enter the name of *your company* in [!INCLUDE[d365fin_md](includes/d365fin_long_md.md)]. This is not the display name. The company name can be found on the 'Companies' page within your [!INCLUDE[d365fin_md](includes/d365fin_long_md.md)] instance. 
![Select Dynamics 365 Business Central and select Get it now](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-connect-to-d365-finance-and-operations-crm.png)
5. Once connected, a dashboard, report and dataset will automatically be loaded into your Power BI workspace. When completed, the tiles will update with data from your [!INCLUDE[d365fin_md](includes/d365fin_long_md.md)] company.
![Select Dynamics 365 Business Central  and select Get it now](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-workspace-dashboard-report-dataset.png)

## What Now?

- Try [asking a question in the Q&A box](https://docs.microsoft.com/en-us/power-bi/service-q-and-a) at the top of the dashboard.
- [Change the tiles](https://docs.microsoft.com/en-us/power-bi/service-dashboard-edit-tile) in the dashboard.  
- [Select a tile](https://docs.microsoft.com/en-us/power-bi/service-dashboard-tiles) to open the underlying report.  
- While your dataset will be scheduled to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**.

## System Requirements
To import your [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] data into Power BI, you need to have permissions to the web services used to retrieve data. The web services required for each content pack include:

## Role Center Reports

**Microsoft Dynamics 365 Business Central – CRM**
- Sales Opportunities
- Excel Template View Company
- Power BI Report Labels

**Microsoft Dynamics 365 Business Central – Finance**
- PowerBIFinance
- Excel Template View Company
- Power BI Report Labels

**Microsoft Dynamics 365 Business Central – Jobs**
- Job List
- Job Planning Lines
- Job Task Lines
- Power BI Report Labels
- Excel Template View Company

**Microsoft Dynamics 365 Business Central - Sales**
- Sales Dashboard
- Excel Template View Company
- Power BI Report Labels

## List Page Reports 

**Microsoft Dynamics 365 Business Central – Customers List**
- Item Sales by Customer
- Power BI Item Purchase List
- Power BI Item Sales List
- Sales Dashboard
- Power BI Customer List
- ExcelTemplateViewCompany
- Power BI Report Labels 

**Microsoft Dynamics 365 Business Central - General Ledger Entries List**
- Power BI GL Amount List
- Power BI GL Budgeted Amount
- ExcelTemplateViewCompany
- Power BI Report Labels

**Microsoft Dynamics 365 Business Central – Items List**
- Item Sales by Customer
- Power BI Item Purchase List
- Power BI Item Sales List
- Sales Dashboard
- ExcelTemplateViewCompany
- Power BI Report Labels

**Microsoft Dynamics 365 Business Central – Jobs List**
- Power BI Jobs List
- ExcelTemplateViewCompany
- Power BI Report Labels

**Microsoft Dynamics 365 Business Central – Purchase Invoices List**
- Power BI Purchase List
- ExcelTemplateViewCompany
- Power BI Report Labels

**Microsoft Dynamics 365 Business Central – Sales Orders List**
- Power BI Sales List
- ExcelTemplateViewCompany
- Power BI Report Labels


**Microsoft Dynamics 365 Business Central – Vendors List**
- Power BI Item Purchase List
- Power BI Item Sales List
- Power BI Vendor List
- ExcelTemplateViewCompany
- Power BI Report Labels

## Web Services
An easy way to find the web services is to search for web services in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. In the list make sure the Publish box is marked for the web services listed above.

## Troubleshooting
The Power BI dashboard relies on the published web services that are listed above, and it will show data from the demonstration company or your own company if you import data from your current finance solution. However, if something goes wrong, this section provides a workaround for the most typical issues.

### Incorrect Company Name  
A common mistake is to enter the company display name instead of the company name. To find the company name search for **Companies**. Then use the **Name** field when entering your company name.

### Incorrect User Name and Password  
The user name and password used to connect will be the same as what is used to connect to your Microsoft Office 365 account.  

The content packs also require that you have a Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] account. Once you enter your credentials, we will auto discover any Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] tenants you have access to. If you do not have a licensed or trial Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] account, you will receive an error message.

### The Key Didn't Match Any Rows in the Table
If you enter a non-valid company name during the connection process, you may get the error message "The key didn't match any rows in the table". Provide the correct company name and try connecting again.

## See Also
[Get started with Power BI](https://docs.microsoft.com/en-us/power-bi/service-get-started)  
[Power BI - Basic Concepts](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts)  
[Business Intelligence](bi.md)  
[Getting Started](product-get-started.md)  
[Importing Business Data from Other Finance Systems](upload-data.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finance](finance.md)  
[Setup Reporting for [!INCLUDE[d365fin](includes/d365fin_md.md)] in Power BI](across-how-use-financials-data-source-powerbi.md)  
