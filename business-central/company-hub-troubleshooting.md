---
title: Troubleshooting your company hub
description: Learn how to work around any issues when you the company hub in Dynamics 365 Business Central to manage work across multiple companies.
author: brentholtorf
ms.topic: troubleshooting-general
ms.devlang: al
ms.search.keywords: accountant, accounting, troubleshoot
ms.search.form: 1151
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Troubleshooting Your Company Hub

Adding companies to the company hub dashboard is easy enough, but this article addresses issues that you may have on the way.  

## Check errors

Use the **Check Errors** action to view a list of recent errors. You can see additional details for each error, and you can clean up the log by deleting older entries.  

## Connection failed

There can be a couple of reasons why you cannot connect to a company, including the following:

- The URL in the **Environment Link** field is not valid  

  Go to the **Environment Links** page, open the environment that you cannot connect to, and then choose the **Test the connection** action.  
- The client's company is currently offline, for example if it being upgraded

  In your dashboard, choose the **Tools** menu item, and then choose **Check Errors**. This opens a list with technical details, so you might want to contact your administrator if you're seeing errors. For example, the error message "*The server has rejected the client credentials*" suggests that you do not have access.  
- You do not have access to all companies in the environment that you are trying to connect to

  In [!INCLUDE [prod_short](includes/prod_short.md)], an organization can have multiple business units called companies, and you might not have access to all companies. Work with your administrator or client to make sure that you have access to the companies that you have to work in.  

## Data does not refresh

When you add a company or request a refresh of the data, [!INCLUDE [prod_short](includes/prod_short.md)] fetches the data. But you must refresh the page yourself, such as choosing the **Reload all companies** action, refresh the browser page, navigate away from the dashboard and then back again, or similar.  

If you've added a company but it is not displaying in the list, you can also use the **Reload all companies** action to update the list.

## Related information

[Manage Work across Multiple Companies in the Company Hub](company-hub.md)  
[Add companies to your company hub](company-hub-add-company.md)  
[Accountant Experiences in Business Central](finance-accounting.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
