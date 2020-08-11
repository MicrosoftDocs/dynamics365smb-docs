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
> [!NOTE]
> Improved email capabilities are available in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you're new to [!INCLUDE[d365fin](includes/d365fin_md.md)] the new capabilities are already turned on. If you have already configured email you can continue using your current setup, or your administrator can turn on the new email capabilities. For more information, see [About Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management.md#about-feature-management). 
>
> If you have customized the email capabilities, for example, through an extension, there is a chance that something will go wrong with your customizations if you start  using the new email connectors. 

You can connect one or more email accounts to [!INCLUDE[d365fin](includes/d365fin_md.md)] and send and receive email messages without having to switch apps. You can compose each message individually with basic formatting tools (fonts, styles, colors, and so on) and add attachments (up to 100MB), or create templates that contain pre-defined, reusable texts. For more information, see [Send Documents by Email](ui-how-send-documents-email).

To use email features, you can either use the email connectors we provide, or build an app yourself and connect to it. The latter will probably require the help of a partner. For more information, see [Using Your Own Email App](admin-add-an-email-account.md#using-your-own-email-app).

## About Email Connectors
You add an email account to [!INCLUDE[d365fin](includes/d365fin_md.md)] by using email connectors. The following table describes the standard email connectors that are available in [!INCLUDE[d365fin](includes/d365fin_md.md)].

|Account Type  |Description  |Examples of when to use  |
|---------|---------|---------|
|Office 365     |Specific account. Everyone sends email from the account you specify.|When all messages come from the same department, for example, your sales organization.<br><br> Two or more people can use the same address, for example, sales@cronus.com. This requires that you set up the account in Azure Active Directory to allow multiple users. To allow multiple users to use the same account, go to the **Microsoft 365 admin center**, choose **Active Users**, choose the user, choose **Mail**, **Manage email account**, and then **Send on behalf of permissions**. Add the account to use, and then save your setting. If you add a shared account, all users must have access to the account.|
|Office 365     |Own accounts. Everyone sends email from their own account.|Allow communications from individual accounts.|
|Outlook     |Outlook.com, Live.com, Hotmail, MSN|Allow communications from individual accounts.|
|Other (SMTP)     |Use SMTP protocol to send emails.|Specific account. Everyone sends email from the account you specify. You can, however, use the **Send As** or **Send on Behalf** capabilities on your Exchange server to change the sender address on outbound messages. For more information, see [Using a Substitute Sender Address on Outbound Email Messages](/dynamics365/business-central/admin-how-setup-email.md#using-a-substitute-sender-address-on-outbound-email-messages).|

> [!NOTE]
> The SMTP connector functions in the same way as previously in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Set Up Email](admin-how-setup-email.md).

## Set Up Email Accounts
To quickly add an account, use the **Set up email** assisted setup guide to complete the process.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Setup Email Accounts**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 

## Assign Accounts to Business Scenarios
You can use specific email accounts for specific business scenarios. For example, you can specify that all users always send sales documents from one account, purchase documents from another, and warehouse or production documents from a third account.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Accounts**, and then choose the related link.
2. Choose the account to define scenarios for, and then choose **Process**, and then **Setup Email Scenarios**.
3. Choose **Add Scenarios**, and then choose the scenarios.

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

## See Also
[Set Up Email](admin-how-setup-email.md)
[Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as Your Business Inbox in Outlook](admin-outlook.md)  
[Getting [!INCLUDE[d365fin](includes/d365fin_md.md)] on My Mobile Device](install-mobile-app.md)