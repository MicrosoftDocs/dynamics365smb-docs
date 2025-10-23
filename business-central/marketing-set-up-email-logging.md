---
title: Set up email logging
description: Learn how to turn email interactions between salespeople and customers into real sales opportunities.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.date: 10/03/2025
ms.custom: bap-template
ms.search.keywords: relationship, prospect, opportunity, email
ms.search.form: 1680, 1811, 5076
ms.service: dynamics-365-business-central
---

# Track email message exchanges between salespeople and contacts

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Get more out of the communications between your salespeople and customers by turning email exchanges into actionable opportunities. [!INCLUDE[prod_short](includes/prod_short.md)] can work with Exchange Online to keep a log of the inbound and outbound messages. You can view and analyze the contents of each message on the **Interaction Log Entries** page.

> [!IMPORTANT]
> For [!INCLUDE[prod_short](includes/prod_short.md)] online, [!INCLUDE[prod_short](includes/prod_short.md)] and Exchange Online must be on the same tenant.

## Set up email logging

### Set up public folders and rules for email logging in Exchange Online

[!INCLUDE[admin-setup-email-public-folder](includes/admin-setup-email-public-folder.md)]

Next, you connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online.

### Set up a shared mailbox and rules for email logging in Exchange Online

> [!NOTE]
> These steps require administrator access for Exchange Online.

Prepare a shared mailbox in the Exchange admin center. Alternatively, you can also use Exchange Online PowerShell. Learn more in [Create a shared mailbox](/microsoft-365/admin/email/create-a-shared-mailbox) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps&preserve-view=true).

> [!NOTE]
> If you use Exchange Management PowerShell, your changes are available in the Exchange admin center after a delay. The delay might be several hours.

### Add a user account for members of the shared mailbox

The account that you use for email logging is an Exchange Online account. The scheduled job uses the account to connect to the shared mailbox and process emails. This account shouldn't be associated with a specific person. Add the email account to the members for the shared mailbox. Learn more in [Use the EAC to edit shared mailbox delegation](/exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

### Allow other users to see logged emails

You can allow another user to open an email message in Exchange that is related to an interaction log entry from [!INCLUDE[prod_short](includes/prod_short.md)]. To do that, give the user ``Read`` permission to the **Archive** folder in the shared mailbox. Learn more in [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps&preserve-view=true).

### Create mail flow rules

Mail flow rules look for specific conditions on messages and take action on them. Create two mail flow rules based on the information in the following table. Learn more in [Manage mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules?preserve-view=true) and [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions?preserve-view=true).

| Purpose | Name | Apply this rule if... | Do the following... |
|--|--|--|--|
| A rule for incoming email | Log Email Sent to This Organization | The sender is located outside the organization, and the recipient is located inside the organization | BCC the email account that is specified for the shared mailbox. |
| A rule for outgoing email | Log Email Sent from This Organization | The sender is located inside the organization, and the recipient is located outside the organization. | BCC the email account that is specified for the shared mailbox. |

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] only processes messages in the Inbox folder in the shared mailbox. If a rule moves messages from the Inbox to another folder, those messages aren't processed. Additionally, messages in the Junk Mails folder are also ignored.

## Set up [!INCLUDE[prod_short](includes/prod_short.md)] to log email messages

Get started with email logging in two easy steps:

1. Connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online for your Microsoft 365 subscription. Exchange Online handles your email messages. We made this step easy by providing an assisted setup guide. You just need your administrator credentials for your administrator account in Microsoft 365. To start the guide, go to the **Assisted Setup** page, and then select the **Set up email logging** guide.  

2. Make sure that the email addresses for your sales people and contacts in [!INCLUDE[prod_short](includes/prod_short.md)] are valid. To do that, for each customer or salesperson, open the **Contact** or **Salesperson/Purchaser** card and have a look in the **Email** field.

    > [!Tip]
    > After you complete the steps in the guide you can check whether the connection was successful. Search for **Email Logging**, choose **Actions**, and then choose **Validate Setup**.

## View email message exchanges in the Interaction Log

[!INCLUDE[prod_short](includes/prod_short.md)] creates an entry on the **Interaction Log** page each time a salesperson and a contact exchange an email message. To view the interaction log, open the **Contact** card for the person, choose **Related**, then **History**, and then **Interaction Log Entries**. There are a few things you can do with each entry in the log, for example:

* View the content of the email message that was exchanged by selecting **Process** and then **Show Attachments**.
* Turn an email exchange into a sales opportunity. If an entry looks promising, you can turn it into an opportunity and then manage its progress toward a sale. To turn an email exchange into an opportunity, choose the entry, then **Process**, and then **Create Opportunity**. Learn more in [Managing Sales Opportunities](marketing-manage-sales-opportunities.md).

## Mailbox and folder limits in Exchange Online

