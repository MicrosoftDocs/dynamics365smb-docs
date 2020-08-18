---
title: Set up email in Business Central | Microsoft Docs
description: Describes how to use the company's SMTP server to send and receive email messages within Business Central, or alternatively how to use the email server settings created with the Office 365 subscription.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, email, Office 365
ms.date: 06/15/2020
ms.author: bholtorf

---
# Set Up Email
> [!Important]
> 2020 release wave 2 offers improved email capabilities. If you're new to [!INCLUDE[d365fin](includes/d365fin_md.md)], the new capabilities are already turned on. If you are already using [!INCLUDE[d365fin](includes/d365fin_md.md)] and have configured email through SMTP, you can continue using your current setup. When you are ready, your administrator can turn on the new email capabilities. For more information, see [About Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management.md#about-feature-management). 
>
> If you have customized the email capabilities, for example, through an extension, there is a chance that something will go wrong with your customizations if you start  using the new email connectors. We recommend that you set up and test the new capabilities before you turn on the feature switch.

You can connect one or more email accounts to [!INCLUDE[d365fin](includes/d365fin_md.md)] send email messages without having to switch apps. You can compose each message individually with basic formatting tools (fonts, styles, colors, and so on) and add attachments (up to 100MB), or create templates that contain pre-defined, reusable texts. For more information, see [Send Documents by Email](ui-how-send-documents-email.md).

To use email features, you can either use the email connectors we provide or build an app yourself and connect to it. The latter will probably require the help of a partner.

## About Email Connectors
You add email accounts to [!INCLUDE[d365fin](includes/d365fin_md.md)] through email connectors. You can have as many connectors as you want, but only one of each type, though you can have multiple email accounts for each connector. The following table describes the standard email connectors that are available in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Other email connectors, such as the Outlook connector, are available in Extension Marketplace. For more information, see [Installing an Extension](/dynamics365/business-central/ui-extensions#installing-an-extension).

|Account Type  |Description  |Examples of when to use  |
|---------|---------|---------|
|Microsoft 365     |Everyone sends email from a shared mailbox.|When all messages come from the same department, for example, your sales organization sends messages from a sales@cronus.com account. For more information, see [Shared mailboxes](/Exchange/collaboration/shared-mailboxes/shared-mailboxes.md).|
|Current User  |Everyone sends email from the account they used to sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)].|Allow communications from individual accounts.|
|Other (SMTP)     |Use SMTP protocol to send emails.|Specific account. Everyone sends email from the account you specify. You can, however, use the **Send As** or **Send on Behalf** capabilities on your Exchange server to change the sender address on outbound messages. For more information, see [Using a Substitute Sender Address on Outbound Email Messages](/dynamics365/business-central/admin-how-setup-email.md#using-a-substitute-sender-address-on-outbound-email-messages).|

> [!NOTE]
> The SMTP connector functions in the same way as previously in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Set Up Email](admin-how-setup-email.md).

## Set Up Email
To quickly add an account, use the **Set up email** assisted setup guide to complete the process.

