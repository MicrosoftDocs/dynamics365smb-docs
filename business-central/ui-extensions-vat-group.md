---
title: The VAT Group Management extension for the United Kingdom
description: You can engage with other businesses to form a VAT group where all members report VAT in a single return.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: VAT, value added tax, report
ms.search.form: 4700, 4701, 4703, 4704, 4705, 4706, 4707, 4708, 4709, 
ms.date: 06/03/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# The VAT Group Management extension for the United Kingdom

You can connect one or more businesses in the United Kingdom to combine value-added tax (VAT) reporting under a single registration number. This type of arrangement is known as a *VAT group*. You can engage with the group as a member or as the group representative.

## Forming a VAT group

VAT group members and the group representative can use the **Set Up VAT Group Management** assisted setup guide to both define their engagement with the group and create a connection between their [!INCLUDE[prod_short](includes/prod_short.md)] tenants. The group members use this connection to submit their VAT returns to the group representative. The group representative then uses a single VAT return to submit the group's VAT to tax authorities.

[!INCLUDE[prod_short](includes/prod_short.md)] supports intra-group VAT return submissions for companies using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises or online, in any combination, which influences the communication setup between businesses. This article describes various group setups.

### License requirements

Participants in the group must be licensed to use [!INCLUDE[prod_short](includes/prod_short.md)]. You can't use guest accounts in VAT groups.

* To calculate and submit VAT returns, a user must be a full [!INCLUDE[prod_short](includes/prod_short.md)] user.
* To sign in and do basic tasks, such as create accounts, you need a [!INCLUDE[prod_long](includes/prod_long.md)] Team Member license.

## Set up a VAT group

The following is the recommended order of steps an administrator uses to set up a VAT group:

1. Create the setup in [Microsoft Entra ID setup for group members](#microsoft-entra-id-setup-for-group-members).
2. Share the technical information VAT group members and the group representative need to connect their [!INCLUDE[prod_short](includes/prod_short.md)] tenants. Usually, the group representative has this information, such as the [API URL](#group-api-setup) and the name of the VAT group representative's environment the VAT group members submit their VAT data to.
3. Create users that VAT group members use to authenticate when they connect to the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)]. The users must have full user licenses for [!INCLUDE[prod_short](includes/prod_short.md)].
4. Run the **Set Up VAT Group Management** assisted setup guide to connect the VAT group members.

   The VAT group representative must supply certain information to group members to complete their setup. (Learn more in the [Set up VAT group members](#set-up-vat-group-members) section below.) Make a note of the **Group Member ID** for each VAT group member. The group representative needs these IDs to add the companies to the VAT group.
5. Set up the VAT group management extension in the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)] using the **Set Up VAT Group Management** assisted setup guide.

> [!NOTE]
> To connect to the VAT group representative, group members must have a user account that can access the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)]. The VAT group representative must create at least one user for this. However, for security reasons we recommended that they create a user for each VAT group member, which can be a system user account that is not related to an actual person. Make sure to distribute the user credentials to VAT group members in a secure way.

### Microsoft Entra ID setup for group members

When the VAT group representative is using [!INCLUDE[prod_short](includes/prod_short.md)] online or on-premises, VAT group members must use Microsoft Entra ID to authenticate users when they submit VAT returns to the VAT group representative. For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, members must configure single sign-on. Learn more at [Configure Microsoft Entra authentication with WS-Federation](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-active-directory?tabs=singletenant%2Cadmintool).

If the VAT group members are also using [!INCLUDE[prod_short](includes/prod_short.md)] online, the member can authenticate with the designated user credentials and the sign-in information provided by the group representative. Learn more in the [Set up VAT group members](#set-up-vat-group-members) section below.

VAT group members who have [!INCLUDE[prod_short](includes/prod_short.md)] on-premises must set up an app registration in Microsoft Entra ID for the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)] tenant. The app registration enables the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)] online to authenticate the group member. Learn more at [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).

When the VAT group member's administrator creates the app registration in Microsoft Entra ID, they must specify the following information.

* In the **Authentication** section, add **Web** as a platform, and use the following **Redirect URL**: `https://businesscentral.dynamics.com/OAuthLanding.htm`.
* In the **Authentication** section, in the option to select **Supported account types**, select **Accounts in any organizational directory (Any Microsoft Entra directory - Multitenant)**.
* In the **Certificates & secrets** section, create a new client secret and note the value. The VAT group members need the secret when they set up the connection to the group representative.
* In the **API permissions** section, add permissions to [!INCLUDE[prod_short](includes/prod_short.md)]. Enable delegated access to **Financials.ReadWrite.All** and **user_impersonation**.
* In the **Overview** section, note the **Application (client) ID**. The VAT group members need the ID when they set up the connection to the group representative.

