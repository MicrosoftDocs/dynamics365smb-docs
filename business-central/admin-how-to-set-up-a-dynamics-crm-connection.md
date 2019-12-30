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
# Set Up a Connection to Dynamics 365 Sales
This topic describes how to set up a connection between [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)].
<br><br>  

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2085501]

## Before You Start
Before you create the connection, there are a few pieces of information to have ready:  

* A URL for your [!INCLUDE[crm_md](includes/crm_md.md)] app. A fast way to get the URL is to open [!INCLUDE[crm_md](includes/crm_md.md)], copy the URL, and then paste it in the **Dynamics 365 Sales URL** field in [!INCLUDE[d365fin](includes/d365fin_md.md)]. [!INCLUDE[d365fin](includes/d365fin_md.md)] will correct the formatting for you.  
* A user name and password of a user account that is used only for the integration.  
* The user name and password of the account that has administrator permissions.  

> [!Note]
> These steps describe the procedure for the online version of [!INCLUDE[d365fin](includes/d365fin_md.md)].

## Set Up, Test, and Enable a Connection to [!INCLUDE[crm_md](includes/crm_md.md)]  
For all authentication types other than Office 365 authentication, you set up your connection to Dynamics 365 Sales on the **Microsoft Dynamics 365 Sales Connection Setup** page. For Office 365 authentication, you can also use the **Set Up Dynamics 365 Sales Connection** assisted setup guide, which will help you provide the required information.

### To use an assisted setup guide
The **Set Up Dynamics 365 Sales Connection** assisted setup guide can help you set up the connection and specify whether to enable advanced features, such as coupling between records.

1. Choose **Setup and Extensions**, and then choose **Assisted Setup**.
2. Choose **Set Up Dynamics 365 Sales Connection** to start the assisted setup guide.
3. Fill in the fields as necessary.
4. Optionally, there are advanced settings that can enhance security and enable [!INCLUDE[crm_md](includes/crm_md.md)] additional capabilities, such as sales order processing and viewing inventory levels. The following table describes the advanced settings.  

|Field|Description|
|-----|-----|
|**Import Dynamics 365 Sales Solution**|Enable this to install and configure the integration solution in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [About the Business Central Integration Solution](admin-prepare-dynamics-365-for-sales-for-integration.md#about-the-business-central-integration-solution).|
|**Publish Item Availability Web Service**|Enable people who are using [!INCLUDE[crm_md](includes/crm_md.md)] to view the availability of items (products) in inventory in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This requires that the [!INCLUDE[d365fin](includes/d365fin_md.md)] user account with a web services access key. Assigning the key is a two-step process. On the user account in [!INCLUDE[d365fin](includes/d365fin_md.md)] you must choose the **Change Web Service Key** action. In the Set Up Dynamics 365 Sales Connection assisted setup guide, you must specify the Dynamics 365 Business Central OData web service URL, and provide [!INCLUDE[d365fin](includes/d365fin_md.md)] user credentials for accessing the service. For more information, see [OData Web Services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services).|
|**Dynamics 365 Business Central OData Web Service URL**|If you enable the Item Availability Web Service, the URL for the OData Web service is provided for you.|
|**Dynamics 365 Business Central OData Web Service Username**|The name of the [!INCLUDE[d365fin](includes/d365fin_md.md)] user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to retrieve information about item availability in [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web Service.|
|**Dynamics 365 Business Central OData Web Service Accesskey**|The access key for the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web Service. The key is assigned to the user chosen in the **Dynamics 365 Business Central OData Web Service Username** field. To get the key, choose the **Look up value** button next to the user name, choose the user, choose **Manage**, and then **Edit**. On the user card, choose **Actions**, **Authentication**, and then choose **Change Web Service Key**.|
|**Enable Sales Order Integration**|When people create sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] and fullfill orders in [!INCLUDE[d365fin](includes/d365fin_md.md)], this integrates the process in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration). This requires that you provide credentials for an administrator user account in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Handling Sales Order Data](marketing-integrate-dynamicscrm.md#handling-sales-order-data).|
|**Enable Dynamics 365 for Sales Connection**|Enable the connection to [!INCLUDE[crm_md](includes/crm_md.md)].|
|**Dynamics 365 SDK Version**|This is relevant only if you are integrating with an on-premises version of [!INCLUDE[crm_md](includes/crm_md.md)]. This is the Dynamics 365 software development kit (also referred to as Xrm) you use to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. The version must be compatible with the SDK version that is used by [!INCLUDE[crm_md](includes/crm_md.md)], and equal to or newer than the version used by [!INCLUDE[crm_md](includes/crm_md.md)].|

> [!Note]
> **Set Up Dynamics 365 Sales Connection** assisted setup guide automatically assigns **Integration Administrator** and **Integration User** security roles to the user account used for integration.

### To create or maintain the connection manually
The following procedure describes how to fill in the fields on the **Microsoft Dynamics 365 Sales Connection Setup** page manually. This is also the page where you manage settings for the integration.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft Dynamics 365 Connection Setup**, and then choose the related link.
2. Enter the following information for the connection from [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)].