> [!TIP]
> If you are converting an existing SMTP email setup to use the capabilities available in 2020 release wave 2, you can set everything up and test your settings before you turn on the feature switch to start using the new capabilities. 

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Setup Email Accounts**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 

    > [!NOTE]
    > You must always have a default email account, even if you add only one account. The default account will be used for all scenarios for which an account is not specified. For more information, see [Assign Accounts to Email Scenarios](admin-how-setup-email.md#assign-accounts-to-email-scenarios).

    > [!NOTE]
    > If you choose **Other (SMTP)** and are using an account that requires two-factor authentication, the password that you enter in the **Password** field must be the same that you use for your Office 365 subscription and it must be of type **App Password**. For more information, see [Manage app passwords for two-step verification](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords).

### Assign Accounts to Email Scenarios
Email scenarios are processes that involve sending a document, such as a sales or purchase order, or a notification, such as an invitation to an external accountant. You can use specific email accounts for specific scenarios. For example, you can specify that all users always send sales documents from one account, purchase documents from another, and warehouse or production documents from a third account. You can only assign a scenario to one email account. 

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Accounts**, and then choose the related link.
2. Choose the account to define scenarios for, and then choose **Process**, and then **Setup Email Scenarios**.
3. Choose **Assign Scenarios**, and then choose the scenarios.

### Using a Substitute Sender Address on Outbound Email Messages
All outgoing email messages from [!INCLUDE[d365fin](includes/d365fin_md.md)] will use the default address for the account that you specified on the SMTP Email Setup page, as described above. You can, however, use the **Send As** or **Send on Behalf** capabilities on your Exchange server to change the sender address on outbound messages. [!INCLUDE[d365fin](includes/d365fin_md.md)] will use the default account to authenticate to Exchange, but will either substitute the sender address with the one you specify, or amend it with "on behalf of."

The following are examples of how Send As and Send on Behalf are used in [!INCLUDE[d365fin](includes/d365fin_md.md)].:

 * When you send documents such as purchase or sales orders to vendors and customers, you might want them to appear to come from a _noreply@yourcompanyname.com_ address.
 * When your workflow sends an approval request by email using the email address of the requestor.

> [!Note]
> You can only use one account to substitute sender addresses. That is, you cannot have one substitute address for purchasing processes, and another for sales processes.

#### To set up the substitute sender address for all outbound email messages
1. In the **Exchange admin center** for your Office 365 account, find the mailbox to use as the substitute address, and then copy or make a note of the address. If you need a new address, go to your Microsoft 365 admin center to create a new user and set up their mailbox.
2. In [!INCLUDE[d365fin](includes/d365fin_md.md)] choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
3. In the **Send As** field, enter the substitute address.
4. Copy or make a note of the address in the **User ID** field.
5. In the **Exchange admin center**, find the mailbox to use as the substitute address, and then enter the address from the **User ID** field in the **Send As** field. For more information, see [Use the EAC to assign permissions to individual mailboxes](/Exchange/recipients/mailbox-permissions?view=exchserver-2019#use-the-eac-to-assign-permissions-to-individual-mailboxes).

#### To use the substitute address in approval workflows

1. In [!INCLUDE[d365fin](includes/d365fin_md.md)] choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
2. Copy or make a note of the address in the **User ID** field.
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval User Setup**, and then choose the related link.
4. In the **Exchange admin center**, find the mailboxes for each user listed in the **Approval User Setup** page, and in the **Send As** field enter the address from the **User ID** field of the **SMTP Email Setup** page in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Manage permissions for recipients](/Exchange/recipients/mailbox-permissions?view=exchserver-2019).
5. In [!INCLUDE[d365fin](includes/d365fin_md.md)] choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
6. To enable substitution, turn on the **Allow Sender Substitution** toggle.

> [!Note]
> [!INCLUDE[d365fin](includes/d365fin_md.md)] will determine which address to display in the following order: <br><br> 1. The address specified in the **E-Mail** field on the **Approval User Setup** page for messages in a workflow. <br> 2. The address specified in the **Send As** field in the **SMTP Email Setup** page. <br> 3. The address specified in the **User ID** field in the **SMTP Email Setup** page.

### Set Up Public Folders and Rules for Email Logging in Exchange Online
Get more out of the communications between salespeople and your existing or potential customers by tracking email exchanges, and then turning them into actionable opportunities. For more information, see [Track Email Message Exchanges Between Salespeople and Contacts](marketing-set-up-email-logging.md).  

[!INCLUDE[admin-setup-email-public-folder](includes/admin-setup-email-public-folder.md)]

Next, you connect [!INCLUDE[prodshort](includes/prodshort.md)] with Exchange Online. For more information, see [Track Email Message Exchanges Between Salespeople and Contacts](marketing-set-up-email-logging.md).  

## See Also

[Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as Your Business Inbox in Outlook](admin-outlook.md)  
[Getting [!INCLUDE[d365fin](includes/d365fin_md.md)] on My Mobile Device](install-mobile-app.md)
