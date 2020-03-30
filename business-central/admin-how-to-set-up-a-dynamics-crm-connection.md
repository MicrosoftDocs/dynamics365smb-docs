---
    title: Connect to Dynamics 365 Sales | Microsoft Docs
    description: You can integrate other apps with Business Central through Common Data Service.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf


---
# Connect to Common Data Service
This topic describes how to set up a connection between [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)]. Typically, businesses create the connection to integrate and synchronize data with another Dynamics 365 business app, such as [!INCLUDE[crm_md](includes/crm_md.md)].  

## Before You Start
There are a few pieces of information to have ready before you create the connection:  

* The URL for the [!INCLUDE[d365fin](includes/cds_long_md.md)] environment that you want to connect to. If you use the **CDS Connection Setup** assisted setup guide to create the connection we will discover your environments, but you can also enter the URL of another environment in your tenant.  
* A user name and password of a user account that is used only for the integration. This account is referred to as the "integration user" account. 
* The user name and password of an account that has administrator permissions in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)].  

> [!Note]
> These steps describe the procedure for the online version of [!INCLUDE[d365fin](includes/d365fin_md.md)].

## Set Up a Connection to [!INCLUDE[d365fin](includes/cds_long_md.md)]  
For all authentication types other than Office 365 authentication, you set up your connection to [!INCLUDE[d365fin](includes/cds_long_md.md)] on the **CDS Connection Setup** page. For Office 365 authentication, we recommend that you use the **CDS Connection Setup** assisted setup guide. The guide makes it easier to set up the connection and specify advanced features, such as coupling between records.  

### To use the CDS Connection Setup assisted setup guide 
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link.
2. Choose **Set up CDS Base Integration connection** to start the assisted setup guide.
3. Fill in the fields as necessary.

> [!Note]
> The **CDS Connection Setup** assisted setup guide automatically assigns **Integration Administrator** and **Integration User** security roles to the user account used for integration, and sets the access mode for the account to **non-interactive**.

### To create or maintain the connection manually
The following procedure describes how to set up the connection manually on the **CDS Connection Setup** page manually. This is also the page where you manage settings for the integration.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **CDS Connection Setup**, and then choose the related link.
2. Enter the following information for the connection from [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[d365fin](includes/cds_long_md.md)].

|Field|Description|
|-----|-----|
|**Environment URL**|If you own environments in [!INCLUDE[d365fin](includes/cds_long_md.md)], we will find those for you when you run the setup guide. If you want to connect to a different environment in another tenant, you can enter the administrator credentials for the environment and we will discover those. |
|**User Name** and **Password**|The credentials of the user account that is dedicated for the integration. For more information, see [Setting Up User Accounts for Integrating with [!INCLUDE[d365fin](includes/cds_long_md.md)]](admin-setting-up-integration-with-dynamics-sales.md).|
|**Enabled**|Start using the integration. If you do not enable the connection now, the connection settings will be saved but users will not be able to access [!INCLUDE[d365fin](includes/cds_long_md.md)] data from [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can return to this page and enable the connection later.  |

3. In the **Ownership Model** field, choose whether you want a team entity in [!INCLUDE[d365fin](includes/cds_long_md.md)] to own new records, or one or more specific users. If you choose **Person**, you must specify each user. If you choose **Team**, the default business unit BCI_Company will display in the **Coupled Business Unit** field.

<!--Need to verify the details in this table, are these specific to Sales maybe?
Enter the following advanced settings.

|Field|Description|
|-----|-----|
|**[!INCLUDE[d365fin](includes/d365fin_md.md)] Users Must Map to CDS Users**|If you are using the Person ownership model, specify whether [!INCLUDE[d365fin](includes/d365fin_md.md)] user accounts must have a matching user accounts in [!INCLUDE[d365fin](includes/cds_long_md.md)]. The **Office 365 Authentication Email** of the [!INCLUDE[d365fin](includes/d365fin_md.md)] user must be the same as the **Primary Email** of the [!INCLUDE[crm_md](includes/crm_md.md)] user.<br /><br /> If you set the value to **Yes**, [!INCLUDE[d365fin](includes/d365fin_md.md)] users who do not have a matching [!INCLUDE[crm_md](includes/crm_md.md)] user account will not have [!INCLUDE[d365fin](includes/d365fin_md.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data directly from [!INCLUDE[d365fin](includes/d365fin_md.md)] is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] user account.<br /><br /> If you set the value to **No**, all [!INCLUDE[d365fin](includes/d365fin_md.md)] users will have [!INCLUDE[crm_md](includes/crm_md.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] connection (integration) user.|
|**Current Business Central Salesperson is Mapped to a User**|Indicates whether your user account is mapped to an account in [!INCLUDE[crm_md](includes/crm_md.md)] <!--double check the name of this field|-->

4. To test the connection settings, choose **Connection**, and then **Test Connection**.  

    > [!NOTE]  
    >  If data encryption is not enabled in [!INCLUDE[d365fin](includes/d365fin_md.md)], you will be asked whether you want to enable it. To enable data encryption, choose **Yes** and provide the required information. Otherwise, choose **No**. You can enable data encryption later. For more information, see [Encrypting Data in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-encrypting-data.md) in Developer and IT-Pro help.  

5. If [!INCLUDE[d365fin](includes/cds_long_md.md)] synchronization is not already set up, you will be asked whether you want to use the default synchronization setup. Depending on whether you want to keep records aligned in [!INCLUDE[d365fin](includes/cds_long_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)], choose **Yes** or **No**.

> [!Note]
> Connecting to [!INCLUDE[d365fin](includes/cds_long_md.md)] using the **CDS Connection Setup** page may require that you assign the Integration Administrator and Integration User security roles to the account used for integration in Dynamics 365 Sales. For more information, see [Assign a security role to a user](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user.md).

### To disconnect from [!INCLUDE[d365fin](includes/cds_long_md.md)]  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **CDS Connection Setup**, and then choose the related link.
2. On the **CDS Connection Setup** page, turn off the **Enabled** toggle.  

## See Also  
[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  
