---
title: The VAT Group Management Extension | Microsoft Docs
description: You can engage with other businesses to form a VAT group, and act as either a member or representative of the group when reporting VAT.
author: bholtorf
manager: annbe

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: VAT, value added tax, report
ms.date: 04/01/2020
ms.author: bholtorf

---

# The VAT Group Management Extension
You can team up with one or more other businesses in your country to consolidate VAT reporting under a single registration number. This type of arrangement is known as a _VAT group_. You can engage with the group as a member or the group representative.

> [!NOTE]
> VAT reports contain customer data. That data will be deleted after 30 days.

## Forming a VAT Group
VAT group members and the group representative can use the **VAT Group Management Setup** assisted setup guide to define their engagement with the group, and create a connection between the group members' and the representative's [!INCLUDE[d365fin](includes/d365fin_md.md)]. The group members will use the connection to submit their VAT returns to the group representative. The VAT Group representative will submit VAT on behalf of the entire group through a single VAT Return, subtmitted to authorities as it would normally be. 

## VAT Group constellations
All communication in VAT Group Mamanagement happens from VAT Group member towards the VAT Group representative. The VAT Group representative exposes an API that allows the VAT Group members to submit their VAT Returns directly to the VAT Group representative. 
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] supports inter-group VAT Return submissions for companies using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] either on premises or online in any combination. The setup of the communication will depend on the constellation. The following sections describes the technical setup needed for various group constellations.

The recommended order of setup across the group is the following:<br>
* Create the needed VAT Group member users in the VAT Group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)].
* Set up the VAT Group Management feature in the VAT Group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)] by starting the **Set up VAT Group Management** assisted setup. Skip the part with adding **Approved members**.
* Create the needed setup in Azure AD (see the section *VAT Group representative is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online*)
* Set up the VAT Group members so they can connect to and authenticate with the VAT Group representative.
* On the VAT Group representative, add VAT Group members in the **VAT Group Approved Members** list. A VAT Group member can only be added to this list once the member has completed the **Set up VAT Group Management** assisted setup, because a unique Group Member ID is needed in order for the VAT Group representative to identify submitting members. This ID is generated as part of the assisted setup.

> [!NOTE]
> In order for VAT Group members to connect to the VAT Group representative, they need a user with access to the VAT Group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. Create at least one user in the VAT Group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. For optimal security it is recommended to create a user for each VAT Group member. Make sure to distribute the credentials for these users securely to VAT Group members.

**VAT Group representative is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online**<br>
When the VAT Group representative is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online the VAT Group members will use Azure AD to authenticate to be able so submit VAT Returns to the VAT Group representative. If the VAT Group members are also using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online the VAT Group member will be able to authenticate using the designated user credentials and the endpoint information. See more details in the **VAT Group member - Setup** section.

