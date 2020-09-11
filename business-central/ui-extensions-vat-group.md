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

<!--
> [!NOTE]
> VAT reports contain customer data. That data will be deleted after 30 days.
-->
## Forming a VAT Group
VAT group members and the group representative can use the **VAT Group Management Setup** assisted setup guide to define their engagement with the group, and create a connection between their [!INCLUDE[d365fin](includes/d365fin_md.md)] tenants. The group members will use the connection to submit their VAT returns to the group representative. The representative will submit VAT to tax authorities on behalf of the group using a single VAT return. 

## VAT Group Constellations
Communications happen from group members toward the representative. The group representative exposes an API that allows the members to submit their VAT returns directly to the VAT Group representative. 
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] supports inter-group VAT return submissions for companies using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] on-premises or online, and in any combination. The setup of the communication will depend on the constellation. The following sections describe how to set up various group constellations.

The recommended order of setup across the group is the following:<br>

1. Create the VAT group member users in the VAT group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)].
2. Set up the VAT Group Management feature in the VAT group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)] by starting the **Set up VAT Group Management** assisted setup. In the guide, skip the step for adding **Approved members**.
3. Create the setup in Azure AD. For more information, see [The VAT Group representative is using Business Central online](ui-extensions-vat-group.md#the-vat-group-representative-is-using-business-ventral-online).
4. Set up the VAT group members so they can connect and authenticate to the VAT group representative.
5. Add VAT group members on the **VAT Group Approved Members** page in the group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The VAT group member must first complete the **Set Up VAT Group Management** assisted setup guide to receive a unique group member ID. The member must provide the ID to the VAT group representative so they can add the member to the group and identify their VAT return submissions.

> [!NOTE]
> In order for VAT group members to connect to the VAT group representative, they need a user with access to the VAT group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The VAT group representative must create at least one user for this, however, for security reasons we recommended that you create a user for each VAT group member. Make sure to distribute the credentials for these users securely to VAT group members.

### The VAT group representative is using Business Central online
When the VAT group representative is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online, the VAT group members will use Azure AD to authenticate when they submit VAT returns to the VAT group representative. If the VAT group members are also using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online, the VAT group member can authenticate using the designated user credentials and the endpoint information. For more information, see [VAT Group Member Setup](ui-extensions-vat-group.md#vat-group-member-setup).

If a VAT group member is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] on-premises, you must set up an app registration in Azure AD on the VAT group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)] tenant. The app registration will enable the VAT group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)] online to authenticate the group member. For more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)<br><br>

When you create the app registration in Azure AD, you must specify the following.

* In the **Authentication** section, add **Web** as a platform, and use the following **Redirect URL**: https://businesscentral.dynamics.com/OAuthLanding.htm.
* In the **Authentication** section, in the option to select **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory - Multitenant)**.
* In the **Certificates & secrets** section, create a new client secret and note the value. The VAT group members will need the secret when they set up the connection to the group representative.
* In the **API permissions** section, add permissions to [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. Make sure to enable delegated access to **Financials.ReadWrite.All** and **user_impersonation**.
* In the **Overview** section, note the **Application (client) ID**. The VAT group members will need the ID when they set up the connection to the group representative. 

## VAT Group Member Setup
Set up the VAT group member by starting the **Set up VAT Group Management** assisted setup guide. 

> [!NOTE]
> Before you get started, contact the VAT group representative for the following information about their [!INCLUDE[d365fin](../../includes/d365fin_md.md)]:
>
> * The API URL
> * The name of their company 
> * Client ID
> * Client secret
> * Sign in credentials for the dedicated user 

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Group**, and then choose the related link.
2. To define the company's VAT group role, choose **Member**, and then choose **Next**.
3. Copy the **Group Member ID** and then share it with the VAT group representative so they can add your company as an approved members of the group.
4. Add the **API URL** from the VAT group representative. Typically, the URL is formatted as follows, **https://api.businesscentral.dynamics.com/v2.0/[ENVIRONMENTNAME]/api/v1.0**. For example, **https://api.businesscentral.dynamics.com/v2.0/GBProduction/api/v1.0**. 
5. Add the [!INCLUDE[d365fin](../../includes/d365fin_md.md)] company name of the VAT Group representative. For example **CRONUS UK Ltd.**
6. Choose **Authentication Type**, choose **OAuth2**, and then choose **Next**.
7. In the **Client ID** field, enter the ID provided by the VAT group representative.
8. In the **Client Secret provided by the VAT Group representative** field, enter the secret provided by the VAT group representative.
9. In the **OAuth 2.0 Authority Endpoint** field, enter **https://login.microsoftonline.com/common/oauth2**.
10. In the **OAuth 2.0 Resource URL** field, enter **https://api.businesscentral.dynamics.com/**.
11. In the **OAuth 2.0 Redirect URL** field, enter **https://businesscentral.dynamics.com/OAuthLanding.htm**. 
12. When done, choose **Next**, and then enter the user credentials provided by the VAT group representative.
13. Choose the VAT report configuration that you use to report VAT to authorities in your country. For example, in the United Kingdom the VAT report configuration would be set up to report VAT to the HMRC. The VAT Group Management extension will copy this setup, but replace the submission codeunit with one that supports submission to the VAT group representative instead of the authorities. The codeunit is provided by Microsoft. When done, choose **Next**.

 
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
