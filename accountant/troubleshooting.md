---
title: Ways to troubleshoot or work around issues | Microsoft Docs
description: Learn how to work around any issues in the Accountant Hub for Dynamics 365.
author: edupont04

ms.service: dynamics365-accountant
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting, troubleshoot
ms.date: 10/01/2019
ms.author: edupont

---
# Troubleshooting [!INCLUDE [d365acc_long](includes/d365acc_long_md.md)]
[!INCLUDE [d365fin_early_release](includes/d365fin_early_release.md.md)]

Signing up for [!INCLUDE [d365acc](includes/d365acc_md.md)] is easy and can be done very quickly. Adding clients to the dashboard is also easy, but this article addresses issues that you may have on the way.

## What email address can I use with [!INCLUDE [d365acc](includes/d365acc_md.md)]?
[!INCLUDE [d365acc](includes/d365acc_md.md)] requires that you use a work or school email address to sign up. [!INCLUDE [d365acc](includes/d365acc_md.md)] does not support email addresses provided by consumer email services or telecommunication providers. This includes outlook.com, hotmail.com, gmail.com, and others.  

If you try to sign up with a personal email address, you will get a message indicating to use a work or school email address.  

## Why can't I connect to my client's data?
There can be a couple of reasons, including the following:

- The URL in the **Client URL** field is not valid  

  Go to **Manage Clients**, open the client that you cannot connect to, and then choose **Test Client URL**.  
- The client's company is currently offline, for example if it being upgraded

  In your dashboard, choose the **Tools** menu item, and then choose **Check Errors**. This opens a list with technical details, so you might want to contact your administrator if you're seeing errors. For example, the error message "The server has rejected the client credentials" suggests that you do not have access.  
- You have not received an email from your client that invites them to their [!INCLUDE [d365fin](includes/d365fin_md.md)], or you did not open the link in the email, or you did not accept the invitation

  You must open the link in the invitation and accept the steps that adds you to your client's [!INCLUDE [d365fin](includes/d365fin_md.md)]. Until then, you do not have access to their data.  
- You do not have access to all companies in your client's [!INCLUDE [d365fin](includes/d365fin_md.md)]

  Your client can have multiple business units or companies in [!INCLUDE [d365fin](includes/d365fin_md.md)], and your invitation does not always include all companies. Work with your client to make sure that you have access to the companies that the client wants you to work in.  

## Why doesn't the data refresh in my dashboard?
When you add a client or request a refresh of the data, [!INCLUDE [d365acc](includes/d365acc_md.md)] fetches the data. But you must refresh the page yourself, such as choosing the "Redisplay all companies" action, refresh the browser page, navigate away from the dashboard and then back again, or similar. This is a known issue that we are working on improving in a later update.  

## See Also
[Get Started with [!INCLUDE[d365acc](includes/d365acc_md.md)]](get-started.md)  
[Add Clients to Your Dashboard in [!INCLUDE[d365acc](includes/d365acc_md.md)]](add-client.md)  