There are mailbox and folder limits in Exchange Online, such as limits for folder sizes and the number of messages. Learn more in [Exchange Online limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#storage-limits) and [Limits for public folders in Exchange Server](/Exchange/collaboration/public-folders/limits?view=exchserver-2019&preserve-view=true).

[!INCLUDE[prod_short](includes/prod_short.md)] stores logged email messages in a folder in Exchange Online. [!INCLUDE[prod_short](includes/prod_short.md)] also stores a link to each logged message. The links open the logged messages in Exchange Online from the Interaction Log Entries, Contact Card, and Salespersons Card pages in [!INCLUDE[prod_short](includes/prod_short.md)]. If a logged message is moved to another folder, the link is broken. For example, a message might be moved manually, or Exchange Online might automatically start AutoSplit when a storage limit is reached.

The following steps can help you avoid breaking links to messages in Exchange Online.

1. Don't move existing messages to another folder after you change settings for your email logging setup. Keeping existing messages put preserves the links. Links to messages in the new folder are valid.
2. Avoid reaching the mailbox and folder limits. If you're about to reach a limit, take the following steps:
    1. Set up a new shared mailbox in Exchange Online.
    2. Update your email flow rules in Exchange Online.
    3. Update your email logging setup in Business Central accordingly

## Connect on-premises versions to Microsoft Exchange

You can connect [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to Exchange on-premises or Exchange Online for email logging. For both versions of Exchange, settings for the connection are available on the **Marketing Setup** page. For Exchange Online, you can also use an assisted setup guide.

<!-- [!IMPORTANT]
> The new experience doesn't support a connection to Exchange on-premises. If you must use Exchange on-premises, do not enable the feature update for the new experience.

## Connect to Exchange on-premises
<!--
## [Current Experience](#tab/current-experience)
To connect [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to Exchange on-premises, on the **Marketing Setup** page, you can use **Basic** as the **Authentication Type**, and then enter credentials for the user account for Exchange on-premises. Then turn on the **Enabled** toggle to start logging email.

## [New Experience](#tab/new-experience)
The new experience does not support connections to Exchange on-premises.
-->
## Connect to Exchange Online

To connect to Exchange Online, you must register an application in Microsoft Entra ID. Provide the application ID, key vault secret, and the redirect URL to use for the registration. The redirect URL is preset and should work for most installations. Learn more in [To register an application in Microsoft Entra ID for connecting from Business Central to Exchange Online](#register-an-application-in-microsoft-entra-id-for-connecting-from-business-central-to-exchange-online).

You must also use **OAuth2** as the **Authentication Type**. You must also register an application in Microsoft Entra ID. Provide the application ID, key vault secret, and the redirect URL to use for the registration. The redirect URL is prepopulated and should work for most installations. Learn more in [To register an application in Microsoft Entra ID for connecting from Business Central to Exchange Online](#register-an-application-in-microsoft-entra-id-for-connecting-from-business-central-to-exchange-online).

You must set up your installation to use HTTPS. Learn more in [Configuring SSL to Secure the Business Central Web Client Connection](/dynamics365/business-central/dev-itpro/deployment/configure-ssl-web-client-connection). If you're setting up your server to have a different home page, you can change the URL. The client secret is saved as an encrypted string in your database.

### Register an application in Microsoft Entra ID for connecting from Business Central to Exchange Online

The following steps assume that you use Microsoft Entra ID to manage identities and access. Learn more in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).

1. In the Azure portal, under **Manage**, choose **Authentication**.
2. Under **Redirect URL**, add the redirect URL that is suggested on the **Email Logging** page in [!INCLUDE[prod_short](includes/prod_short.md)]. If the redirect URL field on the Email Logging page is empty, find the suggested redirect URL on the **Assisted Setup** page. To open the page, on the **Email Logging** page, choose **Actions**, and then **Assisted Setup**.

    > [!NOTE]
    > If you don't specify the redirect URL, you can do so later by choosing **Add a platform**, and then choosing **Web** to add the web application and the redirect URL.

3. Under **Manage**, choose **API permissions**, and choose **Microsoft Graph**, and then choose **Delegated permissions**.
4. Use the search box to find and select **Mail**, and then add the **Mail.ReadWrite.Shared** permission.
5. Under **Manage**, choose **Certificates & Secrets**, and then create a new secret for your app. You use the secret either in the **Client Secret** field on the **Email Logging** page in [!INCLUDE[prod_short](includes/prod_short.md)].
6. Choose **Overview**, and then find the **Application (client) ID** value. This value is the client ID of your application. You must enter it either in the **Client ID** field on the **Email Logging** page.
7. In [!INCLUDE[prod_short](includes/prod_short.md)], set up email logging on the **Email Logging** page, or use the **Assisted Setup** guide for assistance.

### Use another identity and access management service

If you aren't using Microsoft Entra ID to manage identities and access, you need some help from a developer. If you prefer to store the app ID and secret in a different location, you can leave the Client ID and Client Secret fields blank and write an extension to fetch the ID and secret from the location. You can provide the secret at runtime by subscribing to the OnGetEmailLoggingClientId and OnGetEmailLoggingClientSecret events in codeunit 1641 "Setup Email Logging."

## Start logging email

1. To start logging email, on the **Email Logging** page, turn on the **Enabled** toggle.
2. Sign in with the Exchange Online account that the scheduled job uses to connect to the shared mailbox and process emails.

    > [!NOTE]
    > If you aren't prompted to sign in the Exchange Online account, it might be because your browser is blocking pop-ups. To sign in, allow pop-ups from https://login.microsoftonline.com.

## Stop logging email

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Email Logging**, and then choose the related link.
2. Turn off the **Enabled** toggle.

## Change the user account used for email logging

### [!INCLUDE[prod_short](includes/prod_short.md)] Online

1. Sign in to [!INCLUDE[prod_short](includes/prod_short.md)] with the account that the scheduled job uses to connect to the shared mailbox and process emails. This account must have access to both [!INCLUDE[prod_short](includes/prod_short.md)] and Exchange Online.
2. [!INCLUDE[open-search](includes/open-search.md)], enter **Email Logging**, and then choose the related link. 
3. Choose **Related**, and then **Job Queue Entry**.
4. Restart the **Email Logging** job.

### [!INCLUDE[prod_short](includes/prod_short.md)] on-premises

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Email Logging**, and then choose the related link.
2. Choose **Actions**, and then **Renew Token**.
3. Sign in with the Exchange Online account that the scheduled job uses to connect to the shared mailbox and process emails.

## Related information

[Manage Relationships](marketing-relationship-management.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]