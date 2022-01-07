---
    title: Connect to Microsoft Dataverse (contains video)
    description: Set up a connection between Business Central and Dataverse. Businesses typically create the connection to integrate data with another Dynamics 365 business app.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/30/2021
    ms.author: bholtorf


---
# Connect to Microsoft Dataverse

[!INCLUDE[prod_short](includes/cc_data_platform_banner.md)]

This topic describes how to set up a connection between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. Typically, businesses create the connection to integrate and synchronize data with another Dynamics 365 business app, such as [!INCLUDE[crm_md](includes/crm_md.md)].  

## Before You Start

There are a few pieces of information to have ready before you create the connection:  

* The URL for the [!INCLUDE[cds_long_md](includes/cds_long_md.md)] environment that you want to connect to. If you use the **Dataverse Connection Setup** assisted setup guide to create the connection we will discover your environments, but you can also enter the URL of another environment in your tenant.  
* The user name and password of an account that has administrator permissions in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[cds_long_md](includes/cds_long_md.md)].  
* If you have an on-premises [!INCLUDE[prod_short](includes/prod_short.md)] 2020 release wave 1, version 16.5, read the [Some Known Issues](/dynamics365/business-central/dev-itpro/upgrade/known-issues#wrong-net-assemblies-for-external-connected-services) article. You'll have to complete the described workaround before you can create your connection to [!INCLUDE[cds_long_md](includes/cds_long_md.md)].
* The local currency for the company in [!INCLUDE[prod_short](includes/prod_short.md)] must be the same as the base transaction currency in [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. After a base transaction is set in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] it cannot be changed. For more information, see [Transaction Currency (currency) entity](/powerapps/developer/data-platform/transaction-currency-currency-entity). This means that all [!INCLUDE[prod_short](includes/prod_short.md)] companies you connect to a [!INCLUDE[cds_long_md](includes/cds_long_md.md)] organization must use the same currency.

> [!IMPORTANT]
> Your [!INCLUDE[cds_long_md](includes/cds_long_md.md)] environment must not be in Administration mode. Administration mode will cause the connection to fail because the integration user account for the connection does not have administrator permissions. For more information, see [Administration mode](/power-platform/admin/admin-mode).

> [!Note]
> These steps describe the procedure for [!INCLUDE[prod_short](includes/prod_short.md)] online.
> If you are using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises and are not using Azure Active Directory account to connect to [!INCLUDE [cds_long_md](includes/cds_long_md.md)], you must also specify a user name and password of a user account for the integration. This account is referred to as the "integration user" account. If you are using an Azure Active Directory account the integration user account is not required or displayed. The integration user will be set up automatically and does not require a license.

## Set Up a Connection to [!INCLUDE[cds_long_md](includes/cds_long_md.md)]

For all authentication types other than Microsoft 365 authentication, you set up your connection to [!INCLUDE[cds_long_md](includes/cds_long_md.md)] on the **Dataverse Connection Setup** page. For Microsoft 365 authentication, we recommend that you use the **Dataverse Connection Setup** assisted setup guide. The guide makes it easier to set up the connection and specify advanced features, such as the ownership model and initial synchronization.  

> [!IMPORTANT]
> During the setup of the connection to [!INCLUDE[cds_long_md](includes/cds_long_md.md)], the administrator will be asked to give following permissions to a registered Azure application named [!INCLUDE[prod_short](includes/prod_short.md)] Integration to [!INCLUDE[cds_long_md](includes/cds_long_md.md)]:
>
> * **Access [!INCLUDE[cds_long_md](includes/cds_long_md.md)] as you** permission is needed so [!INCLUDE[prod_short](includes/prod_short.md)] can, on behalf of administrator, automatically create non-licensed non-interactive [!INCLUDE[prod_short](includes/prod_short.md)] Integration application user, assign security roles to this user and to deploy [!INCLUDE[prod_short](includes/prod_short.md)] Integration Solution to [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. This permission is used only once during set up of connection to [!INCLUDE[cds_long_md](includes/cds_long_md.md)].  
> * **Have full access to Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)]** permission is needed so automatically created [!INCLUDE[prod_short](includes/prod_short.md)] Integration application user can access [!INCLUDE[prod_short](includes/prod_short.md)] data that will be synchronized.  
> * **Sign in and read your profile** permission is needed to verify user logging in actually has System Administrator security role assigned in [!INCLUDE[cds_long_md](includes/cds_long_md.md)].  
>
> By giving consent on behalf of organization, the administrator is entitling the registered Azure application called [!INCLUDE[prod_short](includes/prod_short.md)] Integration to [!INCLUDE[cds_long_md](includes/cds_long_md.md)] to synchronize data using automatically created [!INCLUDE[prod_short](includes/prod_short.md)] Integration application user's credentials.

