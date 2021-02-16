---
title: Set up email in Business Central | Microsoft Docs
description: Describes how to connect email accounts to Business Central so that you can send outbound messages without having to open another app.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, email, Office 365, connector
ms.date: 06/15/2020
ms.author: bholtorf

---
# Set Up Email
People in businesses send information and documents, such as sales and purchase orders and invoices, by email every day. Administrators can make that easier to do by connecting one or more email accounts to [!INCLUDE[prod_short](includes/prod_short.md)], so you can send documents without having to open an email app. You can compose each message individually with basic formatting tools, such as fonts, styles, colors, and so on, and add attachments of up to 100MB. Administrators can also set up report layouts that include only the key information from documents. For more information, see [Send Documents by Email](ui-how-send-documents-email.md).

The email capabilities in [!INCLUDE[prod_short](includes/prod_short.md)] are for outbound messages only. You cannot receive replies, that is, there is no inbox page in [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> If you are using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, before you can set up email you must create an app registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Azure portal. The app registration will enable [!INCLUDE[prod_short](includes/prod_short.md)] to authorize and authenticate with your email provider. For more information, see [Setting Up Email for Business Central On-Premises](admin-how-setup-email.md#setting-up-email-for-business-central-on-premises). In [!INCLUDE[prod_short](includes/prod_short.md)] online, we handle this for you.

## Required Permissions
To set up email, you must have the **EMAIL SETUP** permission set. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md). 

## Adding Email Accounts
You add email accounts through extensions that enable accounts from different providers to connect to [!INCLUDE[prod_short](includes/prod_short.md)]. The standard extensions let you use accounts from Microsoft Exchange Online, but other extensions may be available that let you connect accounts from other providers, such as Gmail.

After you add an email account, you can specify predefined business scenarios in which to use the account to send emails. For example, you can specify that all users send sales documents from one account, and purchase documents from another. For more information, see [Assign Email Scenarios to Email Accounts](admin-how-setup-email.md#assign-email-scenarios-to-email-accounts).

The following table describes the email extensions that are available by default.

|Extension  |Description  |Examples of when to use  |
|---------|---------|---------|
|**Microsoft 365**|Everyone sends email from a shared mailbox in Exchange Online.|When all messages come from the same department, for example, your sales organization sends messages from a sales@cronus.com account. This requires that you set up a shared mailbox in the Office 365 admin center. For more information, see [Shared mailboxes](/Exchange/collaboration/shared-mailboxes/shared-mailboxes).|
|**Current User**|Everyone sends email from the account they used to sign in to [!INCLUDE[prod_short](includes/prod_short.md)].|Allow communications from individual accounts.|
|**Other (SMTP)**|Use SMTP protocol to send emails.|Allow communications through your SMTP mail server. |

> [!NOTE]
> The **Microsoft 365** and **Current User** extensions use the accounts you set up for users in the Microsoft 365 admin center for your Office 365 subscription. To send email using the extensions, users must have a valid license for Exchange Online. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4JsUk]

## Legacy SMTP Settings and the Email - SMTP Connector Extension
If you're already using [!INCLUDE[prod_short](includes/prod_short.md)] and have configured email through the legacy SMTP setup, you can continue using your setup in parallel with the Email - SMTP Connector extension. When we update your [!INCLUDE[prod_short](includes/prod_short.md)] to the next release version, we will copy your legacy SMTP settings to the Email - SMTP Connector extension. When ready, your administrator can turn on the enhanced email capabilities and you will start using the Email - SMTP Connector extension. For more information, see [About Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management#about-feature-management). However, there is no synchronization between the SMTP Connector extension and the legacy settings. If you change the SMTP settings in the extension, you should make the same changes in the legacy SMTP setup, or vice versa.

> [!NOTE]
> If you have customizations that rely on the legacy SMTP email setup, there is a chance that something will go wrong with your customizations if you start using email extensions. We recommend that you set up and test the extensions before you turn on the feature switch for enhanced email capabilities.

## Add Email Accounts
The **Set Up Email** assisted setup guide can help you get started quickly with emails.

> [!NOTE]
> You must have a default email account, even if you add only one account. The default account will be used for all email scenarios that are not assigned to an account. For more information, see [Assign Email Scenarios to Email Accounts](admin-how-setup-email.md#assign-email-scenarios-to-email-accounts).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Set Up Email Accounts**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 

<!--
> [!NOTE]
> If you choose **Other (SMTP)** and are using an account that requires two-factor authentication, the password that you enter in the **Password** field must be the same that you use for your Office 365 subscription, and it must be of type **App Password**. For more information, see [Manage app passwords for two-step verification](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords). 

is this still true?-->
## Assign Email Scenarios to Email Accounts
Email scenarios are processes that involve sending a document, such as a sales or purchase order, or a notification, such as an invitation to an external accountant. You can use specific email accounts for specific scenarios. For example, you can specify that all users always send sales documents from one account, purchase documents from another, and warehouse or production documents from a third account. You can assign, reassign, and remove scenarios whenever you want, but you can only assign a scenario to one email account at a time. The default email account will be used for all scenarios that are not assigned to an account.
 
<!--
## To set up email
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > If you are using an account that requires two-factor authentication, then the password that you enter in the **Password** field must be the same that you use for your Microsoft 365 subscription and it must be of type **App Password**. For more information, see [Manage app passwords for two-step verification](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords).
3. Alternatively, choose the **Apply Microsoft 365 Server Settings** action to insert any information that is already defined for your Microsoft 365 subscription.
4. When all the fields are correctly filled in, choose the **Test Email Setup** action.
5. When the test succeeds, close the page.

-->

## Set Up Reusable Email Texts and Layouts for Sales and Purchase Documents
You can use reports to include key information from sales and purchase documents in texts for emails. This procedure describes how to set up the **Sales - Invoice** report for posted sales invoices, but the process is similar for other reports.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selections Sales**, and then choose the related link.
2. On the **Report Selection - Sales** page, in the **Usage** field, select **Invoice**.
3. On a new line, in the **Report ID** field, select, for example, standard report 1306.
4. Select the **Use for Email Body** check box.
5. Choose the **Email Body Layout Code** field, and then select a layout from the drop-down list.

    Report layouts define both the style and the content of the text in the email, including texts such as a greeting or instructions that precede the document information. You can see all available report layouts if you choose the **Select from full list**.
6. To view or edit the layout that the email text is based on, select the layout on the **Custom Report Layouts** page, and then choose the **Edit Layout** action.
7. If you want to offer customers to pay for sales electronically, you can set up the related payment service, such as PayPal, and then have the PayPal information and link inserted in the email text. For more information, see [Enable Customer Payments Through PayPal](sales-how-enable-payment-service-extensions.md).
8. Choose the **OK** button.

Now, when you choose, for example, the **Send** action on the **Posted Sales Invoice** page, the email body will contain the document information of report 1306 preceded by styled standard text according to the report layout that you selected in step 5.

## Using a Substitute Sender Address on Outbound Email Messages
If you are using the legacy SMTP settings, you can use the **Send As** or **Send on Behalf** capabilities from Microsoft Exchange to change the sender address on outbound messages. [!INCLUDE[prod_short](includes/prod_short.md)] will use the SMTP account to authenticate to Exchange, but will either substitute the sender address with the one you specify, or amend it with "on behalf of."

The following are examples of how Send As and Send on Behalf are used in [!INCLUDE[prod_short](includes/prod_short.md)]:

 * When you send documents such as purchase or sales orders to vendors and customers, you might want them to appear to come from a _noreply@yourcompanyname.com_ address.
 * When your workflow sends an approval request by email using the email address of the requestor.

> [!Note]
> You can only use one account to substitute sender addresses. That is, you cannot have one substitute address for purchasing processes, and another for sales processes.

### To set up the substitute sender address for all outbound email messages
1. In the **Exchange admin center** for your Microsoft 365 account, find the mailbox to use as the substitute address, and then copy or make a note of the address. If you need a new address, go to your Microsoft 365 admin center to create a new user and set up their mailbox.
2. In [!INCLUDE[prod_short](includes/prod_short.md)] choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
3. In the **Send As** field, enter the substitute address.
4. Copy or make a note of the address in the **User ID** field.
5. In the **Exchange admin center**, find the mailbox to use as the substitute address, and then enter the address from the **User ID** field in the **Send As** field. For more information, see [Use the EAC to assign permissions to individual mailboxes](/Exchange/recipients/mailbox-permissions?view=exchserver-2019#use-the-eac-to-assign-permissions-to-individual-mailboxes).

### To use the substitute address in approval workflows
1. In [!INCLUDE[prod_short](includes/prod_short.md)] choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
2. Copy or make a note of the address in the **User ID** field.
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval User Setup**, and then choose the related link.
4. In the **Exchange admin center**, find the mailboxes for each user listed in the **Approval User Setup** page, and in the **Send As** field enter the address from the **User ID** field of the **SMTP Email Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Manage permissions for recipients](/Exchange/recipients/mailbox-permissions?view=exchserver-2019).
5. In [!INCLUDE[prod_short](includes/prod_short.md)] choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
6. To enable substitution, turn on the **Allow Sender Substitution** toggle.

> [!Note]
> [!INCLUDE[prod_short](includes/prod_short.md)] will determine which address to display in the following order: <br><br> 1. The address specified in the **E-Mail** field on the **Approval User Setup** page for messages in a workflow. <br> 2. The address specified in the **Send As** field in the **SMTP Email Setup** page. <br> 3. The address specified in the **User ID** field in the **SMTP Email Setup** page.

## Set Up Document Sending Profiles
You can set up a preferred method of sending sales documents for each of your customers so that you do not have to select a sending option, such as whether to send the document by email or as an electronic document, every time you send a document. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

## Set Up Public Folders and Rules for Email Logging in Exchange Online
Get more out of the communications between salespeople and your existing or potential customers by tracking email exchanges, and then turning them into actionable opportunities. For more information, see [Track Email Message Exchanges Between Salespeople and Contacts](marketing-set-up-email-logging.md).  

[!INCLUDE[admin-setup-email-public-folder](includes/admin-setup-email-public-folder.md)]

Next, you connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online. For more information, see [Track Email Message Exchanges Between Salespeople and Contacts](marketing-set-up-email-logging.md).  

## Setting Up Email for Business Central On-Premises 
[!INCLUDE[prod_short](includes/prod_short.md)] on-premises can integrate with services that are based on Microsoft Azure. For example, you can use Cortana Intelligence for smarter cash flow forecasts, Power BI to visualize your business, and Exchange Online for sending email. Integration with these services is based on an app registration in Azure Active Directory. The app registration provides authentication and authorization services for communications. To use the email capabilities in [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you must register [!INCLUDE[prod_short](includes/prod_short.md)] as an app in the Azure portal, and then connect [!INCLUDE[prod_short](includes/prod_short.md)] to the app registration. The following sections describe how.

### Create an App Registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Azure Portal
The steps to register [!INCLUDE[prod_short](includes/prod_short.md)] in Azure portal are described in [Register an application in Azure Active Directory](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory). The settings that are specific to the email capabilities are the delegated permissions that you grant to your app registration. The following table lists the minimum permissions.

|API / Permission Name  |Type  |Description  |
|---------|---------|---------|
|Microsoft Graph / User.Read |Delegated|Sign in and read user profile.         |
|Microsoft Graph / Mail.ReadWrite |Delegated|Compose email messages.         |
|Microsoft Graph / Mail.Send|Delegated|Send email messages.         |
|Microsoft Graph / offline_access|Delegated|Maintain data access consent. <!--need to verify this-->|

> [!TIP]
> When you create your app registration, note the following information. You will need it to connect [!INCLUDE[prod_short](includes/prod_short.md)] to your app registration.
> 
> * Application (client) ID 
> * Redirect URI (optional)
> * Client secret

For general guidelines for registering an app, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app). 

### Connect [!INCLUDE[prod_short](includes/prod_short.md)] to Your App Registration
After you register your application in Azure portal, in [!INCLUDE[prod_short](includes/prod_short.md)], use the **Email Application AAD Registration** assisted setup guide to connect [!INCLUDE[prod_short](includes/prod_short.md)] to it.

1. In [!INCLUDE[prod_short](includes/prod_short.md)], choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Application AAD Registration**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> Alternatively, if you are connecting for the first time, you can run the **Set up email** assisted setup guide. The guide will require the information for connecting to your app registration. <!--Need to verify this too. Ask John to clear the aad settings, delete the email accounts, and then run the guide.-->

<!--

1. In [!INCLUDE[prod_short](includes/prod_short.md)], start the **Email Application AAD Registration** assisted setup guide.
2. On the first page of the guide, copy the value in the **Redirect URL** field.
3. In Azure Active Directory, search for **App registrations**, and then open the **App registrations** page.
4. Choose **New registration**.
5. In the **Name** field, enter a name for your app.
6. Under **Supported account types**, choose either the **Accounts in any organizational directory (Any Azure AD Directory - Multitenant)** or **Accounts in any organizational directory (Any Azure AD Directory - Multitenant) and personal Microsoft accounts (/e.g. Skype, Xbox)** options, depending on your needs. If you're unsure, choose **Help me choose** for more information.
7. Under **Redirect URI (optional)**, choose **Web**, paste the URL you copied from the **Redirect URL** field in the assisted setup guide in Business Central, and then choose **Register**.
8. On the navigation pane, choose **Overview**, and then copy the value in the **Application (client) ID** field.
9. In [!INCLUDE[prod_short](includes/prod_short.md)], in the assisted setup guide, paste the ID in **Client ID** field.
10. In Azure Active Directory, on the navigation pane, choose **API permissions**, and then choose **Add a permission**.
11. On the **Request API permissions** pane, on the **Microsoft APIs** tab, choose **Microsoft Graph**.  
12. Choose **Delegated permissions**, and then in the **Select permissions** field, search for **Mail.ReadWrite**, **Mail.Send**, and **offline_access**. Choose those permissions, and then choose **Add permissions**.
13. On the navigation pane, choose **Certificates & secrets**.
14. Under **Client secrets**, choose **New client secret**.
15. Under **Add a client secret**, enter a description of the client, specify how long you want your secret to be available, and then choose **Add**.
16. When the secret is generated, copy it. 
17. In [!INCLUDE[prod_short](includes/prod_short.md)], in the assisted setup guide paste the secret in the **Client Secret field**.
18. The **Verify Registration** button becomes available. 

-->

## See Also
[Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  
[Using [!INCLUDE[prod_short](includes/prod_short.md)] as Your Business Inbox in Outlook](admin-outlook.md)  
[Getting [!INCLUDE[prod_short](includes/prod_short.md)] on My Mobile Device](install-mobile-app.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]