|Field|Description|
|-----|-----|
|**Dynamics 365 Sales URL**|The URL for your instance of [!INCLUDE[crm_md](includes/crm_md.md)]. To get the URL, open [!INCLUDE[crm_md](includes/crm_md.md)], copy the URL from the address bar in your browser, and then paste the URL in the field. [!INCLUDE[d365fin](includes/d365fin_md.md)] will make sure that the format is correct.|
|**User Name** and **Password**|The credentials of the user account that is dedicated for the integration. For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).|
|**Enabled**|Start using the integration. If you do not enable the connection now, the connection settings will be saved but users will not be able to access [!INCLUDE[crm_md](includes/crm_md.md)] data from [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can return to this page and enable the connection later.  |
|**Dynamics 365 SDK Version**|If you are integrating with an on-premesis version of [!INCLUDE[crm_md](includes/crm_md.md)], this is the Dynamics 365 software development kit (also referred to as Xrm) you use to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. The version that you select must be compatible with the SDK version that is used by [!INCLUDE[crm_md](includes/crm_md.md)]. This version equal to or newer than the version used by [!INCLUDE[crm_md](includes/crm_md.md)].|

> [!Note]
> If you are connecting an on-premeses version of [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)] and you want to configure a connection to a [!INCLUDE[crm_md](includes/crm_md.md)] instance with a specific authentication type, fill in the fields on the **Authentication Type Details** FastTab. For more information, see [Use connection strings in XRM tooling to connect to Dynamics 365](https://go.microsoft.com/fwlink/?linkid=843055). This step is not required when connecting an online version of [!INCLUDE[d365fin](includes/d365fin_md.md)].

3. Enter the following information for the connection from [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)].

|Field|Description|
|-----|-----|
|**Dynamics 365 Business Central Web Client URL**|The URL of your [!INCLUDE[d365fin](includes/d365fin_md.md)] instance. This enables users in [!INCLUDE[crm_md](includes/crm_md.md)] to open corresponding records in [!INCLUDE[d365fin](includes/d365fin_md.md)] from records in [!INCLUDE[crm_md](includes/crm_md.md)], such as an account or product. The [!INCLUDE[d365fin](includes/d365fin_md.md)] records open in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Set this field to the URL of the [!INCLUDE[d365fin](includes/d365fin_md.md)] instance to use.<br /><br /> To reset the field to the default URL for the [!INCLUDE[d365fin](includes/d365fin_md.md)], choose **Reset Web Client URL** action.<br /><br /> This field is relevant only if the [!INCLUDE[d365fin](includes/d365fin_md.md)] Integration Solution is installed in [!INCLUDE[crm_md](includes/crm_md.md)].|
|**Item Availability Web Service Enabled**|Enable people who are using [!INCLUDE[crm_md](includes/crm_md.md)] to view the availability of items (products) in inventory in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you enable this, you must also provide a user name and an access key for the [!INCLUDE[crm_md](includes/crm_md.md)] to use to query OData Web Service for availablity of items (products). For more information, see [OData Web Services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services.md).|
|**Dynamics 365 Business Central OData Web Service URL**|If you enable the Item Availability Web Service, the URL for the OData Web service is provided for you.|
|**Dynamics 365 Business Central OData Web Service Username**|The name of the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web service.|
|**Dynamics 365 Business Central OData Web Service Accesskey**|The access key for the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web service. The key is assigned to the user chosen in the **Dynamics 365 Business Central OData Web Service Username** field. To get the key, choose the **Look up value** button next to the user name, choose the user, choose **Manage**, and then **Edit**. On the user card, choose **Actions**, **Authentication**, and then choose **Change Web Service Key**.|

