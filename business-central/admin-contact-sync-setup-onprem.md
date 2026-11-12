---
title: Set Up Legacy Outlook Contact Sync On-Premises
description: Configure OAuth authentication for legacy Outlook contact synchronization in Business Central on-premises version 27 and earlier.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-op
ms.topic: how-to
ms.date: 11/12/2026
ai-usage: ai-assisted
ms.custom: bap-template
---

# Set up legacy Outlook contact sync on-premises

> **APPLIES TO:**  [!INCLUDE[prod_short](includes/prod_short.md)] 2025 release wave 2 (v27) and earlier. For later versions, this setup isn't needed. Learn more in [Save business contacts to Microsoft Outlook](save-business-contacts-to-outlook.md).

> [!IMPORTANT]
> This legacy integration uses Exchange Web Services (EWS). Exchange Online starts disabling EWS in October 2026 and fully disables it in April 2027. Configuring OAuth doesn't prevent the EWS retirement from affecting contact synchronization. Learn more in [Deprecation of Exchange Web Services in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/deprecation-of-ews-exchange-online). For Business Central version 28 and later, use [Save business contacts to Microsoft Outlook](save-business-contacts-to-outlook.md).

In this article, you learn how to set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to synchronize contacts in [!INCLUDE[prod_short](includes/prod_short.md)] with contacts in Outlook. Learn more in [Synchronize contacts in Business Central with contacts in Microsoft Outlook](admin-synchronize-outlook-contacts.md).

## Authentication requirements for legacy contact sync

Contact synchronization requires using the OAuth 2.0 protocol for authentication with Exchange Online. Previously, basic authentication was also supported, but it's been deprecated and is no longer supported with Exchange Online. Learn more in [Deprecation of Basic authentication in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/deprecation-of-basic-authentication-exchange-online). The following steps configure OAuth authentication for the legacy integration.

## Prerequisites for legacy contact sync

- Exchange Online, either a standalone version or through Microsoft 365 plan  
- Access to the Microsoft Entra tenant used by Exchange Online
- [!INCLUDE[prod_short](includes/prod_short.md)] users have a Microsoft 365 or Exchange Online email account, which is assigned to their accounts in [!INCLUDE[prod_short](includes/prod_short.md)]. You can check this setting in the **Microsoft 365 Authentication** section of user profile in the **Users** list. 

## Set up contact sync

Complete the following steps to set up contact sync. If you're running [!INCLUDE[prod_short](includes/prod_short.md)] Spring 2019 (v.14), you'll have to do an extra step that either modifies application code or sets up a connection to Power BI.

1. <a name="registerapp"></a>Register an app for Exchange Online API in your Microsoft Entra tenant.

   In this step, you add a registered app in the Microsoft Entra tenant of your Microsoft 365 or Exchange Online plan. Like other Azure services that work with Business Central, Exchange Online requires a registered app in Microsoft Entra ID. The registered app provides authentication and authorization services between Business Central and Exchange Online.

   Learn more in [Register an application in Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-microsoft-entra-id) in the developer and IT pro help. As you go through the instructions, remember the following points:

   - If you've already registered an application as part of an integration with another Microsoft product, such as Power BI, then reuse that registered app. In this case, you'll just have to set up the app with the Office 365 Exchange Online permissions described in the next bullet.

   - Configure the registered app with the following delegated permissions to the Office 365 Exchange Online API:

     - Contacts.ReadWrite
     - EWS.AccessAsUser.All

1. For [!INCLUDE[prod_short](includes/prod_short.md)] version 14, do one of the following tasks:

   - Modify page 6700 by changing `FALSE` to `TRUE` in the following line of code in the `OnOpenPage` trigger:

     ```
     PasswordRequired := AzureADMgt.GetAccessToken(AzureADMgt.GetO365Resource,AzureADMgt.GetO365ResourceName,TRUE) = '';
     ```

   - Create a new page with the following code in the `OnOpenPage` trigger:

     ```
     PasswordRequired := AzureADMgt.GetAccessToken(AzureADMgt.GetO365Resource,AzureADMgt.GetO365ResourceName,TRUE) = '';
     ```

   - Set up Power BI by following the instructions at [Set up Business Central on-premises for Power BI integration](across-working-with-business-central-in-powerbi.md).

   After the solution you choose is in place, ask users to either run the new/modified page or [connect to Power BI](across-working-with-powerbi.md#connect). They'll only need to do this step once.

## Related information

[Synchronize Contacts in Business Central with Contacts in Microsoft Outlook](admin-synchronize-outlook-contacts.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
