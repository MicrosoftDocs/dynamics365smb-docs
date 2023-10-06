---
title: Printer Setup and Management Overview
description: Learn what the different printer opportunities in Business Central  
author: jswymer 
ms.author: jswymer 
ms.reviewer: jswymer 
ms.service: dynamics365-business-central
ms.topic: overview 
ms.date: 09/28/2023
ms.custom: bap-template 
---

# Printer Setup and Management Overview

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Printing documents and reports from [!INCLUDE[prod_short](includes/prod_short.md)] is an important task for business users. You'll typically want to send print jobs directly to one of your organization's printers&mdash;no matter the [!INCLUDE[prod_short](includes/prod_short.md)] client or app you're using. Because [!INCLUDE[prod_short](includes/prod_short.md)] online is a cloud service, it can't directly reach local printers connected to users' devices, but you can connect it to cloud-enabled printers.

## What are your printer possibilities in Business Central

To support your print needs, [!INCLUDE[prod_short](includes/prod_short.md)] offers the following features:

|Feature|Description|Web client| Mobile app|App for Teams|
|-------|-----------|----------|-----------|--------------|
|Universal Print|Universal Print is a printer management solution available as a cloud service from Microsoft. With this feature, you can set up your printers in Universal Print, then register them for use in [!INCLUDE[prod_short](includes/prod_short.md)]. This feature requires a Universal Print subscription and the **Universal Print Integration** extension.|![works online.](media/check.png)|![works online.](media/check.png)|![works online](media/check.png)|
|Email Print|This feature lets you set up email-enabled printers. [!INCLUDE[prod_short](includes/prod_short.md)] then sends print jobs to a printer using the printer's email address. This feature requires email-enabled printers, and the **Send to Email Printer** extension.|![works online.](media/check.png)|![works online](media/check.png)|![works online](media/check.png)|
|Browser printing|Print jobs are handled by the print functionality of the user's browser. If a cloud printer isn't installed and set up, or if an installed printer fails, then printing will default to the printing options for the browser. The **Printer** field on the report request page will display *(Handled by the browser)*.|![works online](media/check.png)|||

Most of the work for setting up printers can be done from the **Printer Management** page in [!INCLUDE[prod_short](includes/prod_short.md)]. Although with Universal Print printers, you may also have to work in in Microsoft 365 admin center or the Azure Portal.

> [!IMPORTANT]
> For Business Central on-premises, Universal Print and Email Print require that Microsoft Entra ID or NavUserPassword authentication is used.

## Custom printer extensions

[!INCLUDE[prod_short](includes/prod_short.md)] supports other custom printer extensions that add even more print features. So if you have any custom printer extensions installed, your application may include print features not described in this article.

If you're an AL developer and want to learn about how to create printer extensions, go to [Developing Printer Extensions in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-reports-printing).

## Next steps

- [Set Up Universal Print Printers](admin-printer-setup-universal-print.md)  
- [Set Up Email Printers](admin-printer-setup-email.md)  
- [Set Up Default Printers](ui-specify-printer-selection-reports.md)