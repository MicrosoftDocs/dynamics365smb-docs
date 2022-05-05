---
title: Set Up Email Logging
description: Learn how to turn email interactions between salespeople and customers into real sales opportunities.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect, opportunity, email
ms.date: 03/22/2022
ms.search.form: 1680, 1811, 5076
ms.author: bholtorf

---
# Track Email Message Exchanges Between Salespeople and Contacts
Get more out of the communications between your salespeople and customers by turning email exchanges into actionable opportunities. [!INCLUDE[prod_short](includes/prod_short.md)] can work with Exchange Online to keep a log of the inbound and outbound messages. You can view and analyze the contents of each message on the **Interaction Log Entries** page.

> [!NOTE]
> In 2022 release wave 1 we've streamlined processes for setting up email logging to increase flexibility and security. If you are a new customer using that version, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the the **Email logging using the Microsoft Graph API** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

> [!IMPORTANT]
> For [!INCLUDE[prod_short](includes/prod_short.md)] online, the new experience requires that [!INCLUDE[prod_short](includes/prod_short.md)] and Exchange Online are on the same tenant.

## To set up email logging
These steps differ, depending on whether your administrator has turned on the **Email logging using the Microsoft Graph API** feature update. If the feature update isn't turned on, follow the steps on the **Current Experience** tab.

## [Current Experience](#tab/current-experience)

### Set up Public Folders and Rules for Email Logging in Exchange Online

[!INCLUDE[admin-setup-email-public-folder](includes/admin-setup-email-public-folder.md)]

Next, you connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online.

## [New Experience](#tab/new-experience)
### Set Up a Shared Mailbox and Rules for Email Logging in Exchange Online

> [!NOTE]
> These steps require administrator access for Exchange Online.

Prepare a shared mailbox in the Exchange admin center. Alternatively, you can also use Exchange Online PowerShell. For more information, see [Create a shared mailbox](/microsoft-365/admin/email/create-a-shared-mailbox) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps&preserve-view=true).

> [!NOTE]
> If you use Exchange Management PowerShell, your changes are available in the Exchange admin center after a delay. The delay might be several hours.

### Add a user account for members of the shared mailbox
The account that you'll use for email logging is an Exchange Online account. The scheduled job will use the account to connect to the shared mailbox and process emails. This account should not be associated with a specific person. Add the email account to the members for the shared mailbox. For more information, see [Use the EAC to edit shared mailbox delegation](/exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

### Allow other users to see logged emails
You can allow another user to open an email message in Exchange that is related to an interaction log entry from [!INCLUDE[prod_short](includes/prod_short.md)]. To do that, give the user ``Read`` permission to the **Archive** folder in the shared mailbox. For more information, see [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps&preserve-view=true).

### Create mail flow rules
Mail flow rules look for specific conditions on messages and take action on them. Create two mail flow rules based on the information in the following table. For more information, see [Manage mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules?preserve-view=true) and [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions?preserve-view=true).

|Purpose  |Name  |Apply this rule if...  |Do the following...  |
|---------|---------|---------|---------|
|A rule for incoming email     |Log Email Sent to This Organization|The sender is located outside the organization, and the recipient is located inside the organization|BCC the email account that is specified for the shared mailbox.|
|A rule for outgoing email     |Log Email Sent from This Organization|The sender is located inside the organization, and the recipient is located outside the organization.|BCC the email account that is specified for the shared mailbox.|

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] only processes messages in the Inbox folder in the shared mailbox. If a rule moves messages from the Inbox to another folder, those messages will not be processed. Additionally, messages in the Junk Mails folder are also ignored. 

---

## Set Up [!INCLUDE[prod_short](includes/prod_short.md)] to Log Email Messages
These steps are the same for both the current and new experiences.

Get started with email logging in two easy steps:

1. Connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online for your Microsoft 365 subscription. Exchange Online handles your email messages. We've made this step easy by providing an assisted setup guide. You just need your administrator credentials for your administrator account in Microsoft 365. To start the guide, go to the **Assisted Setup** page, and then select the **Set up email logging** guide.  

