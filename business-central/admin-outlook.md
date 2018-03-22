---
title: Using Business Central with Outlook| Microsoft Docs
description: This service has deep integration with Office 365 enabling you to manage all your business interactions and mail with customers and vendors directly in Outlook.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, mail, Office 365
ms.date: 03/16/2018
ms.author: edupont

---
# Using Business Central as your Business Inbox in Outlook
[!INCLUDE[d365fin](includes/d365fin_md.md)] introduces the ability to manage business interactions with your customers and vendors, directly in Microsoft Outlook. With the [!INCLUDE[d365fin](includes/d365fin_md.md)] Outlook add-ins, you can see financial data related to customers and vendors, as well as create and send financial documents, such as quotes and invoices.  

## Getting the Add-in
In [!INCLUDE[d365fin](includes/d365fin_md.md)], one of the steps in the Getting Started assisted setup is the **Run your business within Office 365** window. In that window, when you choose the **Set up in Outlook** button, you must specify your Office 365 user name and password. The [!INCLUDE[d365fin](includes/d365fin_md.md)] add-ins are then automatically added to your Outlook.  

Then, when you open Outlook, you will see an email message from Business Central Admin. The new add-in is added to the Outlook ribbon, and in Outlook Web Access, you can see it in the add-in ribbon, immediately above the body of the email message. The add-in itself will be updated periodically, and you'll get notified that a new version is ready for you in Outlook.  

Some companies using Office 365 restrict users’ permissions to deploy add-ins. So you must make sure that you have an Office 365 subscription that includes email and allows you to deploy add-ins. If you want to try out the add-in anyway, you can [try Office 365 for free](https://products.office.com/try).  

## Using the Contact Insights Add-in
Let's say that you get an email from a customer that wants to get a quote on some items. Directly in Outlook, you can open the [!INCLUDE[d365fin](includes/d365fin_md.md)] add-in, which recognizes the sender as a customer, and opens the customer card for his company. From this dashboard, you can see overview information for the customer, as well as drill down for more detail on specific documents. You can also dig into the sales history for the customer. If it's a new customer, you can create them as a new customer in [!INCLUDE[d365fin](includes/d365fin_md.md)] without leaving Outlook.  

In the add-in, you can create a sales quote and send it back to this customer without leaving Outlook. All of the information that you need to send the sales quote is available in your business inbox in Outlook.  
Once you have the data entered, you can post the quote. You can then send it by email. [!INCLUDE[d365fin](includes/d365fin_md.md)] generates a .PDF file with the sales quote and attaches it to the email message that you draft in the add-in.  

Similarly, if you get an email from a vendor, you can use the add-in to work with vendors and purchase invoices.  

Sometimes you want to see more fields than you can see in the add-in, such as when you want to fill in lines in an invoice. To give you a bit more space to work with, you can pop out the add-in to a separate window. It's still part of Outlook, but you have more space. As you enter data for the document in the pop-out view, the changes are automatically saved. When you are done entering data for the document, you can choose the **OK** button. Choosing the add-in frame in Outlook automatically refreshes the document with the changes you made in the pop-out view.  

## Creating Invoices from Your Meeting Appointments
Some businesses record all billable appointments in the Outlook calendar. With [!INCLUDE[d365fin](includes/d365fin_md.md)], you can create the invoice for the customer right from the calendar item: Open the appointment, and then you can open the [!INCLUDE[d365fin](includes/d365fin_md.md)] add-in, look up existing information or create an invoice or another sales document right there.  

## Doing Quick Document Lookup
The [!INCLUDE[d365fin](includes/d365fin_md.md)] Document Links add-in gives you quick access to documents mentioned in email messages. The add-in is available for an email message if a document number is recognized in the body of the message. Opening the add-in provides quick access to the document.  

For example, if you receive an email message that mentions the text *S-QUO100*, [!INCLUDE[d365fin](includes/d365fin_md.md)] identifies that as a sales quote, and so you can open this document in Outlook. In Outlook, choose the **Document Links** button immediately above the body of the email message. In the Outlook Web App, choose the *S-QUO1001* text in the body of the email message.  

In the Document Links add-in, you can modify and take actions with the document, just like you can in [!INCLUDE[d365fin](includes/d365fin_md.md)].

## Adding the Add-ins Manually
In some cases, the add-ins do not get added automatically to Outlook. Even if you or a colleague ran the assisted setup guide on behalf of the company, [!INCLUDE[d365fin](includes/d365fin_md.md)] might not show up in Outlook. If you experience this issue, you can add the [!INCLUDE[d365fin](includes/d365fin_md.md)] add-ins manually.  

First, you must verify that you have access to the add-ins in your Office 365 account. Quite simply open your Outlook Web Access in a browser, and then add `/owa/#path=/options/manageapps` to the URL in the address bar. This opens the **Manage add-ins** page, where you can enable [!INCLUDE[d365fin](includes/d365fin_md.md)] for your Outlook. Then, when you navigate back to Outlook, [!INCLUDE[d365fin](includes/d365fin_md.md)] should be available.  

Similarly in the Outlook desktop client, you can verify that [!INCLUDE[d365fin](includes/d365fin_md.md)] is listed in the **Manage Add-ins** window.  

In both cases, if [!INCLUDE[d365fin](includes/d365fin_md.md)] is still not available, you have to get the add-in manifest files. For more information, please contact your Office 365 administrator.

## See Also
[Getting Started](product-get-started.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