4. Enter the following settings for [!INCLUDE[crm_md](includes/crm_md.md)].

|Field|Description|
|-----|-----|
|**Sales Order Integration is Enabled**|Enable users to submit sales orders and activated quotes in [!INCLUDE[crm_md](includes/crm_md.md)] and then view and process them in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This integrates the process in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration).|
|**Automatically Create Sales Orders**|Create a sales order in [!INCLUDE[d365fin](includes/d365fin_md.md)] when a user creates and submits one in [!INCLUDE[crm_md](includes/crm_md.md)].|
|**Automatically Process Sales Quotes**|Process a sales quote in [!INCLUDE[d365fin](includes/d365fin_md.md)] when a user creates and activates one in [!INCLUDE[crm_md](includes/crm_md.md)].|

5. Enter the following advanced settings.

|Field|Description|
|-----|-----|
|**[!INCLUDE[d365fin](includes/d365fin_md.md)] Users Must Map to Dynamics 365 Sales Users**|Specify whether [!INCLUDE[d365fin](includes/d365fin_md.md)] user accounts must have a matching user accounts in [!INCLUDE[crm_md](includes/crm_md.md)]. The **Office 365 Authentication Email** of the [!INCLUDE[d365fin](includes/d365fin_md.md)] user must be the same as the **Primary Email** of the [!INCLUDE[crm_md](includes/crm_md.md)] user.<br /><br /> If you set the value to **Yes**, [!INCLUDE[d365fin](includes/d365fin_md.md)] users who do not have a matching [!INCLUDE[crm_md](includes/crm_md.md)] user account will not have [!INCLUDE[d365fin](includes/d365fin_md.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data directly from [!INCLUDE[d365fin](includes/d365fin_md.md)] is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] user account.<br /><br /> If you set the value to **No**, all [!INCLUDE[d365fin](includes/d365fin_md.md)] users will have [!INCLUDE[crm_md](includes/crm_md.md)] integration capabilities in the user interface. Access to [!INCLUDE[crm_md](includes/crm_md.md)] data is done on behalf of the [!INCLUDE[crm_md](includes/crm_md.md)] connection (integration) user.|
|**Current Business Central User is Mapped to a Dynamics 365 Sales User**|Indicates whether your user account is mapped to an account in [!INCLUDE[crm_md](includes/crm_md.md)]|

6. To test the connection settings, choose **Test Connection**.  

    > [!NOTE]  
    >  If data encryption is not enabled in [!INCLUDE[d365fin](includes/d365fin_md.md)], you will be asked whether you want to enable it. To enable data encryption, choose **Yes** and provide the required information. Otherwise, choose **No**. You can enable data encryption later. For more information, see [Encrypting Data in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-encrypting-data) in Developer and IT-Pro help.  

7. If [!INCLUDE[crm_md](includes/crm_md.md)] synchronization is not already set up, you will be asked whether you want to use the default synchronization setup. Depending on whether you want to keep records aligned in [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)], choose **Yes** or **No**.

> [!Note]
> Connecting to Dynamics 365 Sales using the **Microsoft Dynamics 365 Sales Connection Setup** page may require that you assign the Integration Administrator and Integration User security roles to the account used for integration. For more information, see [Assign a security role to a user](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).


> [!Note]
> Connecting to Dynamics 365 Sales using **Microsoft Dynamics 365 Sales Connection Setup** page may require you to [assign  **Integration Administrator** and **Integration User** security roles](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user) to user account used for integration.


### To disconnect from [!INCLUDE[crm_md](includes/crm_md.md)]  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft Dynamics 365 Sales Connection Setup**, and then choose the related link.
2. On the **Microsoft Dynamics 365 Sales Connection Setup** page, clear the **Enabled** check box.  