2. Make sure that the email addresses for your sales people and contacts in [!INCLUDE[prod_short](includes/prod_short.md)] are valid. To do that, for each customer or salesperson, open the **Contact** or **Salesperson/Purchaser** card and have a look in the **Email** field.

> [!Tip]
> After you complete the steps in the guide you can check whether the connection was successful. Depending on whether you're using the current or new exerience, do one of the following steps: 
>
> * **Current experience**: Search for **Marketing Setup**, choose **Access**, then **Functions**, and then **Validate Email Logging Setup**.
> * **New experience**: Search for **Email Logging**, choose **Actions**, and then choose **Validate Setup**.

## Viewing Email Message Exchanges in the Interaction Log

[!INCLUDE[prod_short](includes/prod_short.md)] creates an entry on the **Interaction Log** page each time a salesperson and a contact exchange an email message. To view the interaction log, open the **Contact** card for the person, choose **Related**, then **History**, and then **Interaction Log Entries**. There are a few things you can do with each entry in the log, for example:

- View the content of the email message that was exchanged by selecting **Process** and then **Show Attachments**.
- Turn an email exchange into a sales opportunity. If an entry looks promising, you can turn it into an opportunity and then manage its progress toward a sale. To turn an email exchange into an opportunity, choose the entry, then **Process**, and then **Create Opportunity**. For more information, see [Managing Sales Opportunities](marketing-manage-sales-opportunities.md).

