---
title: The VAT Group Extension | Microsoft Docs
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

# The VAT Group Extension
You can team up with one or more other businesses in your country to consolidate VAT reporting under a single registration number. This type of arrangement is known as a _VAT group_. You can engage with the group as a member or the group representative.

> [!NOTE]
> VAT reports contain customer data. That data will be deleted after 30 days.

## Forming a VAT Group
VAT group members and the group representative can use the **VAT Group Management Setup** assisted setup guide to define their engagement with the group, and create a connection between the group members' and the representative's [!INCLUDE[d365fin](includes/d365fin_md.md)]. The group members will use the connection to submit their VAT returns to the group representative

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
