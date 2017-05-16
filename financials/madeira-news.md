---
title: What's New in Dynamics 365 for Financials| Microsoft Docs
description: What's New in Dynamics 365 for Financials
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: news
ms.date: 03/28/2017
ms.author: sgroespe
---

# What's New in Dynamics 365 for Financials
Welcome to [!INCLUDE[d365fin](includes/d365fin_md.md)]! If you haven't already, then sign up for a trial, let us walk you through the basics of what you can do with [!INCLUDE[d365fin](includes/d365fin_md.md)], and then try things out on your own for a while. When you are ready, you can open a blank company and set things up for yourself.  

On a regular basis, we will update [!INCLUDE[d365fin](includes/d365fin_md.md)] with additional capabilities in the core application and with new [extensions](ui-extensions.md). For an overview of what is coming and what is currently available, see the [Dynamics 365 Roadmap](https://roadmap.dynamics.com/) - and remember to filter for [!INCLUDE[d365fin](includes/d365fin_md.md)].  

On this page, you can see which areas became available while we were still in preview. Going forward, find the updates in the [Dynamics 365 Roadmap](https://roadmap.dynamics.com/).

## November 2016 Launch of [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]
As announced on the blog, we're now a service that you use in your business. But this update also adds new capabilities and a new extension.

### Project management
If you switch to the Suite experience, you can manage projects and work with resources, time sheets, and jobs. When you first log in as a Project Manager role, an assisted setup guide will help you set up how your projects are managed. You can work with the sample accounts, jobs, resources, and so on in the demonstration company to get familiar with the functionality. For more information, see [Manage Projects](projects-manage-projects.md).

### Fixed assets
If you switch to the Suite experience, you can manage fixed assets, including depreciation and insurance. A standard setup is provided, but you can modify it if anytime you want. You can register purchases of fixed assets in dedicated fixed asset G/L journals where you can also dispose of fixed assets. The right accounting entries are created automatically. For more information, see [Fixed Assets](fa-manage.md).

### New extension for migrating data from Dynamics GP
If your business uses Dynamics GP today, you can use an assisted setup guide to migrate master records to [!INCLUDE[d365fin](includes/d365fin_md.md)]. You must have exported your existing customers, vendors, inventory items, and accounts using the export data functionality in Dynamics GP. The Dynamics GP Data Migration extension automatically maps the exported data so that you can quickly get  your existing data into your new company in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Dynamics GP Data Migration](ui-extensions-dynamicsgp-data-migration.md).

### Cash flow forecasting
The charts on the Accountant Role Center provide insight that can help you make solid decisions about what to do with your cash. Also, you can use the **Cash Flow Forecast** chart to generate predictions of your cash flow in the future. For more information, see [Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md).

### Team members
The **Team Member** Role Center is a new role center that is defined for the Dynamics 356 team member role so that these users can read and modify most data in the system. As a team member, you can also work with timesheets and approval tasks that they are assigned.

### Synchronize your customers and services with Bookings in Office 365
With this update, you can automatically synchronize your customer and service item records with the new **Bookings** app in Office 365. You'll create customers and services and book appointments in Bookings, and these then show up in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Just like that, you'll have invoiced the customer following the service automatically - and you won't have entered the same information twice in the process.

## September 2016 Update
This update of [!INCLUDE[d365fin](includes/d365fin_md.md)] added new capabilities as [announced on the blog](https://community.dynamics.com/business/b/financials/archive/2016/09/29/new-and-updated-capabilities-in-the-september-update-of-project-quot-madeira-quot).

### More flexibility in your sales processes
This update adds more flexibility in what you sell:
- You can now set up nonstock items - items that you offer to customers but do not maintain inventory for. For more information, see [How to: Work with Nonstock Items](inventory-how-work-nonstock-items.md).
- You can now mark an item for drop shipment on a sales order and immediately create a purchase order for the item. This way, you can sell an item to a customer, purchase it from the vendor, and have it shipped directly from your vendor to your customer. For more information, see [How to: Purchase Products for a Sale](purchasing-how-purchase-products-sale.md).

### Categorize items in your inventory
With this update, you can create a hierarchy of item categories and assign item attributes to each item category. For more information, see [How to: Categorize Items](inventory-how-categorize-items.md).

### Send purchase orders to vendors
Now you can enter purchase orders within [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [How to: Record Purchases](purchasing-how-record-purchases.md).

### Better quality incoming documents
You can now easily correct errors in the scanned documents before you receive the resulting document - this way, you'll train the service to avoid the errors going forward. For more information, see [How to: Use OCR to Turn PDF and Image Files into Electronic Document](across-how-use-ocr-pdf-images-files.md).

## August 2016 Update
This update of [!INCLUDE[d365fin](includes/d365fin_md.md)] added new capabilities as [announced on the blog](https://community.dynamics.com/business/b/financials/archive/2016/08/29/new-and-updated-capabilities-in-the-august-update-of-project-quot-madeira-quot).

### Smart notifications give you advice and recommendations
With this update, you'll notice such notifications display when you create a sales invoice for a customer that has an overdue balance, or when the amount in the sales document exceeds the credit limit specified for the customer, for example. For more information, see [Smart Notifications](ui-smart-notifications.md).  

### Introducing the new Sales and Inventory Forecast extension
In this update, we introduce the new Sales and Inventory Forecast extension that gives you insights about potential sales and a clear overview of expected stock-outs. The extension uses [Cortana Intelligence](https://www.microsoft.com/en-us/cloud-platform/what-is-cortana-intelligence-suite) to predict future sales based on your sales history to help you avoid inventory shortage. For more information, see [Sales and Inventory Forecast](ui-extensions-sales-forecast.md).  

###  Smarter sales and purchase documents
We've made several small but important improvements to sales and purchase documents:
- You can cancel posted credit memos
- Sales invoices include Package Tracking No. and Shipping Agent Code
- You can cross reference items
- You can substitute items

## July 2016 Update
This update of [!INCLUDE[d365fin](includes/d365fin_md.md)] added new capabilities as [announced on the blog](https://community.dynamics.com/business/b/financials/archive/2016/07/05/new-and-updated-capabilities-in-the-july-update-of-project-quot-madeira-quot).  

### Working with incoming documents in Outlook
This update adds actions to the vendor dashboard in the Outlook add-in so you can work directly with attachments to the associated email. You use the actions to send the email attachments directly to the **Incoming Documents** list, send the documents to the OCR service, and send an approval request for the incoming document. For more information, see [Manage Incoming Documents](across-income-documents.md).

### Create invoices in your Outlook calendar
The Outlook add-in now extends to the Outlook calendar. From a calendar appointment, you can open the [!INCLUDE[d365fin](includes/d365fin_md.md)] add-in and get an overview for the customer associated with the appointment. Then, you can create and send an invoice for the services provided in the meeting - all of this happening right there in the Outlook calendar. For more information, see [Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as your Business Inbox in Outlook](madeira-outlook.md).  

### AppSource marketplace for extensions
[!INCLUDE[d365fin](includes/d365fin_md.md)] extensions are now available in the AppSource marketplace at [AppSource.microsoft.com](https://appsource.microsoft.com/). You will be able to search and find extensions in the marketplace. You will be able to view information, including marketing material, screenshots, videos and links to additional details. For more information, see [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md).  

### Shipping agents and item attributes
You can add attributes to your inventory items that make it really easy to find the right product that your customer wants. For more information, see [How to: Work with Item Attributes](inventory-how-work-item-attributes.md).  

### New extensions made available
With this update, you can choose between even more extensions in the **Extension Management** window.
For more information, see [[!INCLUDE[d365fin](includes/d365fin_md.md)] Extensions by Other Providers](ui-extensions-other.md).  

### Manage your customer relationships using Microsoft Dynamics CRM from inside [!INCLUDE[d365fin](includes/d365fin_md.md)]
We've added a new assisted setup guide to the Business Manager home page that guides you through the setup process to connect to Dynamics CRM. Once that's done, you'll have a seamless coupling of Dynamics CRM records with [!INCLUDE[d365fin](includes/d365fin_md.md)] records. For more information, see [Manage your customer relationships using Microsoft Dynamics CRM from inside [!INCLUDE[d365fin](includes/d365fin_md.md)] ](marketing-integrate-dynamicscrm.md).

## May 2016 Update
This update of [!INCLUDE[d365fin](includes/d365fin_md.md)] added new capabilities as [announced on the blog](https://community.dynamics.com/business/b/financials/archive/2016/06/01/new-and-updated-capabilities-in-the-first-update-of-project-quot-madeira-quot).  

### New extensions made available
Check out the **Extension Management** window: The update adds new extensions, including Sana Commerce for [!INCLUDE[d365fin](includes/d365fin_md.md)] that provides B2B Commerce capabilities, and ChargeLogic Payments that provides payment and credit card processing capabilities. The extensions are not installed automatically for you, but the **Extension Management** window will help you install the extensions that you want to use. For more information, see [[!INCLUDE[d365fin](includes/d365fin_md.md)] Extensions by Other Providers](ui-extensions-other.md).  

### Filter on unprocessed incoming documents
We have also changed some core functionality in this month's update: The list of incoming documents is now filtered to show only entries that have not been used to create posted documents with. For more information, see [Manage Incoming Documents](across-income-documents.md).  

### Office Suite notifications are now enabled in [!INCLUDE[d365fin](includes/d365fin_md.md)]
In the top right corner, next to the Settings menu, you will notice the bell symbol that you probably already know well from other Office products: That's the Notifications menu. Here you will receive notifications such as new mail and calendar reminders directly while working in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## April 2016 Preview
In April 2016, we launched the preview of [!INCLUDE[d365fin](includes/d365fin_md.md)]. Everything was new, and we encouraged you to start the Getting Started guide in the demonstration company that you get access to when you first sign up. The Getting Started guide steps you through key scenarios. For more information, see [Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md).  

Key scenarios to try out on your own:  

- [Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as your Business Inbox in Outlook](madeira-no-outlook.md)  
- [Getting [!INCLUDE[d365fin](includes/d365fin_md.md)] on Your Mobile Device](install-mobile-app.md)  
- [Enabling Your Business Data for Power BI](madeira-powerbi.md)  
- [Changing the Role Center](change-role.md)  



## See Also
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Dynamics 365 Roadmap](https://roadmap.dynamics.com/)  
