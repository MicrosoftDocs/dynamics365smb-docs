---
    title: How to Set Up Email Logging | Microsoft Docs
    description: You set up email logging in the **Marketing Setup** window. Setup requires an email account that has a valid email address on Exchange. It also requires that you use public folders. This enables you to share and log information and email in a company.
    services: project-madeira
    documentationcenter: ''
    author: brentholtorf
    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: email, log, logging, marketing, interaction
    ms.date: 09/01/2017
    ms.author: bholtorf
---
# Set Up Email Logging
You set up email logging in the **Marketing Setup** window. Setup requires an email account that has a valid email address on Exchange. It also requires that you use public folders. This enables you to share and log information and email in a company.  
  
> [!NOTE]  
>  Consider creating a domain user email account that is not tied to specific individual. If you do this, you will also have to add the domain account to [!INCLUDE[d365fin](includes/d365fin_md.md)] as a Windows user who has the relevant permission set. For more information, see [Manage Users and Permissions](ui-how-users-permissions.md).  
  
To set up email logging you will need a CRONUS International Ltd. demonstration database. You must also have configured public folders on your Exchange Server. For more information about configuring public folders in Exchange Server, see [Public folders](http://go.microsoft.com/fwlink/?LinkId=526140).  
  
You can set up email logging for use with Exchange Server and with Exchange Online.  

If you decide to stop using email logging, you can undo all settings for the email logging setup by choossing the **Clear Email Logging Setup** action.  
  
## To set up email logging    
1. Choose the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Marketing Setup**, and then choose the related link.  
2. Expand the **Email Logging** FastTab to enter information to enable email logging.  
3. In the **Autodiscovery E-Mail Address** field, enter the email address that you want to use to enable the discovery and identification of your Exchange connection.  
4. If you use Exchange Online, you must also specify the following fields:  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Exchange Service URL**|Optionally, specify the URL for your Exchange service.<br /><br /> If you specify this URL, [!INCLUDE[d365fin](includes/d365fin_md.md)] connects faster to Exchange when you choose **Validate Email Logging Setup**.|  
    |**Exchange Account User Name**|Specify the name of the user account that has access to Exchange.|  
    |**Exchange Account User Password**|Specify the password of the user account that has access to Exchange.|  
  
5. In the **Queue Folder Path** and **Storage Folder Path** fields, choose the **AssistEdit** button to open the **Exchange Public Folders** window.  
6. For each field, select the public folder that you have set up for email logging. On the **Home** tab, in the **Process** group, choose **Get Subfolders**. If you have to access subfolders, select the folder, and choose **Get Subfolders** again. Expand the folder directory to reach the **Queue** and **Storage** folders that you have created.  
  
    > [!NOTE]  
    >  [!INCLUDE[d365fin](includes/d365fin_md.md)] does not support folder paths that are longer than 250 characters. Accordingly, you should set up your public folder structure to be able to handle this limitation.  
  
7. In the **Email Batch Size** field, enter the number of emails that you want to process at a time. You can use the value that you specify to address performance issues.  
8. To make sure that the address is valid on an Exchange Server, choose the **Validate Email Logging Setup** action.  
  
When setup is complete, you can set up a job queue to start the process of having your email interactions logged on a regular or one-time basis. For more information, see the next section in this topic.  
  
## To set up email logging for use with the Job Queue
You can run regular background processing such as email logging using a job queue. In the following procedure, you configure the server<!--ADD INCLUDE [!INCLUDE[nav_server](includes/nav_server_md.md)]-->. When you do this, you can decide whether it makes sense in your installation to set up a unique server instance to manage your email logging. Any instance that you set up must have access to the Exchange Server and run as a user account with that access.  
  
> [!NOTE]  
>  When you are using public folders in a multiple Exchange Server environment, you may encounter delays in seeing a mail message synchronize among the servers. For example, a mail message on one server can take several minutes to be synchronized with another server on the same domain. This can manifest itself when you are using email logging with job queues.  
  
To use email logging, you must be connected to Microsoft Exchange Server and have an email account.  
  
> [!NOTE]  
>  The email account that is used to configure email logging in [!INCLUDE[d365fin](includes/d365fin_md.md)] must have certain permissions with regard to the public folders.  
>   
>  * When you set up email logging in the **Marketing Setup** window, the user name that is used to validate the setup must have **Read** access to the public folders.  
>  * When email logging is running, the user account credentials that are used on the server instance must have full **Read**, **Write**, and **Delete items** permission levels set on the public folders.  
>   
>  For more information, see [Managing Public Folder Permissions](http://go.microsoft.com/fwlink/?LinkId=246183).  
  
### To set up Microsoft Dynamics NAV Server  
1. Open Microsoft Dynamics NAV Server Administration tool.  
2. Create a new server instance that uses a user account for the service account. The user account must have an account on an Exchange Server. <!--For more information, see [Create a Microsoft Dynamics NAV Server Instance](../How%20to:%20Create%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance.md).-->  
  
<!--> [!NOTE]  
   >  The user must have sufficient <!-- ADD INCLUDE [!INCLUDE[navnow](includes/demolong_md.md)]-->.  
  
3. Choose the **Edit** action, and then enter the parameter **450** in the **Startup Codeunit** field. In the **Company** field, enter the name of the company.  
4. Choose **Save**, and then choose **OK**.  
5. Start the server instance.  
6. If there are errors in starting the queue, you can check the event viewer log. In **Control Panel**, open **Administrative Tools**, and then choose **Event Viewer**.  
7. Choose **Windows Logs**, and then choose **Application** to open the Services snap-in.  
  
 Review the error message and make modifications as needed. After you have verified that the server instance is running correctly, you can stop it from running. Then, set up a job queue to run on the server instance.  

## Connecting On-Premises Versions
To connect Business Central on-premises to Exchange for email logging, you must specify some information on the **Marketing Setup** page, or run the assisted setup guide for email logging.

If you want to connect using a Microsoft Entra ID  account, you must register an application in Microsoft Entra ID, and provide the application ID, key vault secret, and the redirect URL to use. The redirect URL is pre-populated and should work for most installations. You must set up your installation to use HTTPS. For more information, see [Configuring SSL to Secure the Business Central Web Client Connection](/dynamics365/business-central/dev-itpro/deployment/configure-ssl-web-client-connection.md). If you are setting up your server to have a different home page, you can always change the URL. The client secret will be saved as an encrypted string in your database.

### Connecting Business Central to Microsoft Exchange
The following steps assume that you use Microsoft Entra ID to manage identities and access. 

To connect Business Central on-premesis to Microsoft Exchange, you must register an application in Microsoft Entra ID. For more information, see see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app.md). If you do not use Microsoft Entra ID, see [Using Another Identity and Access Management Service](how-to-set-up-email-logging.md#using-another-identity-and-access-management-service).

1.	In the Azure Portal, under **Manage** on the Navigation Pane, choose **Authentication**.
2.	Under **Redirect URL**, add the redirect URL that is suggested on the **Marketing Setup** page in Business Central. If the redirect URL on the Marketing Setup page is empty, then find the suggested redirect URL on the **Email Logging Assisted Setup** page.
3.	Under **Manage**, choose **API permissions**.
4.	Select **Add a permission**. On the **Request API Permissions** page, select **Exchange** under **Supported legacy APIs**.
5.	To use delegated permissions, select **Delegated permissions**, and then select **EWS.AccessAsUser.All** under **EWS**. Click **Add permissions**.
6.	To use application permissions, select **Application permissions** and then select **full_access_as_app**. Click **Add permissions**.
7.	Select **Grant admin consent for org** and accept the consent dialog.
8.	Under **Manage**, choose **Certificates & Secrets**, and then create a new secret for your app. You will use the secret either in Business Central, in the **Client Secret** field on the **Marketing Setup** page, or store it in secure storage and provide it in an event subscriber.
9.	Choose **Overview**, and then find the **Application (client) ID** value. This is the client ID of your application. You must enter it either on the **Marketing Setup page**, in the **Client ID** field, or store it in secure storage and provide it in an event subscriber.
10.	In Business Central, set up email logging on the **Marketing Setup** page, or use the **Email Logging Assisted Setup** guide for assistance with the process.
    * Provide the email account of the user on behalf of whom the scheduled job will connect to Exchange and process emails. The user must have a valid license for Exchange.
    * Provide the URL for your Exchange Service. Typically, this is the domain that you specified in the user's email address.
    * Provide **Queue Folder Path** and **Storage Folder Path**.
11.	To start logging email, turn on the **Enabled** toggle.
12.	Sign in with your administrator account for Microsoft Entra ID (this account must have a valid license for Exchange and be an administrator in your Exchange). After you sign in you will be prompted to allow your registered application to sign in to Exchange on behalf of the organization. You must give consent to complete the setup.

   > [!NOTE]
   > If you are not prompted to sign in with your administrator account, it is probably because pop ups are blocked. To sign in, allow pop-ups from https://login.microsoftonline.com.

### Using Another Identity and Access Management Service
If you are not using Microsoft Entra ID to manage identities and access, you will need some help from a developer. If you prefer to store the app ID and secret in a different location, you can leave the Client ID and Client Secret fields blank and write an extension to fetch the ID and secret from the location. You can provide the secret at runtime by subscribing to the OnGetEmailLoggingClientId and OnGetEmailLoggingClientSecret events in codeunit 1641 "Setup Email Logging".


## See Also  
[Managing Interactions With Contacts](marketing-interactions.md)   
[Walkthrough: Logging Email Interactions in the Database](walkthrough-logging-email-interactions-in-the-database.md)   