If just one of the VAT Group members is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] on premises you need to set up an **App Registration** in Azure AD on the VAT Group representative tenant. This App Registration will enable authentication towards the [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online environment used by the VAT Group representative. Please see the following documentation on how to create an App Registration in Azure AD. [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)<br><br>
Make sure the following guidelines are followed when creating the App Registration in Azure AD:<br>
* On the **Authentication** section, add **Web** as a platform and use the following **Redirect URL**: https://businesscentral.dynamics.com/OAuthLanding.htm
*  On the **Authentication** section, in the option to select **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory - Multitenant)**
* On the **Certificates & secrets** section, create a new **client secret** and note the value. This will be needed by the VAT Group members when they setup the connection to the VAT Group representative. 
* On the **API permissions** section, make sure to add permissions to [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. Make sure to enable delegated access to **Financials.ReadWrite.All** and **user_impersonation**.
* On the **Overview** section, note the **Application (client) ID**. This will be needed by the VAT Group members when they setup the connection to the VAT Group representative. 

## VAT Group member - Setup
Setting up the VAT Group member to use VAT Group Management is done by starting the **Set up VAT Group Management** assisted setup.
* Start by defining this company's VAT Group role. Select **Member**. When done, choose **Next**.
* Copy the **Group Member ID** and inform the VAT Group representative, who needs it to add your company to the approved members of the group.
* Add the **API URL** of the VAT Group representative. You will need this information from the VAT Group representative. Usually this URL is in the form of **https://api.businesscentral.dynamics.com/v2.0/[ENVIRONMENTNAME]/api/v1.0** as for example **https://api.businesscentral.dynamics.com/v2.0/GBProduction/api/v1.0**. 
* Add the [!INCLUDE[d365fin](../../includes/d365fin_md.md)] company name of the VAT Group representative. For example **CRONUS UK Ltd.**
* Choose **Authentication Type**. Select **OAuth2**. WHen done, choose **Next**.
* In **Client ID** provided by the VAT Group representative.
* In **Client Secret provided by the VAT Group representative**
* In **OAuth 2.0 Authority Endpoint** enter **https://login.microsoftonline.com/common/oauth2**
* In **OAuth 2.0 Resource URL** enter **https://api.businesscentral.dynamics.com/**
* In **OAuth 2.0 Redirect URL** enter **https://businesscentral.dynamics.com/OAuthLanding.htm**. When done, choose **Next**.
* The VAT Group member will now try to authenticate agenst the VAT Group representative tenant and get a token for access. It will prompt the VAT Group member for the user credentials to use that was provided by the VAT Group representative.
* Choose the current VAT Report configuration. Normally this would be a configuration that is set up to report VAT to authorities in the given country. For example in the United Kingdom the VAT Report configuration would be set up to report VAT to the HMRC. The VAT Group Management feature will copy this setup but change the submission codeunit to one provided by Microsoft that supports submission to the VAT Group representative instead of the authorities. When done, choose **Next**.

 
(TO DO's IN THIS DOCS)
* Explain the VAT Group representative on prem scenario (complex, firewall, possibly Web Service Access Key etc)
* Creating approved group members
* Submitting VAT Returns to VAT Group representative
* Mention the need for proper setup (e.g. same  VAT Return Periods across all members)
* How group representative checks that submissions have been received
* Creating VAT Returns for the group


(PREVIOUS DOC TEXT - WILL COPY FROM THIS WHERE NEEDED)

Before using the guide to set up a VAT group, the group members and the representative must exchange the following information: 

* The group representative must create a user in the company that members will submit VAT reports to, and assign the **VAT Group API User** permission to the user. The group members will need the user name and credentials for this user when they join the group. We recommend that this user is used only for submitting VAT returns to the group representative, and is not associated with a person. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).
* The group representative must provide the web service access key. <!--where do they get the web service access key?-->
* The group members must complete the VAT Group Management assisted setup guide as a member to generate a group member ID. Afterward, the member ID is available on the VAT Report Setup page. Members must provide the group member ID to the group representative, will use the information to add the member to the **Approved Members** list.


### Choosing an Authentication Type
When a member joins a VAT group, they must choose an authentication method. The following authentication methods are available:

* **Web Services Access Key** - The user name and web service access key of the user that was set up for the group representative.
* **OAuth 2.0** - You must create an Azure AD app registration that has delegated permissions to Business Central. For more information, see [Setting up Azure Active Directory (AAD) based authentication](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps#AAD). This app can be created on a free Azure account. Each group member can create their own Azure AD app registration, or use a common one provided by the group representative. For Business Central on-premises, you must use HTTPS. For example, https://dell-paivan/nav_gb/OAuthLanding.htm. In the assisted setup guide, after you choose Next an authentication page will open and you must sign in as the user from the group representative and accept the permissions request. This allows the Azure AD app to make requests to the Bussiness Central API.
* **Windows** - This only works [!INCLUDE[d365fin](includes/d365fin_md.md)] on-premises on NSTs that have Windows authentication as the authentication type. If you choose this then the user signed in on the member instance must also be a user that can access the group representative company in [!INCLUDE[d365fin](includes/d365fin_md.md)].

### To use the assisted setup guide
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Report Setup**, and then choose the related link.
2. Complete the steps in the assisted setup guide. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 

> [!NOTE]
> The information you provide in the guide includes the codeunit to use when sending the VAT report. When your reach that step, choose codeunit **50100**.

### Set up VAT return periods
The group representative must define the period of time for which representatives will submit their VAT report. On the **VAT Report Setup** page, 

## Tasks for VAT Group Members
As a member of a VAT group, you must submit your VAT return to the group representative.

### To submit a VAT return to your group representative
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Returns**, and then choose the related link.
2. In the **Version** field, choose **VATGROUP**.
3. Choose **Process**, and then **Submit Lines**.
4. On the **VAT Report Requests** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Choose **OK**.
5. On the **VAT Returns** page, choose **Release**, and then **Submit**.

## To verify that the representative submitted your VAT report
You can verify that your group representative has submitted the VAT report to the tax authority. On the **Group VAT Returns** page, the **VAT Returns** column displays the status of the report.

### Leaving a VAT Group
If you no longer want to participate in a VAT group, you can exit the group by changing the VAT report configuration and version on the VAT Report Setup page to use the standard VAT reporting process instead. For more information, see [Set Up Value-Added Tax](finance-setup-vat.md).

## Tasks for the VAT Group Representative
As the group representative you receive, consolidate, and submit VAT amounts from group members to your tax authority.

### Inspect VAT submissions from group members
You can view the details about a VAT report that a member submitted. On the **VAT Return Periods** page, choose the submission that you are interested in, and then choose the **Group Member Submissions** field.

### Submit VAT to your tax authority
All members of the VAT group must submit their VAT returns to you before you can submit the consolidated information to your tax authority.

> [!TIP]
> After you submit the VAT return, members cannot update the VAT report they submitted to you. If you need to update the report, choose **Reopen**.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Group VAT Submissions**, and then choose the related link.

## See Also
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Set Up Value-Added Tax](finance-setup-vat.md)  
q