### Group API setup

The VAT group representative creates and supplies an API to group members. The members use this API to connect to the representative's [!INCLUDE[prod_short](includes/prod_short.md)] tenant and submit VAT returns. VAT group members often use [!INCLUDE[prod_short](includes/prod_short.md)] in separate Microsoft Entra tenants. For that reason, setup is needed to connect the VAT group member and the representative's [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> This setup requires credentials for an administrator account that has a full user license for [!INCLUDE[prod_short](includes/prod_short.md)].

1. In the Business Central admin center for the representative's tenant, choose the **Environments** tab.
1. Choose the representative's environment.
1. In the **Details** section, copy the **URL**.
1. Open Notepad, and paste the URL. Replace `https://businesscentral.dynamics.com` with `https://api.businesscentral.dynamics.com/v2.0`.

## Set up VAT group members

VAT group members connect to the representative by calling a web service on the VAT group representative's tenant. The caller must be authenticated using OAuth2. When the VAT group management extension is set up, members are asked to authenticate to the VAT group representative, during which an access token is generated and saved. This access token is used when submitting VAT returns to the VAT group representative.

> [!IMPORTANT]
> The member companies in the VAT group do not need to connect to HMRC because they report through the group's representative.

Before VAT group members start their setup (listed below), they need to contact the VAT group representative for the following information about their [!INCLUDE[prod_short](includes/prod_short.md)] tenant:

* The API URL
* The name of their company
* Sign in credentials for the dedicated user

1. In the top right corner, choose the **Settings** ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, then choose the **Assisted setup** action.
2. Choose the **Set Up VAT Group Management** action.
3. In the **VAT Group Role** field, choose **Member** then **Next**.
4. Copy the value of the **Group Member ID** field, and then share it with the VAT group representative so they can add your company as an approved member of the group.
5. In the **Group Representative Product Version** field, specify the version of [!INCLUDE[prod_short](includes/prod_short.md)] the representative is using.
6. In the **API URL** field, enter the API URL provided by the VAT group representative. Typically, the URL is formatted as follows: `https://api.businesscentral.dynamics.com/v2.0/[TENANT-ID]/[ENVIRONMENTNAME]`. For example, `https://api.businesscentral.dynamics.com/v2.0/aaaabbbb-0000-cccc-1111-dddd2222eeee/UKRepresentative`.
7. In the **Group Representative Company** field, enter the company name of the VAT group representative, such as, **CRONUS UK Ltd**.
8. In the **Authentication Type** field, choose **OAuth2**. If the VAT group representative is using [!INCLUDE[prod_short](includes/prod_short.md)] online, enable the **Group Representative Uses Business Central Online** toggle, and then choose **Next**.

   Then, follow the steps in either the [VAT Group Representative uses Business Central online](ui-extensions-vat-group.md#vat-group-representative-uses-business-central-online) or [VAT Group Representative uses Business Central on-premises](ui-extensions-vat-group.md#vat-group-representative-uses-business-central-on-premises) section below.

### VAT group representative uses Business Central online

1. Enter the user credentials provided by the VAT group representative, and add the required permissions to generate the access token.
2. Choose the VAT report configuration you use to submit VAT returns to the UK tax authorities. 

After you complete the setup, [!INCLUDE[prod_short](includes/prod_short.md)] will create a new configuration based on this choice that enables you to submit VAT returns to the VAT group representative.

### VAT group representative uses Business Central on-premises

1. Enter the user credentials provided by the VAT group representative and choose **Next**.
2. In the **Client ID** field, specify the client ID from the app registration in [Microsoft Entra ID setup for group members](#microsoft-entra-id-setup-for-group-members).
3. In the **Client Secret** field, specify the client secret from the app registration in Microsoft Entra ID.
4. In the **OAuth 2.0 Authority Endpoint** field, enter `https://login.microsoftonline.com/common/oauth2`.
5. In the **OAuth 2.0 Resource URL** field, enter `https://api.businesscentral.dynamics.com/`.
6. In the **OAuth 2.0 Redirect URL** field, enter `https://businesscentral.dynamics.com/OAuthLanding.htm`.
7. When you've specified the various fields, choose **Next**, and then confirm the authentication connection to generate the access token.
8. Choose the VAT report configuration you use to submit VAT returns to the UK tax authorities.

## Set up the VAT group representative

> [!NOTE]
> For on-premises, [!INCLUDE[prod_short](includes/prod_short.md)] supports only a single tenant instance of the group representative.

> [!IMPORTANT]
> The representative company must enable the **HMRC VAT Setup** service connection on the **Service Connections** page. Representatives must also download VAT return periods from HMRC.

1. In the top right corner, choose the **Settings** icon ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then choose the **Assisted setup** action.
2. Choose the **Set Up VAT Group Management** action.
3. In the **VAT Group Role** field, choose **Representative** to act as the VAT group representative, then choose **Next**.
4. In the **Group Settlement Account** field, specify the settlement account used for the group member VAT tax amounts. This account should have **Assets** as the **Account Category**.
5. In the **VAT Settlement Account** field, specify the account you use for VAT settlements. This account should have **Liabilities** as the **Account Category**.
6. In the **VAT Due Box No.** field, specify the box that represents the total VAT amount due from a VAT group submission.
7. In the **Group Settlement General Journal Template** field, specify the general journal template used to create the document with which the group representative posts the group VAT to the settlement account.
8. The **Approved Members** field shows the number of group members set up to submit VAT returns to the group representative. To add new members, choose the number to open the **VAT Group Approved Members** page and add the following information:
    1. In the **Group Member ID** field, enter an identifier for the group member, as displayed during the group member setup (learn more in the [VAT group member setup](#set-up-vat-group-members) section above).
    2. In the **Group Member Name** field, specify the name of the group member.
    3. In the **Company** field, specify the company from which the group member submits VAT returns in [!INCLUDE[prod_short](includes/prod_short.md)], such as, **CRONUS UK Ltd**.
    4. Specify contact details for the company.

## Use the VAT group management features

VAT group members use the standard processes to prepare VAT returns. The only difference is members must choose the **VATGROUP** report version in the **VAT Return** page to submit the VAT return to the VAT group representative rather than the authorities. Learn more at [About the VAT Return report](finance-how-report-vat.md#vatreturn).

> [!NOTE]
> VAT group members can correct submitted VAT returns as long as the group representative has not released the VAT return for the group. To make a correction, the VAT group member must create a new VAT return for the VAT return period and submit it to the VAT group representative. On the VAT group representative's side, the member's latest VAT return replaces the previous and is included on the **VAT Returns** page.

The following sections describe the tasks that VAT group representatives must do to file the group VAT return.

### Review VAT member submissions

The **VAT Group Submissions** page lists the VAT returns that members have submitted. The page serves as a draft location for the submissions until the VAT group representative includes them in a VAT return for the group. The representative can open the submissions to review the individual boxes containing the amount reported by each VAT group member.

> [!TIP]
> On the **VAT Return Periods** page, the **Group Member Submissions** field shows how many returns members have submitted. To ensure that this number is up to date, choose the **Get VAT Returns** action.

### Create a group VAT return

To report VAT for the group, on the **VAT Returns** page, create a VAT return for your company only. Afterward, include the most recent VAT submissions from VAT group members by choosing the **Include Group VAT** action.  

When the group representative has submitted the group's VAT return to the authorities, the representative then normally runs the **Calculate and Post VAT Settlement** action. This action closes open VAT Entries and transfers amounts to the VAT settlement account. Currently, this action doesn't take the group submissions into account. Only the VAT entries of the VAT group representative company are posted. The VAT group member submission amounts must be posted using the **Post Group VAT Settlement** action.

> [!IMPORTANT]
> The VAT group functionality is only supported in those markets where [!INCLUDE[prod_short](includes/prod_short.md)] uses a VAT framework that consists of VAT returns and VAT return periods. You cannot use VAT groups in markets with other implementations of local VAT reporting, such as Austria, Germany, Italy, Spain, and Switzerland.

## Issue with enabling Multifactor Authentication (MFA)

If you get an error message related to authorization during the renewal of the **OAuth2 Token** on the **VAT Report Setup** page after you enable MFA, complete the following steps.  

1. Sign in to the **Azure Portal** as an Authentication Administrator.  
2. Go to the **Microsoft Entra ID**.   
3. Browse to **Users**, and then select the user you want to perform an action.  
4. Select the **Authentication methods** and at the top of the page, select **Require re-register multifactor authentication**. 
5. Go back to Dynamics 365 Business Central and select to renew the token from the **VAT Report Setup**.  

This should be a onetime setup after you enable multifactor authentication for the user selected in **VAT Report Setup**.  

## Related information

[United Kingdom Local Functionality in the British Version](LocalFunctionality/unitedkingdom/united-kingdom-local-functionality.md)  
[Making Tax Digital in the United Kingdom](LocalFunctionality/UnitedKingdom/making-tax-digital-submit-vat-return.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Set Up Value-Added Tax](finance-setup-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Consolidating Financial Data from Multiple Companies](finance-consolidated-company-reporting.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
