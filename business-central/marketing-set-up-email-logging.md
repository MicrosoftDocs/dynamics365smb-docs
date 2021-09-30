---
title: Set Up Email Logging| Microsoft Docs
description: Learn how to turn email interactions between salespeople and customers into real sales opportunities.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect, opportunity, email
ms.date: 04/01/2021
ms.author: bholtorf

---
# Track Email Message Exchanges Between Salespeople and Contacts

Get more out of the communications between salespeople and your existing or potential customers by tracking email exchanges, and then turning them into actionable opportunities. [!INCLUDE[prod_short](includes/prod_short.md)] can work with Exchange Online to keep a log of the inbound and outbound messages. You can view and analyze the contents of each message on the **Interaction Log Entries** page.

## Set up Public Folders and Rules for Email Logging in Exchange Online

[!INCLUDE[admin-setup-email-public-folder](includes/admin-setup-email-public-folder.md)]

Next, you connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online.

## Setting Up [!INCLUDE[prod_short](includes/prod_short.md)] to Log Email Messages

Get started with email logging in two easy steps:

1. Connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online for your Microsoft 365 subscription. Exchange Online handles your email messages. We've made this step easy by providing an assisted setup guide. You just need your administrator credentials for your administrator account in Microsoft 365. To start the guide, go to the **Assisted Setup** page, and then select the **Set up email logging** guide.  

2. Make sure that valid email addresses have been entered in [!INCLUDE[prod_short](includes/prod_short.md)] for your sales people and contacts, depending on whether they are potential or existing customers. To do that, for each customer or salesperson, open the **Contact** or **Salesperson/Purchaser** card and have a look in the **Email** field.

> [!Tip]
> After you complete the steps in the guide you can check whether the connection was successful. Search for **Marketing Setup**, and select **Access**, then **Functions**, and then **Validate Email Logging Setup**.

## Viewing Email Message Exchanges in the Interaction Log

[!INCLUDE[prod_short](includes/prod_short.md)] creates an entry on the **Interaction Log** page each time a salesperson and a contact exchange an email message. To view the interaction log, open the **Contact** card for the person, choose **Related**, then **History**, and then **Interaction Log Entries**. There are a few things you can do with each entry in the log, for example:

- View the content of the email message that was exchanged by selecting **Process** and then **Show Attachments**.
- Turn an email exchange into a sales opportunity - If an entry looks promising, you can turn it into an opportunity and then manage its progress toward a sale. To do this, select the entry, and then select **Process**, and then **Create Opportunity**. For more information, see [Managing Sales Opportunities](marketing-manage-sales-opportunities.md).

## Connecting On-Premises Versions to Microsoft Exchange

You can connect [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to Exchange on-premises or Exchange Online for email logging. For both versions of Exchange, settings for the connection are available on the **Marketing Setup** page. For Exchange Online, you can also use an assisted setup guide.

### Connecting to Exchange On-premises

To connect [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to Exchange on-premises, on the **Marketing Setup** page, you can use **Basic** as the **Authentication Type**, and then enter credentials for the user account for Exchange on-premises. Then turn on the **Enabled** toggle to start logging email.

### Connecting to Exchange Online

To connect to Exchange Online, you must use **OAuth2** as the **Authentication Type**. You must also register an application in Azure Active Directory, and provide the application ID, key vault secret, and the redirect URL to use. The redirect URL is pre-populated and should work for most installations. For more information, see To register an application in Azure AD for connecting from Business Central to Exchange Online below.

You must set up your installation to use HTTPS. For more information, see [Configuring SSL to Secure the Business Central Web Client Connection](/dynamics365/business-central/dev-itpro/deployment/configure-ssl-web-client-connection). If you are setting up your server to have a different home page, you can change the URL. The client secret will be saved as an encrypted string in your database.

### To register an application in Azure AD for connecting from Business Central to Exchange Online

The following steps assume that you use Azure Active Directory to manage identities and access. For more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app). If you do not use Azure Active Directory, see [Using Another Identity and Access Management Service](marketing-set-up-email-logging.md#using-another-identity-and-access-management-service). 

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

7. Under **Manage**, choose **Certificates & Secrets**, and then create a new secret for your app. You will use the secret either in [!INCLUDE[prod_short](includes/prod_short.md)], in the **Client Secret** field on the **Marketing Setup** page, or store it in secure storage and provide it in an event subscriber.
8. Choose **Overview**, and then find the **Application (client) ID** value. This is the client ID of your application. You must enter it either on the **Marketing Setup page**, in the **Client ID** field, or store it in secure storage and provide it in an event subscriber.
9. In [!INCLUDE[prod_short](includes/prod_short.md)], set up email logging on the **Marketing Setup** page, or use the **Email Logging Assisted Setup** guide for assistance with the process.
    * Provide the email account of the user on behalf of whom the scheduled job will connect to Exchange Online and process emails. The user must have a valid license for Exchange Online.
    * Provide the URL for your Exchange Online. Typically, this is the domain that you specified in the user's email address.
    * Provide the **Queue Folder Path** and **Storage Folder Path**.
10. To start logging email, turn on the **Enabled** toggle.
11. Sign in with your administrator account for Azure Active Directory (this account must have a valid license for Exchange and be an administrator in your Exchange Online). After you sign in you will be prompted to allow your registered application to sign in to Exchange Online on behalf of the organization. You must give consent to complete the setup.

   > [!NOTE]
   > If you are not prompted to sign in with your administrator account, it might be because pop ups are blocked. To sign in, allow pop-ups from https://login.microsoftonline.com.

### Using Another Identity and Access Management Service
If you are not using Azure Active Directory to manage identities and access, you will need some help from a developer. If you prefer to store the app ID and secret in a different location, you can leave the Client ID and Client Secret fields blank and write an extension to fetch the ID and secret from the location. You can provide the secret at runtime by subscribing to the OnGetEmailLoggingClientId and OnGetEmailLoggingClientSecret events in codeunit 1641 "Setup Email Logging".

### To stop logging email
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Marketing Setup**, and then choose the related link.
2. Turn off the **Enabled** toggle.

## See Also
[Managing Relationships](marketing-relationship-management.md)



[!INCLUDE[footer-include](includes/footer-banner.md)]