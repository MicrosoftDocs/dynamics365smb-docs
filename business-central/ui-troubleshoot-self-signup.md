---
title: Troubleshoot Issues with Self-Service Sign-Up | Microsoft Docs
description: Learn about the most common reasons why you may not be able to complete the signup to Business Central, and ways to work around them.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2020
ms.author: edupont

---
# Troubleshooting Self-Service Sign-Up
Signing up for [!INCLUDE[d365fin](includes/d365fin_md.md)] is easy and can be done very quickly. You can create a free account even if you are an existing organization. This article addresses issues that you may have during signup.

## What email address can I use with Business Central?
[!INCLUDE[d365fin](includes/d365fin_md.md)] requires that you use a work, or school, email address to sign up. [!INCLUDE[d365fin](includes/d365fin_md.md)] does not support email addresses provided by consumer email services or telecommunication providers. This includes outlook.com, hotmail.com, gmail.com, and others.

If you try to sign up with a personal email address, you will get a message indicating to use a work or school email address.

## Troubleshooting
In many cases, registering for [!INCLUDE[d365fin](includes/d365fin_md.md)] can be achieved by following the sign-up process. However, there are several reasons why you may not be able to complete self-service signup. The table below summarizes some of the most common reasons you may not be able to complete signup and ways you can workaround these issues.

| Symptom/Error Message | Cause and Workaround |
| --------------------- | -------------------- |
| For Office 365 email addresses that are not registered in a supported country, you receive a message like the following during signup:<br /><br />**That didn't work, we don't support your country or region yet.** |[!INCLUDE[d365fin](includes/d365fin_md.md)] currently only supports Office 365 email accounts that are registered in a limited number of markets. For more information, see [Regional Availability](#regional-availability). |
| Personal email addresses such as nancy@gmail.com are not supported. You receive a message like the following during signup:<br /><br />**You entered a personal email address: Please enter your work email address so we can securely store your company's data.**<br> or <br> **That looks like a personal email address. Enter your work address so we can connect you with others in your company. And don’t worry. We won’t share your address with anyone.** |[!INCLUDE[d365fin](includes/d365fin_md.md)] does not support email addresses provided by consumer email services or telecommunications providers. To complete signup, try again using an email address assigned by your work or school. If you still cannot sign up and are willing to complete a more advanced setup process, you can register for a new Office 365 trial subscription and use that email address to sign up. |
| .gov or .mil email addresses You receive a message like the following during signup:<br /><br />**[!INCLUDE[d365fin](includes/d365fin_md.md)] unavailable: [!INCLUDE[d365fin](includes/d365fin_md.md)] is not available for users with .gov or .mil email addresses at this time. Use another work email address or check back later.** <br>or <br>**We can't finish signing you up. It looks like [!INCLUDE[d365fin](includes/d365fin_md.md)] isn't currently available for your work or school.** |[!INCLUDE[d365fin](includes/d365fin_md.md)] does not support .gov or .mil addresses at this time. |
| Self-service signup is not enabled. You receive a message like the following during signup:<br /><br />**We can't finish signing you up. Your IT department has turned off signup for [!INCLUDE[d365fin](includes/d365fin_md.md)]. Contact them to complete signup.** <br>or <br> **That looks like a personal email address. Enter your work address so we can connect you with others in your company. And don’t worry. We won’t share your address with anyone.** |Your organization’s IT administrator has disabled self-service signup for [!INCLUDE[d365fin](includes/d365fin_md.md)]. To complete signup, contact your IT administrator and ask them to follow the instructions on the page below to allow existing users to sign up for [!INCLUDE[d365fin](includes/d365fin_md.md)] and to allow new users to join your existing tenant. You may also experience this problem if you signed up for Office 365 through a partner. |
| Email address is not an Office 365 ID. You receive a message like the following during signup:<br /><br />**We can't find you at contoso.com. Do you use a different ID at work or school? Try signing in with that, and if it doesn't work, contact your IT department.** |Your organization uses IDs to sign in to Office 365 and other Microsoft services that are different than your email address. For example, your email address might be Nancy.Smith@contoso.com but your ID is nancys@contoso.com. To complete signup, use the ID that your organization has assigned to for signing in to Office 365 or other Microsoft services. If you do not know what this is, contact your IT administrator. If you still cannot sign up and are able to complete a more advanced setup process, you can register for a new Office 365 trial subscription and use that email address to sign up. |
| If your Office 365 account is registered to a supported country, and you are signing up for [!INCLUDE[d365fin](includes/d365fin_md.md)] while in a different country, you receive a message like the following during signup:<br /><br />**That didn't work, we don't support your country or region yet.**| Your organization's Office 365 subscription is registered to a specific country in the Office 365 administration portal. The signup experience for [!INCLUDE[d365fin](includes/d365fin_md.md)] uses the language and locale that your current browser uses, and as a result, you can get the error message even though you are in a supported country. Ask your IT administrator to verify the country that is specified in the organization profile in the [Office 365 administration portal](https://portal.office.com/adminportal/home#/companyprofile). You may have to use a different account for [!INCLUDE[d365fin](includes/d365fin_md.md)].|

## Regional Availability

[!INCLUDE [prodshort](includes/prodshort.md)] is available in a number of countries or regions with localization provided either by Microsoft or an approved localization partner. For a complete list of supported countries and regions, see [Country/Regional Availability and Supported Translations](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json).  

For an overview of currently supported markets across Dynamics 365, see the [International availability of Microsoft Dynamics 365](/dynamics365/get-started/availability) deck. For an overview of local functionality in [!INCLUDE [prodshort](includes/prodshort.md)], see the [Local Functionality](about-localization.md) landing page.  

## See Also

[Welcome to [!INCLUDE[d365fin](includes/d365fin_long_md.md)]](index.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Local Functionality](about-localization.md)  
[Country/Regional Availability and Supported Translations](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json)  
[International availability of Microsoft Dynamics 365](/dynamics365/get-started/availability)  
