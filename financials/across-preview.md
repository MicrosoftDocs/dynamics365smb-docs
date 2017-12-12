---
title: Get the preview in new markets
description:
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 12/12/2017
ms.author: edupont

---
# [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] Preview Access
[!INCLUDE[d365fin](includes/d365fin_md.md)] is coming to new markets in the spring of 2018 and will offer a public preview in each of those markets ahead of the launch. Starting in December, the preview for Denmark is available, with additional markets to follow every month.  

## Get the Preview
Go here to start your preview <link>.  

Starting the preview creates an instance of [!INCLUDE[d365fin](includes/d365fin_md.md)] with all features enabled, thereby requiring advanced product knowledge to set it up. To learn more [!INCLUDE[d365fin](includes/d365fin_md.md)] and the capabilities, please refer to the documentation here on this site.  

### What about the preview in United States, Canada, and United Kingdom specifically
For partners and customers in the United States, Canada, and United Kingdom, we have a trial experience available in which the sandbox environment that includes [!INCLUDE[d365fin](includes/d365fin_md.md)] functionality can be enabled. Please go to the [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] homepage to start this trial.
Please find instructions for how to create a Sandbox environment below.  

### Build new solutions and intellectual property
Extend functionalities and experiences by building an add-on or embed solution for [!INCLUDE[d365fin](includes/d365fin_md.md)] to implement new and industry specific end-to-end experiences. Add new functionality to the application to integrate third-party solutions, such as PayPal Payments with add-ons.  

Build a connected app to establish an interchange of data between [!INCLUDE[d365fin](includes/d365fin_md.md)] and your app by using an API. Connect apps can also make use of extensions to create pages to be used for setup, configuration, or to support app-specific features.  

Learn more [https://aka.ms/getstartedwithapps]  

## Automate the provisioning of tenants via PartnerCenter
If you as a partner would like to automate the provisioning of tenants via PartnerCenter, please follow the steps in this section.  

### Getting Started
There are two types of accounts in Partner Center:  

-	Primary Partner Center account for creating real orders for real customers  
-	Integration sandbox account for testing your code and its integration with the Partner Center APIs before you deploy it broadly.  

    The sandbox account is configured from inside primary Partner Center account, but it acts independently and does not share any credentials with the primary account.  

The script can be downloaded from here: <path>

We recommend that you run the demo script using the Sandbox Partner account.

Learn how to set up API access in Partner Center: https://msdn.microsoft.com/library/partnercenter/mt709136.aspx

### Prerequisites for Demo Script:
-	Configure a native app in PartnerCenter  
-	Update app.config file with Native App ID and partner center credentials  

To run the application, run this command:
```
SaaSTenantsViaPartnerCenterDemo.exe -File:<Path to the .csv file with customer data>
```

The log file is at the equivalent of ```SaaSTenantsViaPartnerCenterDemo\SaaSTenantsViaPartnerCenterDemo\bin\Debug\Logs```.  
The output file, CspCustomerDetails.csv, will contain the following CSP customer data: company name, user credentials, link to the company tenant.  

A useful link is to the PartnerCenter API samples: https://github.com/PartnerCenterSamples/Partner-Center-SDK-Samples/tree/master/Source/Partner%20Center%20SDK%20Samples

If you have the relevant data in an Excel workbook, you can save that as a .csv. However, then you must make sure that the line separator is set to ; on the computer where you do the conversion.  

## Creating a Sandbox Environment
A Sandbox environment (Preview) is a non-production instance of [!INCLUDE[d365fin](includes/d365fin_md.md)]. Isolated from production, a Sandbox environment is the place to safely explore, learn, demo, develop, and test the service without a risk of affecting the data and settings of your production environment.  

You must have a subscription to [!INCLUDE[d365fin](includes/d365fin_md.md)] to be able to create a Sandbox environment. There can only be one Sandbox environment per subscription.

### To create a sandbox environment

1.	Sign in to your production instance of [!INCLUDE[d365fin](includes/d365fin_md.md)].  
2.	Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sandbox Environment**, and then choose the related link.
3.	Select Create. Another tab in your browser will open for finishing the setup of your Sandbox environment.
If you have pop-up blocker enabled in your browser, change it to allow URLs from the *.financials.dynamics.com* address.
4.	As soon as the Sandbox environment is ready, you will be redirected to the Sandbox environment's Welcome wizard.
5.	Choose the **Learn more** link if you want to read about scenarios that you can try in a Sandbox environment. At the time of this writing, it describes how you can develop extensions using the Sandbox. Otherwise, choose **Close** to continue to the Role Center of your [!INCLUDE[d365fin](includes/d365fin_md.md)] Sandbox instance.
6.	At the top of the Role Center, a notification appears to inform you that this is a Sandbox environment. You can also see the type of the environment in the title bar of the client.
In the Sandbox environment, a brand-new tenant has been created. This tenant is loaded with default demonstration data for the CRONUS company. No data is copied or otherwise transferred from the production environment during the Sandbox creation.
7.	At any time, you can return to Sandbox Environments page, and reset the Sandbox environment.
Resetting the Sandbox environment will remove it completely, and then create it again with the default demonstration data.
8.	To switch between your production and Sandbox environments, you can use the Dynamics 365 menu or the Dynamics home page.
9.	It is possible for an administrator or another user to limit or even block access for some users to the Sandbox environment. This can be done by using the standard security features of the product, such as the User card, User Groups and Permission Sets:

### Advanced functionality available in a Sandbox environment
Within a Sandbox environment, you will find the in-client designer feature enabled, which you can activate by selecting the icon on a page. For more information, see <link>.
It is possible to enable and try the advanced (full) functionality of [!INCLUDE[d365fin](includes/d365fin_md.md)] in a Sandbox tenant by setting the Experience field on the Company Information page. For more information, see <link>. After you’ve enabled the advanced functionality in a Sandbox tenant, you get access to all the standard profiles and Role Centers. You can also create an evaluation company that is fully set up, including demonstration data and access to the advanced areas of the product.