## Mailbox and folder limits in Exchange Online
There are mailbox and folder limits in Exchange Online, such as limits for folder sizes and the number of messages. For more information, see [Exchange Online limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#storage-limits) and [Limits for public folders in Exchange Server](/Exchange/collaboration/public-folders/limits?view=exchserver-2019).

[!INCLUDE[prod_short](includes/prod_short.md)] stores logged email messages in a folder in Exchange Online. [!INCLUDE[prod_short](includes/prod_short.md)] also stores a link to each logged message. The links open the logged messages in Exchange Online from the Interaction Log Entries, Contact Card, and Salespersons Card pages in [!INCLUDE[prod_short](includes/prod_short.md)]. If a logged message is moved to another folder, the link will be broken. For example, a message might be moved manually, or Exchange Online might automatically start AutoSplit when a storage limit is reached.

The following steps can help you avoid breaking links to messages in Exchange Online.

1. Don't move existing messages to another folder after you change settings for your email logging setup. Keeping existing messages where they are will preserve the links. Links to messages in the new folder will be valid.
2. Avoid reaching the mailbox and folder limits. If you're about to reach a limit, take the following steps:
    1. Set up a new shared mailbox (new experience) or a new shared folder (current experience) in Exchange Online.
    2. Update your email flow rules in Exchange Online.
    3. Update your email logging setup in Business Central accordingly

## Connect On-Premises Versions to Microsoft Exchange

You can connect [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to Exchange on-premises or Exchange Online for email logging. For both versions of Exchange, settings for the connection are available on the **Marketing Setup** page. For Exchange Online, you can also use an assisted setup guide.

> [!IMPORTANT]
> The new experience doesn't support a connection to Exchange on-premises. If you must use Exchange on-premises, do not enable the feature update for the new experience.

## Connect to Exchange On-Premises
## [Current Experience](#tab/current-experience)
To connect [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to Exchange on-premises, on the **Marketing Setup** page, you can use **Basic** as the **Authentication Type**, and then enter credentials for the user account for Exchange on-premises. Then turn on the **Enabled** toggle to start logging email.

## [New Experience](#tab/new-experience)
The new experience does not support connections to Exchange on-premises.

---

## Connect to Exchange Online
To connect to Exchange Online you must register an application in Azure Active Directory. Provide the application ID, key vault secret, and the redirect URL to use for the registration. The redirect URL is pre-set and should work for most installations. For more information, see [To register an application in Azure AD for connecting from Business Central to Exchange Online](marketing-set-up-email-logging.md#to-register-an-application-in-azure-ad-for-connecting-from-business-central-to-exchange-online). 

You must also use **OAuth2** as the **Authentication Type**. You must also register an application in Azure Active Directory. Provide the application ID, key vault secret, and the redirect URL to use for the registration. The redirect URL is pre-populated and should work for most installations. For more information, see To register an application in Azure AD for connecting from Business Central to Exchange Online below.

You must set up your installation to use HTTPS. For more information, see [Configuring SSL to Secure the Business Central Web Client Connection](/dynamics365/business-central/dev-itpro/deployment/configure-ssl-web-client-connection). If you're setting up your server to have a different home page, you can change the URL. The client secret will be saved as an encrypted string in your database.

### To register an application in Azure AD for connecting from Business Central to Exchange Online
The following steps assume that you use Azure Active Directory to manage identities and access. For more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app). 

## [Current Experience](#tab/current-experience) 
The following steps assume that you use Azure Active Directory to manage identities and access. For more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app). If you do not use Azure Active Directory, see [Use Another Identity and Access Management Service](marketing-set-up-email-logging.md#use-another-identity-and-access-management-service). 

1. In the Azure Portal, under **Manage**, choose **Authentication**.
2. Under **Redirect URL**, add the redirect URL that is suggested on the **Marketing Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)]. If the redirect URL on the Marketing Setup page is empty, find the suggested redirect URL on the **Email Logging Assisted Setup** page.

    > [!NOTE]
    > If you do not specify the redirect URL, you can do so later by choosing **Add a platform**, and then choosing **Web** to add the web application and the redirect URL. 

3. Under **Manage**, choose **Manifest**.
4. Locate the **requiredResourceAccess** property in the manifest, and add the following code in the brackets ([]) to add the required permissions. For more information, see [Register your application](/exchange/client-developer/exchange-web-services/how-to-authenticate-an-ews-application-by-using-oauth#register-your-application).

```
{
    "resourceAppId": "00000002-0000-0ff1-ce00-000000000000",
    "resourceAccess": [
        {
            "id": "3b5f3d61-589b-4a3c-a359-5dd4b5ee5bd5",
            "type": "Scope"
        },
        {
            "id": "dc890d15-9560-4a4c-9b7f-a736ec74ec40",
            "type": "Role"
        }
    ]
}
```

5. Choose **Save**.
6. Under **Manage**, choose **API permissions**, and then confirm that the following permissions are listed:  

    * EWS.AccessAsUser.All
    * full_access_as_app

7. Under **Manage**, choose **Certificates & Secrets**, and then create a new secret for your app. You'll use the secret either in [!INCLUDE[prod_short](includes/prod_short.md)], in the **Client Secret** field on the **Marketing Setup** page, or store it in secure storage and provide it in an event subscriber.
8. Choose **Overview**, and then find the **Application (client) ID** value. The **Application (client) ID** value is the client ID of your application. You must enter the client ID either on the **Marketing Setup page**, in the **Client ID** field, or store it in secure storage and provide it in an event subscriber.
9. In [!INCLUDE[prod_short](includes/prod_short.md)], set up email logging on the **Marketing Setup** page, or use the **Email Logging Assisted Setup** guide for assistance with the process.
    * Provide the email account of the user on behalf of whom the scheduled job will connect to Exchange Online and process emails. The user must have a valid license for Exchange Online.
    * Provide the URL for your Exchange Online. Typically, this URL is the domain that you specified in the user's email address.
    * Provide the **Queue Folder Path** and **Storage Folder Path**.
10. To start logging email, turn on the **Enabled** toggle.
11. Sign in with your administrator account for Azure Active Directory (this account must have a valid license for Exchange and be an administrator in your Exchange Online). After you sign in, you must allow your registered application to sign in to Exchange Online on behalf of the organization. You must give consent to complete the setup.

   > [!NOTE]
   > If you are not prompted to sign in with your administrator account, it might be because pop ups are blocked. To sign in, allow pop-ups from https://login.microsoftonline.com.

## [New Experience](#tab/new-experience)
1. In the Azure Portal, under **Manage**, choose **Authentication**.
2. Under **Redirect URL**, add the redirect URL that is suggested on the **Email Logging** page in [!INCLUDE[prod_short](includes/prod_short.md)]. If the redirect URL field on the Email Logging page is empty, find the suggested redirect URL on the **Assisted Setup** page. To open the page, on the **Email Logging** page, choose **Actions**, and then **Assisted Setup**.

    > [!NOTE]
    > If you do not specify the redirect URL, you can do so later by choosing **Add a platform**, and then choosing **Web** to add the web application and the redirect URL.

3. Under **Manage**, choose **API permissions**, and choose **Microsoft Graph**, and then choose **Delegated permissions**.
4. Use the search box to find and select **Mail**, and then add the **Mail.ReadWrite.Shared** permission. 
5. Under **Manage**, choose **Certificates & Secrets**, and then create a new secret for your app. You'll use the secret either in the **Client Secret** field on the **Email Logging** page in [!INCLUDE[prod_short](includes/prod_short.md)].
6. Choose **Overview**, and then find the **Application (client) ID** value. This is the client ID of your application. You must enter it either in the **Client ID** field on the **Email Logging** page.
7. In [!INCLUDE[prod_short](includes/prod_short.md)], set up email logging on the **Email Logging** page, or use the **Assisted Setup** guide for assistance.

### Use Another Identity and Access Management Service
If you are not using Azure Active Directory to manage identities and access, you will need some help from a developer. If you prefer to store the app ID and secret in a different location, you can leave the Client ID and Client Secret fields blank and write an extension to fetch the ID and secret from the location. You can provide the secret at runtime by subscribing to the OnGetEmailLoggingClientId and OnGetEmailLoggingClientSecret events in codeunit 1641 "Setup Email Logging".

---

## To start logging email
1. To start logging email, on the **Email Logging** page, turn on the **Enabled** toggle.
2. Sign in with the Exchange Online account that the scheduled job will use to connect to the shared mailbox and process emails.

    > [!NOTE]
    > If you are not prompted to sign in the the Exchange Online account, it might be because your browser is blocking pop-ups. To sign in, allow pop-ups from https://login.microsoftonline.com.

## To stop logging email
## [Current Experience](#tab/current-experience)
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Marketing Setup**, and then choose the related link.
1. Turn off the **Enabled** toggle.

## [New Experience](#tab/new-experience)
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Logging**, and then choose the related link.
2. Turn off the **Enabled** toggle.

---

## To change the user account used for email logging
If you are using the new experience, you can change the user account used for email logging. The current experience doesn't support this.

## [Current Experience](#tab/current-experience) 
Disable your current setup, change the user on the **Email Logging** page, and then re-enable email logging. You can also run the assisted setup guide again.

## [New Experience](#tab/new-experience)
### [!INCLUDE[prod_short](includes/prod_short.md)] Online
1. Sign in to [!INCLUDE[prod_short](includes/prod_short.md)] with the account that the scheduled job will use to connect to the shared mailbox and process emails. This account must have access to both [!INCLUDE[prod_short](includes/prod_short.md)] and Exchange Online.
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Logging**, and then choose the related link. 
3. Choose **Related**, and then **Job Queue Entry**.
4. Restart the **Email Logging** job.

### [!INCLUDE[prod_short](includes/prod_short.md)] On-Premises
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Logging**, and then choose the related link. 
2. Choose **Actions**, and then **Renew Token**.
3. Sign in with the Exchange Online account that the scheduled job will use to connect to the shared mailbox and process emails.



## See Also
[Managing Relationships](marketing-relationship-management.md)



[!INCLUDE[footer-include](includes/footer-banner.md)]