---
title: Finance and Operations, Business edition and Power BI Content Packs| Microsoft Docs
description: Getting insight, business intelligence, and KPIs from your Finance and Operations, Business edition data is easy with Power BI and the Finance and Operations, Business edition content packs.
author: edupont04

ms.service: dynamics365-financials
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 09/05/2017
ms.author: edupont

---
# Enabling Your Business Data for Power BI
Getting insights into your [!INCLUDE [d365fin](includes/d365fin_md.md)] data is easy with Power BI and the [!INCLUDE [d365fin](includes/d365fin_md.md)] content packs. Power BI retrieves your data and then builds an out-of-the-box dashboard and reports based on that data.  

Microsoft has published the following content packs:

| App | Description |
| --- | --- |
| Microsoft Finance and Operations, Business edition | Provides a dashboard with key financial data over time, such as earnings versus expenses, operating margin, and cash cycle.|
| Microsoft Finance and Operations, Business edition - CRM | Provides a dashboard with key data about sales opportunities and contacts.  |
| Microsoft Finance and Operations, Business edition - Sales | Provides a dashboard with key data about sales and inventory. |

## Using the Dashboards
Each content pack provides reports that you can drill into:

* Choose any visual on the dashboard to bring up one of the underlying reports.  
* Filter the report or add fields that you want to monitor.  
* Pin this customized view to the dashboard to continue tracking.  
  You can refresh data manually, and you can set up a refresh schedule. For more information, see [Configuring scheduled refresh](https://powerbi.microsoft.com/en-us/documentation/powerbi-refresh-scheduled-refresh/).  

The content packs are preconfigured to work with data from the demonstration company that you get when you sign up for [!INCLUDE [d365fin](includes/d365fin_md.md)]. When you install the apps in Power BI, and you connect to your own data, some reports may not work because they rely on data that your company does not have. In those cases, you can simply remove that report from your dashboard.  

> [!NOTE]
>   You can also build your own reports and dashboards in Power BI based on your [!INCLUDE [d365fin](includes/d365fin_md.md)] data. For more information, see [Connecting Your Business Data to Power BI](across-how-use-financials-data-source-powerbi.md).  

## Accessing [!INCLUDE [d365fin](includes/d365fin_md.md)] in Power BI
To see your [!INCLUDE [d365fin](includes/d365fin_md.md)] data in Power BI, you must have the following:  

* Access to [!INCLUDE [d365fin](includes/d365fin_md.md)]. For more information, see [Finance and Operations, Business edition](http://go.microsoft.com/fwlink/?LinkID=759714).  
* Access to Power BI. For more information, see [Power BI](https://powerbi.microsoft.com).

On the Power BI site, you can find additional information about [connecting to services with content packs for Power BI](http://go.microsoft.com/fwlink/?LinkID=760850).  

To access your [!INCLUDE [d365fin](includes/d365fin_md.md)] data in Power BI, on the connection page, you must specify the following information:


|           Field           |                                                                        Description                                                                         |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    **OData Feed URL**     | The OData URL so Power BI can access data from your company, such as <https://mybusiness.financials.dynamics.com:7048/MS/ODataV4/Company('My%2Business>'). |
| **Authentication method** |                                                                     Choose **Basic**.                                                                      |
|       **User name**       |                      Your name as it displays for your account in [!INCLUDE [d365fin](includes/d365fin_md.md)], such as *John Smith*.                      |
|       **Password**        |                         This is the web service access key for your user account in [!INCLUDE [d365fin](includes/d365fin_md.md)].                          |

This means that you must get 2 pieces of information from [!INCLUDE [d365fin](includes/d365fin_md.md)]: The *OData URL* and the *web service access key* for your user account.  

### Getting the URL
When you add [!INCLUDE [d365fin](includes/d365fin_md.md)] to Power BI, you must specify a URL so Power BI can access data from your company. On the connection page, the URL is referred to as the **OData Feed URL**, and it must have the following format:

         https://mybusiness.financials.dynamics.com:7048/MS/ODataV4/Company('CRONUS%20US')  
In this example, *mybusiness* is the name of your [!INCLUDE [d365fin](includes/d365fin_md.md)] service, and *CRONUS US* is the name of the demonstration company with *%20* representing the space in the name.   
To get the URL, in [!INCLUDE [d365fin](includes/d365fin_md.md)], search for and open the **Web Services** window. This window lists the web services that are currently available, and you can copy the link from the **OData URL** field for one of the default OData web services.  

### Getting the user name and the web service access key
In order to use data from [!INCLUDE [d365fin](includes/d365fin_md.md)] in Power BI, in the **Connect to Financials** window, you must specify a user name and a password. The user name is your name as it displays for your account in [!INCLUDE [d365fin](includes/d365fin_md.md)] so that Power BI can log in to [!INCLUDE [d365fin](includes/d365fin_md.md)]. The password is the web service access key that is set up for your user account in [!INCLUDE [d365fin](includes/d365fin_md.md)].  

To find this information, in [!INCLUDE [d365fin](includes/d365fin_md.md)], search for the **Users** window, and then open the card for your user account. On the **General** FastTab, copy the content of the **User Name** field, and on the **Web Service Access** FastTab, copy the contents of the **Web Service Access Key** field. If the **Web Service Access Key** field is blank, in the ribbon, choose **Change Web Service Access Key**, choose the **Key Never Expires** field, and then choose the OK button. You can then copy the key.  

## Getting Data from [!INCLUDE [d365fin](includes/d365fin_md.md)]
The [!INCLUDE [d365fin](includes/d365fin_md.md)] dashboard shows the most typical reports that you will want to use to track your business. The data is extracted from your [!INCLUDE [d365fin](includes/d365fin_md.md)] company using web services to read live data. In [!INCLUDE [d365fin](includes/d365fin_md.md)], the **Web Services** window lists the web services that have been set up for you.

> [!NOTE]
>   If you change the name of any of these web services, the data will not show up in Power BI.  
> If you want to add use other data in Power BI, you must find the tables in [!INCLUDE [d365fin](includes/d365fin_md.md)], expose them as web services, and then add them to the content pack. This is an advanced scenario, and we recommend that you start with the data that is already available in Power BI.  

## Troubleshooting
The Power BI dashboard relies on the published web services that are listed above, and it will show data from the demonstration company or your own company if you import data from your current finance solution. However, if something goes wrong, this section provides a workaround for the most typical issues.  

**"Parameter validation failed, please make sure all parameters are valid"**  
If you see this error after you enter your [!INCLUDE [d365fin](includes/d365fin_md.md)] URL, make sure the following requirements are satisfied:  

* The URL follows exactly this pattern:

    <https://mybusiness.financials.dynamics.com:7048/MS/ODataV4/Company('CRONUS%20US>')  
* Delete any text after the company name in parenthesis  
* Make sure there are no trailing forward slash at the end of the URL.  
* Make sure that it is a secure connection as indicated by the URL starting with *https*.  

**"Login failed"**  
If you get a "login failed" error when you log in to the dashboard, using your [!INCLUDE [d365fin](includes/d365fin_md.md)] credentials, then this can be caused by one of the following issues:

* The account you are using does not have permissions to read the [!INCLUDE [d365fin](includes/d365fin_md.md)] data from your account.

    Verify your user account in [!INCLUDE [d365fin](includes/d365fin_md.md)], and make sure that you have used the right web service access key as the password, and then try again.  
* The [!INCLUDE [d365fin](includes/d365fin_md.md)] instance that you are trying to connect to does not have a valid SSL certificate. In this case you'll see a more detailed error message ("unable to establish trusted SSL relationship").

    > [!NOTE]  
  >   Self-signed certificates are not supported.  

**"Oops"**  
If you see an "Oops" error dialog after you pass the authentication dialog, this is most frequently caused by a problem connecting to the data for the content pack.

* Verify that the URL follows the pattern that was specified earlier:

    `https://mybusiness.financials.dynamics.com:7048/MS/ODataV4/Company('CRONUS%20US')`  
* A common mistake is to specify the full URL for a specific web service:

    `https://mybusiness.financials.dynamics.com:7048/MS/ODataV4/Company('CRONUS%20US')/powerbifinance`
* Or you might have forgotten to specify the company name:

    `https://mybusiness.financials.dynamics.com:7048/MS/ODataV4/`

## See Also
[Business Intelligence](bi.md)  
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as a PowerApps Data Source](across-how-use-financials-data-source-powerapps.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] in Microsoft Flow](across-how-use-financials-data-source-flow.md)   

## [!INCLUDE [d365fin](includes/free_trial_md.md)]  
## [!INCLUDE [d365fin](includes/training_link_md.md)]
