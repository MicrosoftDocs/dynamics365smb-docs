---
title: Add an Email Account in Business Central | Microsoft Docs
description: Describes how to add an email account to send and receive email messages in Business Central.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, mail, Office 365
ms.date: 06/15/2020
ms.author: bholtorf

---
# Add an Email Account
Connect one or more email accounts to [!INCLUDE[d365fin](includes/d365fin_md.md)] and send messages without having to switch apps. 

To use email features, you can either use the email connectors we provide, or build an app yourself and connect to it. The latter will probably require the help of a partner. For more information, see [Using Your Own Email App](admin-how-setup-email.md#using-your-own-email-app).

## About Email Connectors
You add an email account to [!INCLUDE[d365fin](includes/d365fin_md.md)] by using email connectors. The following table describes the standard email connectors that are available in [!INCLUDE[d365fin](includes/d365fin_md.md)].

|Account Type  |Description  |Examples of when to use  |
|---------|---------|---------|
|Office 365     |Specific account. Everyone sends email from the account you specify.|When all messages come from the same department, for example, your sales organization.|
|Office 365     |Own accounts. Everyone sends email from their own account.|Allow individual communications.|
|Outlook     |Outlook.com, Live.com, Hotmail, MSN|Allow individual communications.|
|Other (SMTP)     |Use SMTP protocol to send emails.|         |

> [!NOTE]
> The SMTP connector functions in the same way as previously in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Set Up Email](admin-how-setup-email.md).

Two people can use the same address, for example, sales@cronus.com. To do that, you must go to Azure AD to allow multiple users to use the same account. To do that, go to Microsoft 365 admin center, Active Users, choose the user, choose Mail blade, and Manage email account, and then Send on behalf of permissions. Add the account to use, and then save you setting. **This is the new send on behalf of feature** You must make sure that all users have access to the account if you choose a shared account.

## Set up email accounts
To quickly add an account, use the **Set up email** assisted setup guide to complete the process.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Setup Email Accounts**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 

## Assign accounts to processes
Email is often used for specific business scenarios. For example, you might want to send sales documents from one account, and purchase documents from another. You can specify which scenarios that you want to use an account for. 

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Accounts**, and then choose the related link.
2. Choose the account to define scenarios for, and then choose **Process**, and then **Setup email scenarios**.
3. Choose **Add scenarios**, and then choose the scenarios.

## Using Your Own Email App
To use your own app, there are a few things you must do.

1. Register your application in Azure Active Directory. For more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).
2. Assign the following permissions for Microsoft Graph to your app.

   |Permission  |Type  |Description  |
   |---------|---------|---------|
   |Mail.Send|Delegated|Send mail as a user         |
   |Mail.Send.Shared|Delegated|Send mail on behalf of others  |
   |offline_access|Delegated|Maintain access to data you have given it access to|
   |openid|Delegated|Sign users in|
   |User.Read|Delegated|Sign in and read user profile|
3. Run the **Set up email** assisted setup guide to connect your email account.

## Uptaking the New Email Features
If you have already configured the email capabilities, you can continue using your current setup or you can start using the new email connectors. If you have customized the email capabilities, for example, through an extension, there is a chance that something will go wrong with those customizations when you start using the new email connectors.

## See Also
[Set Up Email](admin-how-setup-email.md)