<!--## Install the [!INCLUDE[d365fin](includes/d365fin_md.md) Integration Solution
[!INCLUDE[d365fin](includes/d365fin_md.md)] includes a solution that enables users to access coupled records, such as customers and items, from records in [!INCLUDE[crm_md](includes/crm_md.md)], such as accounts and products. The solution adds a link to the pages in [!INCLUDE[crm_md](includes/crm_md.md)] to open the coupled [!INCLUDE[d365fin](includes/d365fin_md.md)] record. The solution also displays information from [!INCLUDE[d365fin](includes/d365fin_md.md)]on certain entities in [!INCLUDE[crm_md](includes/crm_md.md)], such as accounts. Installing this solution is optional. <!--"Solution" sounds old school. Is it an app, or an add-in, or an extension?


1.  From [!INCLUDE[d365fin](includes/d365fin_md.md)] installation media \(DVD\), copy the DynamicsNAVIntegrationSolution.zip file to your computer.  

     The DynamicsNAVIntegrationSolution.zip file is located in the **CrmCustomization** folder. This file is the solution package.   

2.  In [!INCLUDE[crm_md](includes/crm_md.md)], import the DynamicsNAVIntegrationSolution.zip as a solution.  

     This step adds the **[!INCLUDE[d365fin](includes/d365fin_md.md) Connection** entity and **[!INCLUDE[d365fin](includes/d365fin_md.md) Account Statistics** entity in the system and additional items such as [!INCLUDE[d365fin](includes/d365fin_md.md)] integration security roles.  

     For more information about how to manage solutions in [!INCLUDE[crm_md](includes/crm_md.md)], [https://go.microsoft.com/fwlink/?LinkID=616519](https://go.microsoft.com/fwlink/?LinkID=616519).  

3.  Optional: Set up the **[!INCLUDE[d365fin](includes/d365fin_md.md) Connection** entity to display in the **Settings** area of [!INCLUDE[crm_md](includes/crm_md.md)].  

     This enables [!INCLUDE[crm_md](includes/crm_md.md)] users who are assigned the **[!INCLUDE[d365fin](includes/d365fin_md.md) Admin** role to modify the entity in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information about how to modify entities in [!INCLUDE[crm_md](includes/crm_md.md)], see [View or edit entity information](https://go.microsoft.com/fwlink/?LinkID=616521).  

4.  Assign the **[!INCLUDE[d365fin](includes/d365fin_md.md) Integration Administrator** role to the user account for the connection to [!INCLUDE[d365fin](includes/d365fin_md.md)].  

5.  Assign the **Business Central Integration User** role to all users who will use the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution.  

If you install the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution after you have set up the connection to [!INCLUDE[crm_md](includes/crm_md.md)] in [!INCLUDE[d365fin](includes/d365fin_md.md)], you must modify the connection setup to point to the URL.-->

<!--of the [!INCLUDE[nav_web_md](../developer/includes/nav_web_md.md)]. For more information, see [Set Up a Microsoft Dynamics 365 Sales Connection]() -->

<!--
# View Item Availability - Support Matrix
For most versions of [!INCLUDE[d365fin](includes/d365fin_md.md) and Dynamics 365 Sales, you can view availability figures for items across the integrated products. The following table shows which version combinations support viewing item availability.

| |Dynamics 365 Sales version|2015/Update 1/Online|2016/Update 1/Online|Dynamics 365 Sales|
|-|---------------------|---------------------|--------------------------|-----------------|
|**Dynamics NAV version**|
|**2016**||Not supported|Not supported|Not supported|
|**2017**||Not supported - Install from 2016|Supported|Supported|
|**Dynamics 365 for Financials**||Not supported - Install from 2016|Supported|Supported|


> [Note]
> You can obtain item availability support for combinations of Dynamics CRM 2015 and Business Central by running the DynamicsNAVIntegrationSolution.zip file on the Business Central product DVD.

For more information, see [System Requirements for Business Central](../deployment/system-requirement-business-central.md).

-->

## See Also  
[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  
