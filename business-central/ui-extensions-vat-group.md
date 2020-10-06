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

## Forming a VAT Group
VAT group members and the group representative can use the **VAT Group Management Setup** assisted setup guide to define their engagement with the group, and create a connection between their [!INCLUDE[d365fin](includes/d365fin_md.md)] tenants. The group members will use the connection to submit their VAT returns to the group representative. The representative will submit VAT to tax authorities on behalf of the group using a single VAT return. 

## VAT Group Constellations
Communications happen from group members toward the representative. The group representative exposes an API that allows the members to submit their VAT returns directly to the VAT Group representative. 
[!INCLUDE[d365fin](includes/d365fin_md.md)] supports inter-group VAT return submissions for companies using [!INCLUDE[d365fin](includes/d365fin_md.md)] on-premises or online, and in any combination. The setup of the communication will depend on the constellation. The following sections describe how to set up various group constellations.

The recommended order of setup across the group is the following:<br>

1. Create the setup in Azure AD. For more information, see [The VAT Group representative is using Business Central online](ui-extensions-vat-group.md#the-vat-group-representative-is-using-business-ventral-online).
2. Prepare the technical information needed by VAT group members. Usually, this is information the VAT Group representative has, like for example name of the VAT Group representative environment to which the VAT Group members will submit VAT.
3. Create users in the VAT Group representative [!INCLUDE[d365fin](../../includes/d365fin_md.md)] that VAT Group members use to authenticate and connect.
4. Run the VAT Group Management assisted setup guide for the connecting VAT Group members. Here you will need information from the VAT Group representative. See **VAT Group Member Setup**. Make sure to note down the **Group Member ID** from each VAT Group member. You will need them in the next step.
5. Set up the VAT Group Management feature in the VAT group representative's [!INCLUDE[d365fin](includes/d365fin_md.md)] by starting the **Set up VAT Group Management** assisted setup. 

> [!NOTE]
> In order for VAT group members to connect to the VAT group representative, they need a user with access to the VAT group representative's [!INCLUDE[d365fin](includes/d365fin_md.md)]. The VAT group representative must create at least one user for this, however, for security reasons we recommended that you create a user for each VAT group member. Make sure to distribute the credentials for these users securely to VAT group members.

## Understanding the VAT Group Management setup
The VAT Group representative exposes an API to which VAT Group members can connect and submit VAT Returns from the VAT Group member companies. VAT Group members will often use [!INCLUDE[d365fin](../../includes/d365fin_md.md)] in separate Azure AD tenants. Therefore, more setup is needed to make a connection between the VAT Group member's [!INCLUDE[d365fin](../../includes/d365fin_md.md)] and the VAT Group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. 
Connections from the VAT Group member is made by calling a web service on the VAT Group representative tenant. The caller needs to be authenticated and currently [!INCLUDE[d365fin](../../includes/d365fin_md.md)] supports authentication using OAuth. For a limited time authentication is also supported using a Web Service Access Key (See [Deprecated Features in 2021 release wave 1](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#deprecated-features-in-2021-release-wave-1)). When the VAT Group Management feature is set up, you will be asked to authenticate towards the VAT Group representative to get and save an access token. This access token will be used when submitting VAT Returns to the VAT Group representative. 
Authentication is handled by Azure AD and therefore setup needs to be made in the VAT Group representative's Azure AD to allow connections to be made from outside the realm of the VAT Group representative. An Azure AD App Registration needs to be configured with access to the VAT Group representative's [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. This is also the case if the VAT Group representative is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] on premises, as Azure AD is still required for authentication. In addition, you will need to configure Single Sign-On in scenarios where the VAT Group representative is using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] on premises.

## Prerequisites - setup external to [!INCLUDE[d365fin](../../includes/d365fin_md.md)] 
When the VAT group representative is using [!INCLUDE[d365fin](includes/d365fin_md.md)] online or on premises, the VAT group members will use Azure AD to authenticate when they submit VAT returns to the VAT group representative. If the VAT group members are also using [!INCLUDE[d365fin](includes/d365fin_md.md)] online, the VAT group member can authenticate using the designated user credentials and the endpoint information. For more information, see [VAT Group Member Setup](ui-extensions-vat-group.md#vat-group-member-setup).

If a VAT group member is using [!INCLUDE[d365fin](includes/d365fin_md.md)] on-premises, you must set up an app registration in Azure Active Directory for the VAT group representative's [!INCLUDE[d365fin](includes/d365fin_md.md)] tenant. The app registration will enable the VAT group representative's [!INCLUDE[d365fin](includes/d365fin_md.md)] online to authenticate the group member. For more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)<br><br>

When you create the app registration in Azure AD, you must specify the following.

* In the **Authentication** section, add **Web** as a platform, and use the following **Redirect URL**: https://businesscentral.dynamics.com/OAuthLanding.htm.
* In the **Authentication** section, in the option to select **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory - Multitenant)**.
* In the **Certificates & secrets** section, create a new client secret and note the value. The VAT group members will need the secret when they set up the connection to the group representative.
* In the **API permissions** section, add permissions to [!INCLUDE[d365fin](includes/d365fin_md.md)]. Make sure to enable delegated access to **Financials.ReadWrite.All** and **user_impersonation**.
* In the **Overview** section, note the **Application (client) ID**. The VAT group members will need the ID when they set up the connection to the group representative. 

## VAT Group Member Setup
Set up the VAT group member by starting the **Set up VAT Group Management** assisted setup guide. 

> [!NOTE]
> Before you get started, contact the VAT group representative for the following information about their [!INCLUDE[d365fin](includes/d365fin_md.md)]:
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
5. Add the [!INCLUDE[d365fin](includes/d365fin_md.md)] company name of the VAT Group representative. For example **CRONUS UK Ltd.**
6. Choose **Authentication Type**, choose **OAuth2**, and then choose **Next**.
7. In the **Client ID** field, enter the ID provided by the VAT group representative.
8. In the **Client Secret provided by the VAT Group representative** field, enter the secret provided by the VAT group representative.
9. In the **OAuth 2.0 Authority Endpoint** field, enter **https://login.microsoftonline.com/common/oauth2**.
10. In the **OAuth 2.0 Resource URL** field, enter **https://api.businesscentral.dynamics.com/**.
11. In the **OAuth 2.0 Redirect URL** field, enter **https://businesscentral.dynamics.com/OAuthLanding.htm**. 
12. When done, choose **Next**, and then enter the user credentials provided by the VAT group representative.
13. Choose the VAT report configuration that you use to report VAT to authorities in your country. For example, in the United Kingdom the VAT report configuration would be set up to report VAT to the HMRC. The VAT Group Management extension will copy this setup, but replace the submission codeunit with one that supports submission to the VAT group representative instead of the authorities. The codeunit is provided by Microsoft. When done, choose **Next**.

## Using the VAT Group Management features
On the VAT Group members there is almost no changes to the business processes after setting up the VAT Group Management extension. Preparing VAT returns happens in much the same way as before. The only change is that the group member must be sure to select the **VATGROUP** Report Version when createing the VAT Return. This will ensure that submission of the VAT Return will go to the VAT Group representative instead of the authorities.

For the VAT Group representative several things have been added to [!INCLUDE[d365fin](../../includes/d365fin_md.md)]:

### VAT Group Submissions
In the page VAT Group Submissions you will see all the submissions from the VAT Group members. Consider this list the draft location for the submissions until they are included in a Group VAT Return on the VAT Group representative. In this list you can drill down into the submissions and see the reported VAT for the individual boxes reported from the given VAT Group member.

### Creating a Group VAT Return
When you want to create a VAT Return to report VAT on behalf of the entire group, you first create a normal VAT Return on the **VAT Returns** page. Go through the standard process of creating the VAT Return. When done, you will have created a VAT Return for the VAT Group representative company only. When you are ready to include the VAT submissions submitted by VAT Group members, select **Process** and **Include Group VAT**. This will bring the latest submission from each VAT Group member into the VAT Return for the group. 

> [!NOTE]
> If a VAT Group member needs to do a correction to the submitted VAT Return, this can be done as long as the Group VAT Return on the VAT Group representative is not yet released. To do this, the VAT Group member must create a new complete VAT Return for the desired VAT Return Period and submit it to the VAT Group representative. On the VAT Group representative side, only the latest submitted VAT Return will be considered and it will automatically get included when opening the **VAT Returns** page. 

## See Also
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Set Up Value-Added Tax](finance-setup-vat.md)
