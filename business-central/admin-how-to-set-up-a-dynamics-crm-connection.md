---
    title: Connect to Dynamics 365 Sales | Microsoft Docs
    description: You can integrate with Dynamics 365 Sales.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2019
    ms.author: bholtorf


---
# Set Up a Connection to Common Data Service
This topic describes how to set up a connection between [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)].
<br><br>  

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2085501]

## Before You Start
Before you create the connection, there are a few pieces of information to have ready:  

* A URL for your [!INCLUDE[d365fin](includes/cds_long_md.md)] environment. <!--add bit aobout auto-discoverability-->.  
* A user name and password of a user account that is used only for the integration.  
* The user name and password of the account that has administrator permissions in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)].  

> [!Note]
> These steps describe the procedure for the online version of [!INCLUDE[d365fin](includes/d365fin_md.md)].

## Set Up, Test, and Enable a Connection to [!INCLUDE[d365fin](includes/cds_long_md.md)]  
For all authentication types other than Office 365 authentication, you set up your connection to [!INCLUDE[d365fin](includes/cds_long_md.md)] on the **CDS Connection Setup** page. For Office 365 authentication, we recommend that you use the **CDS Connection Setup** assisted setup guide, which makes it easy to provide the required information.

<!-- Need to point this procedure to the new guide, and copy this to the content for Sales-->
### To use an assisted setup guide 
The **CDS Connection Setup** assisted setup guide can help you set up the connection and specify advanced features, such as coupling between records.

1. Choose **Setup and Extensions**, and then choose **Assisted Setup**.
2. Choose **CDS Connection Setup** to start the assisted setup guide.
3. Fill in the fields as necessary.

> [!Note]
> The **Set Up CDS Connection** assisted setup guide automatically assigns **Integration Administrator** and **Integration User** security roles to the user account used for integration.-->

### To create or maintain the connection manually
The following procedure describes how to fill in the fields on the **CDS Connection Setup** page manually. This is also the page where you manage settings for the integration.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **CDS Connection Setup**, and then choose the related link.
2. Enter the following information for the connection from [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[d365fin](includes/cds_long_md.md)].

|Field|Description|
|-----|-----|
|**Environment URL**|If you own environments in [!INCLUDE[d365fin](includes/cds_long_md.md)], we will find those for you when you run the setup guide. If you want to connect to a different environment in another tenant, you can enter the administrator credentials for the environment and we will discover those. |
|**User Name** and **Password**|The credentials of the user account that is dedicated for the integration. For more information, see [Setting Up User Accounts for Integrating with [!INCLUDE[d365fin](includes/cds_long_md.md)]](admin-setting-up-integration-with-dynamics-sales.md).|
|**Enabled**|Start using the integration. If you do not enable the connection now, the connection settings will be saved but users will not be able to access [!INCLUDE[d365fin](includes/cds_long_md.md)] data from [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can return to this page and enable the connection later.  |

3. Enter the following advanced settings.

<!--Need to verify the details in this table-->

|Field|Description|
|-----|-----|
|**[!INCLUDE[d365fin](includes/d365fin_md.md)] Users Must Map to CDS Users**|If you are using the Person ownership model, specify whether [!INCLUDE[d365fin](includes/d365fin_md.md)] user accounts must have a matching user accounts in [!INCLUDE[d365fin](includes/cds_long_md.md)]. The **Office 365 Authentication Email** of the [!INCLUDE[d365fin](includes/d365fin_md.md)] user must be the same as the **Primary Email** of the [!INCLUDE[crm_md](includes/crm_md.md)] user.<br /><br /> If you set the value to **Yes**, [!INCLUDE[d365fin](includes/d365fin_md.md)] users who do not have a matching [!INCLUDE[crm_md](includes/crm_md.md)] user account will not have [!INCLUDE[d365fin](includes/d365fin_md.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data directly from [!INCLUDE[d365fin](includes/d365fin_md.md)] is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] user account.<br /><br /> If you set the value to **No**, all [!INCLUDE[d365fin](includes/d365fin_md.md)] users will have [!INCLUDE[crm_md](includes/crm_md.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] connection (integration) user.|
|**Current Business Central Salesperson is Mapped to a User**|Indicates whether your user account is mapped to an account in [!INCLUDE[crm_md](includes/crm_md.md)] <!--double check the name of this field-->|

4. To test the connection settings, choose **Test Connection**.  

    > [!NOTE]  
    >  If data encryption is not enabled in [!INCLUDE[d365fin](includes/d365fin_md.md)], you will be asked whether you want to enable it. To enable data encryption, choose **Yes** and provide the required information. Otherwise, choose **No**. You can enable data encryption later. For more information, see [Encrypting Data in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-encrypting-data) in Developer and IT-Pro help.  

7. If [!INCLUDE[d365fin](includes/cds_long_md.md)] synchronization is not already set up, you will be asked whether you want to use the default synchronization setup. Depending on whether you want to keep records aligned in [!INCLUDE[d365fin](includes/cds_long_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)], choose **Yes** or **No**.

> [!Note]
> Connecting to [!INCLUDE[d365fin](includes/cds_long_md.md)] using the **CDS Connection Setup** page may require that you assign the Integration Administrator and Integration User security roles to the account used for integration. For more information, see [Assign a security role to a user](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).


> [!Note]
> Connecting to Dynamics 365 Sales using **Microsoft Dynamics 365 Sales Connection Setup** page may require you to [assign  **Integration Administrator** and **Integration User** security roles](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user) to user account used for integration.


### To disconnect from [!INCLUDE[d365fin](includes/cds_long_md.md)]  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **CDS Connection Setup**, and then choose the related link.
2. On the **CDS Connection Setup** page, clear the **Enabled** check box.  

## View Item Availability - Support Matrix
For most versions of [!INCLUDE[d365fin](includes/d365fin_md.md) and Dynamics 365 Sales, you can view availability figures for items across the integrated products. For more information, see [System Requirements for Business Central](../deployment/system-requirement-business-central.md).

## See Also  
[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  
