---
title: Set up contact sync with Outlook for Business Central on-premises
description: Learn how to configure a Business Central on-premises environment to synchronize contacts in Business Central and Outlook.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-op
ms.topic: how-to
ms.date: 09/28/2023
ms.custom: bap-template
---

# Set up contact sync with Outlook for Business Central on-premises

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

In this article, you learn how to set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to synchronize contacts in [!INCLUDE[prod_short](includes/prod_short.md)] with contacts in Outlook. For more information the feature, go to [Synchronize Contacts in Business Central with Contacts in Microsoft Outlook](admin-synchronize-outlook-contacts.md).

## Introduction

Contact synchronization requires using the OAuth 2.0 protocol for authentication with Exchange Online. Previously, basic authentication was also supported, but it's been deprecated and no longer supported with Exchange Online. You can read more about the deprecation at [Deprecation of Basic authentication in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/deprecation-of-basic-authentication-exchange-online). This change means that contact synchronization in Business Central may have stopped working on your on-premises environment. This article will explain how to get it working again.

## Prerequisites

- Exchange Online, either a standalone version or through Microsoft 365 plan  
- Access to the Microsoft Entra tenant used by Exchange Online
- [!INCLUDE[prod_short](includes/prod_short.md)] users have a Microsoft 365 or Exchange Online email account, which is assigned to their accounts in [!INCLUDE[prod_short](includes/prod_short.md)]. You can check this setting in the **Microsoft 365 Authentication** section of user profile in the **Users** list. 

## Set up contact sync

Complete the following steps to set up contact sync. If you're running [!INCLUDE[prod_short](includes/prod_short.md)] Spring 2019 (v.14), you'll have to do an extra step that either modifies application code or sets up a connection to Power BI.

1. <a name="registerapp"></a>Register an app for Exchange Online API in your Microsoft Entra tenant.

   In this step, you add a registered app in the Microsoft Entra tenant of your Microsoft 365 or Exchange Online plan. Like other Azure services that work with Business Central, Exchange Online requires a registered app in Microsoft Entra ID. The registered app provides authentication and authorization services between Business Central and Exchange Online.

   Follow the detailed instructions in the developer and IT pro help at [Register an application in Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory). As you go through the instructions, remember the following points:

   - If you've already registered an application as part of an integration with another Microsoft product, such as Power BI, then reuse that registered app. In this case, you'll just have to set up the app with the Office 365 Exchange Online permissions described in the next bullet.

   - Configure the registered app with the following delegated permissions to the Office 365 Exchange Online API:

     - Contacts.ReadWrite
     - EWS.AccessAsUser.All

2. For [!INCLUDE[prod_short](includes/prod_short.md)] version 14, do one of the following tasks:

   - Modify page 6700 by changing `FALSE` to `TRUE` in the following line of code in the `OnPageOpen` trigger:

     ```
     PasswordRequired := AzureADMgt.GetAccessToken(AzureADMgt.GetO365Resource,AzureADMgt.GetO365ResourceName,TRUE) = '';
     ```

   - Create new page with the following code on the OnPageOpen trigger:

     ```
     PasswordRequired := AzureADMgt.GetAccessToken(AzureADMgt.GetO365Resource,AzureADMgt.GetO365ResourceName,TRUE) = '';
     ```

   - Set up Power BI by following the instructions at [Set up Business Central on-premises for Power BI integration](across-working-with-business-central-in-powerbi.md).

   After the solution you choose is in place, ask users to either run the new/modified page or [connect to Power BI](across-working-with-powerbi.md#connect). They'll only need to do this step once.

## Next steps

[Synchronize Contacts in Business Central with Contacts in Microsoft Outlook](admin-synchronize-outlook-contacts.md)  