### To use the Dataverse Connection Setup assisted setup guide
The Dataverse Connection Setup guide can make it easier to connect the applications, and can even help you run an initial synchronization. If you choose to run initial synchronization, [!INCLUDE[prod_short](includes/prod_short.md)] will review the data in both applications and provide recommendations for how to approach initial synchronization. The following table describes the recommendations.

|Recommendation  |Description  |
|---------|---------|
|**Full synchronization**|Data exists only in [!INCLUDE[prod_short](includes/prod_short.md)], or only in [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. The recommendation is to synchronize all data from the service that has it to the other service.|
|**No synchronization**|Data exists in both applications, and running full synchronization would duplicate the data. The recommendation is to couple records.|
|**Dependency not satisfied**|Data exists in both applications, but the row or table cannot be synchronized because it depends on a row or table that has the No synchronization recommendation. For example, if customers cannot be synchronized, then data for contacts that depends on the customer data cannot be synchronized either.|

> [!IMPORTANT]
> Typically, you only use full synchronization when you're integrating the applications for the first time, and only one application contains data. Full synchronization can be useful in a demonstration environment because it automatically creates and couples records in each application, which makes it faster to start working with synchronized data. However, you should only run full synchronization if you want one row in [!INCLUDE[prod_short](includes/prod_short.md)] for each row in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] for the table mappings. Otherwise, the result can be duplicate records.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link.
2. Choose **Set up a connection to Microsoft Dataverse** to start the assisted setup guide.
3. Fill in the fields as necessary.

> [!NOTE]
> If you are not prompted to sign in with your administrator account, it is probably because pop-ups are blocked. To sign in, allow pop-ups from `https://login.microsoftonline.com`.

### To create or maintain the connection manually

The following procedure describes how to set up the connection manually on the **Dataverse Connection Setup** page. This is also the page where you manage settings for the integration.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dataverse Connection Setup**, and then choose the related link.
2. Enter the following information for the connection from [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[cds_long_md](includes/cds_long_md.md)].

    |Field|Description|
    |-----|-----|
    |**Environment URL**|If you own environments in [!INCLUDE[cds_long_md](includes/cds_long_md.md)], we will find those for you when you run the setup guide. If you want to connect to a different environment in another tenant, you can enter the administrator credentials for the environment and we will discover those. |
    |**Enabled**|Start using the integration. If you do not enable the connection now, the connection settings will be saved but users will not be able to access [!INCLUDE[cds_long_md](includes/cds_long_md.md)] data from [!INCLUDE[prod_short](includes/prod_short.md)]. You can return to this page and enable the connection later.  |

3. In the **Ownership Model** field, choose whether you want a team table in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] to own new records, or one or more specific users. If you choose **Person**, you must specify each user. If you choose **Team**, the default business unit will display in the **Coupled Business Unit** field.

    <!--Need to verify the details in this table, are these specific to Sales maybe?  IK: No they are not and no longer relevant 
    Enter the following advanced settings.-->

    <!-- |Field|Description|
    |-----|-----|
    |**[!INCLUDE[prod_short](includes/prod_short.md)] Users Must Map to CDS Users**|If you are using the Person ownership model, specify whether [!INCLUDE[prod_short](includes/prod_short.md)] user accounts must have a matching user accounts in [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. The **Microsoft 365 Authentication Email** of the [!INCLUDE[prod_short](includes/prod_short.md)] user must be the same as the **Primary Email** of the [!INCLUDE[crm_md](includes/crm_md.md)] user.<br /><br /> If you set the value to **Yes**, [!INCLUDE[prod_short](includes/prod_short.md)] users who do not have a matching [!INCLUDE[crm_md](includes/crm_md.md)] user account will not have [!INCLUDE[prod_short](includes/prod_short.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data directly from [!INCLUDE[prod_short](includes/prod_short.md)] is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] user account.<br /><br /> If you set the value to **No**, all [!INCLUDE[prod_short](includes/prod_short.md)] users will have [!INCLUDE[crm_md](includes/crm_md.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] connection (integration) user.|
    |**Current Business Central Salesperson is Mapped to a User**|Indicates whether your user account is mapped to an account in [!INCLUDE[crm_md](includes/crm_md.md)] double check the name of this field|-->
4. To test the connection settings, choose **Connection**, and then **Test Connection**.  

    > [!NOTE]  
    > If data encryption is not enabled in [!INCLUDE[prod_short](includes/prod_short.md)], you will be asked whether you want to enable it. To enable data encryption, choose **Yes** and provide the required information. Otherwise, choose **No**. You can enable data encryption later. For more information, see [Encrypting Data in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-encrypting-data) in the developer and administration help.  
5. If [!INCLUDE[cds_long_md](includes/cds_long_md.md)] synchronization is not already set up, you will be asked whether you want to use the default synchronization setup. Depending on whether you want to keep records aligned in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)], choose **Yes** or **No**.

<!--
## Show Me the Process

The following video shows the steps to connect [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. <br>
  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ArlP]

-->

## Customize the Match-Based Coupling

Starting in 2021 release wave 2, you can couple records in [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [cds_long_md](includes/cds_long_md.md)] based on matching criteria defined by the administrator.  

The algorithm for matching records can be started from the following places in [!INCLUDE [prod_short](includes/prod_short.md)]:

* List pages that show records that are synchronized with [!INCLUDE [cds_long_md](includes/cds_long_md.md)], such as the Customers and Items pages.  

    Select multiple records, and then choose the **Related** action, choose **Dataverse**, choose **Coupling**, and then choose **Match-Based Coupling**.

    When the match-based coupling process is started from a master data list, a coupling job will be scheduled right after you have selected the coupling criteria.  
* The **Dataverse Full Synch. Review** page.  

    When the full synchronization process detects that you have uncoupled records both in [!INCLUDE [prod_short](includes/prod_short.md)] and in [!INCLUDE [cds_long_md](includes/cds_long_md.md)], a **Select Coupling Criteria** link appears for the relevant integration table.  

    You can start the **Run Full Synchronization** process from the **Dataverse Connection Setup** and **Dynamics 365 Connection Setup** pages, and it can be initiated as a step in the **Set up a connection to Dataverse** assisted setup guide when you choose to complete setup and run full synchronization at the end.  

    When the match-based coupling process is started from **Dataverse Full Synch. Review** page, a coupling job will be scheduled right after you completed the setup.  
* The **Integration Table Mappings** list.  

    Select a mapping, choose the **Coupling** action, and then choose **Match-Based Coupling**.

    When the match-based coupling process is started from an integration table mapping, a coupling job will run for all uncoupled records in that mapping. If it was run for a set of selected records from the list, it will run only for the selected uncoupled records.

In all three cases, the **Select Coupling Criteria** page opens so that you can define the relevant coupling criteria. In this page, customize the coupling with the following tasks:

* Choose which fields to match [!INCLUDE [prod_short](includes/prod_short.md)] records and [!INCLUDE [cds_long_md](includes/cds_long_md.md)] entities by, and also choose whether the match on that field will be case-sensitive or not.  

* Specify whether to run a synchronization after coupling records, and, if the record uses bidirectional mapping, also choose what happens if conflicts are listed in the **Resolve Update Conflicts** page.  

* Prioritize the order in which records are searched by specifying a *match priority* for the relevant mapping fields. The match priorities make the algorithm search for a match in a number of iterations as defined by the **Match Priority** field values in ascending order. A blank value in the **Match Priority** field is interpreted as priority 0, so fields with this value fill be considered first.  

* Specify whether to create a new entity instance in [!INCLUDE [cds_long_md](includes/cds_long_md.md)] in case no unique uncoupled match can be found by using the match criteria. To activate this capability, choose the **Create New if Unable to Find a Match** action.  

### View the results of the coupling job

To view the results of the coupling job, open the **Integration Table Mappings** page, select the relevant mapping, choose the **Coupling** action, and then choose the **Integration Coupling Job Log** action.  

If there are any records that were not coupled, you can drill down on the value in the Failed column, which will open a list of errors that specifies why the records failed to couple.  

Failed coupling often happens in the following cases:

* No matching criteria was defined

    In this case, run the match-based coupling again, but remember to define coupling criteria.

* No match was found for a number of records, based on the chosen matching fields

    In this case, repeat the coupling with some other matching fields.

* Multiple matches were found for a number of records, based on the chosen matching fields  

    In this case, repeat the coupling with some other matching fields.

* A single match was found, but the matching record is already coupled to another record in [!INCLUDE [prod_short](includes/prod_short.md)]  

    In this case, repeat the coupling with some other matching fields, or investigate why that [!INCLUDE [cds_long_md](includes/cds_long_md.md)] entity is coupled to that other record in [!INCLUDE [prod_short](includes/prod_short.md)].

> [!TIP]
> To help you get an overview over the progress of the coupling, the **Coupled to Dataverse** field shows whether a specific record is coupled to a [!INCLUDE [cds_long_md](includes/cds_long_md.md)] entity or not. You can filter the list of records that are being synchronized with [!INCLUDE [cds_long_md](includes/cds_long_md.md)] by this field.

## Upgrade Connections from Business Central Online to Use Certificate-Based Authentication
> [!NOTE]
> This section is relevant only for [!INCLUDE[prod_short](includes/prod_short.md)] online tenants that are hosted by Microsoft. Online tenants hosted by ISVs, and on-premises installations, are not affected.

In April, 2022, [!INCLUDE[cds_long_md](includes/cds_long_md.md)] is deprecating the Office365 authentication type (username/password). For more information, see [Deprecation of Office365 authentication type](/power-platform/important-changes-coming#deprecation-of-office365-authentication-type-and-organizationserviceproxy-class-for-connecting-to-dataverse). Additionally, in March, 2022, [!INCLUDE[prod_short](includes/prod_short.md)] is deprecating the use of client secret based service-to-service authentication for online tenants, and will require the use of certificate-based service-to-service authentication for connections to [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. [!INCLUDE[prod_short](includes/prod_short.md)] online tenants that are hosted by ISVs, and on-premises installations, can continue to use client secret authentication to connect to [!INCLUDE[cds_long_md](includes/cds_long_md.md)].

To avoid disrupting integrations, _you must upgrade_ the connection to use certificate-based authentication. Although the change is scheduled for March, 2022, we strongly recommend that you upgrade as soon as possible. The following steps describe how to upgrade to certificate-based authentication. 

### To upgrade your Business Central online connection to use certificate-based authentication

> [!NOTE]
> Certificate-based authentication is available in Business Central 2021 release wave 1 and later. If you are using an earlier version, you must schedule an update to Business Central 2021 release wave 1 before March, 2022. For more information, see [Scheduling updates](/dynamics365/business-central/dev-itpro/administration/update-rollout-timeline#scheduling-updates). If you experience issues, contact your partner or support.

1. In the [Business Central administration center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center), verify that you are using Business Central 2021 release wave 1 or later (version 18 or later).
2. Depending on whether you integrate with Dynamics 365 Sales, do one of the following:
   * If you do, open the **Microsoft Dynamics 365 Connection Setup** page.
   * If you don't, open the **Dataverse Connection Setup** page.
3. Choose **Connection**, and then **Use Certificate Authentication** to upgrade the connection to use certificate based authentication.
4. Sign in with administrator credentials for Dataverse. Sign in should take less than a minute.

> [!NOTE]
> You must repeat these steps in each [!INCLUDE[prod_short](includes/prod_short.md)] environment, including both production and sandbox environments, and in each company where you have a connection to [!INCLUDE[cds_long_md](includes/cds_long_md.md)].

## Connecting On-Premises Versions

To connect [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to [!INCLUDE[cds_long_md](includes/cds_long_md.md)], you must specify some information on the **Dataverse Connection Setup** page.

If you want to connect using an Azure Active Directory (Azure AD) account, you must register an application in Azure AD, and provide the application ID, key vault secret, and the redirect URL to use. The redirect URL is pre-populated and should work for most installations. You must set up your installation to use HTTPS. For more information, see [Configuring SSL to Secure the Business Central Web Client Connection](/dynamics365/business-central/dev-itpro/deployment/configure-ssl-web-client-connection). If you are setting up your server to have a different home page, you can always change the URL. The client secret will be saved as an encrypted string in your database. 

### Prerequisites

Dataverse must use one of the following authentication types:

* Office365 (legacy)

  > [!IMPORTANT]
  > Effective April 2022, Office365 (legacy) will no longer be supported. For more information, see [Important changes (deprecations) coming in Power Apps, Power Automate and customer engagement apps](/power-platform/important-changes-coming#deprecation-of-office365-authentication-type-and-organizationserviceproxy-class-for-connecting-to-dataverse).
* Office365 (modern, OAuth2 client secret based)
* OAuth

### To register an application in Azure AD for connecting from Business Central to Dataverse

The following steps assume that you use Azure AD to manage identities and access. For more information about registering an application in Azure AD, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app). 

1. In the Azure Portal, under **Manage** on the Navigation Pane, choose **Authentication**.  
2. Under **Redirect URLs**, add the redirect URL that is suggested on the **Dataverse Connection Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)].
3. Under **Manage**, choose **API permissions**.
4. Under **Configured permissions**, choose **Add a permission**, and then add delegated permissions on the **Microsoft APIs** tab as follows:
    * For Business Central, add the **Financials.ReadWrite.All** permissions.
    * For Dynamics CRM, add the **user_impersonation** permissions.  

    > [!NOTE]
    > The name of the Dynamics CRM API might change.

5. Under **Manage**, choose **Certificates & Secrets**, and then create a new secret for your app. You will use the secret either in [!INCLUDE[prod_short](includes/prod_short.md)], in the **Client Secret** field on the **Dataverse Connection Setup** page, or store in a secure storage and provide it in an event subscriber as described earlier in this topic.
6. Choose **Overview**, and then find the **Application (client) ID** value. This is the Client ID of your application. You must enter it either on the **Dataverse Connection Setup** page in the **Client ID** field, or store it in a secure storage and provide it in an event subscriber.
7. In [!INCLUDE[prod_short](includes/prod_short.md)], on the **Dataverse Connection Setup** page, in the **Environment URL** field, enter the URL for your [!INCLUDE[cds_long_md](includes/cds_long_md.md)] environment.
8. To enable the connection to [!INCLUDE[cds_long_md](includes/cds_long_md.md)], turn on the **Enabled** toggle.
9. Sign in with your administrator account for Azure Active Directory (this account must have a valid license for [!INCLUDE[cds_long_md](includes/cds_long_md.md)] and be an administrator in your [!INCLUDE[cds_long_md](includes/cds_long_md.md)] environment). After you sign in you will be prompted to allow your registered application to sign in to [!INCLUDE[cds_long_md](includes/cds_long_md.md)] on behalf of the organization. You must give consent to complete the setup.

   > [!NOTE]
   > If you are not prompted to sign in with your administrator account, it is probably because pop ups are blocked. To sign in, allow pop-ups from `https://login.microsoftonline.com`.

### To disconnect from [!INCLUDE[cds_long_md](includes/cds_long_md.md)]

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dataverse Connection Setup**, and then choose the related link.
2. On the **Dataverse Connection Setup** page, turn off the **Enabled** toggle.  

## See Also

[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
