---
title: Set Up Universal Print Printers in Business Central
description: Set up Universal Print, share printers with licensed users, and add the printers to Business Central online or on-premises for cloud printing.
author: jswymer
ms.author: jswymer
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 11/11/2026
ms.custom: bap-template
ai-usage: ai-assisted
---

# Set up Universal Print printers in Business Central

Universal Print is a Microsoft 365 subscription-based service that runs entirely on Microsoft Azure. It gives you centralized printer management through the Universal Print portal. [!INCLUDE[prod_short](includes/prod_short.md)] makes printers set up in Universal Print available to client users through the **Universal Print Integration** extension.

:::image type="content" source="media/Universal-Print-arch.png" alt-text="Diagram showing how Business Central connects to printers through Universal Print.":::

The complete setup requires you to work in both Microsoft Azure, using the [Azure portal](https://portal.azure.com), and in [!INCLUDE[prod_short](includes/prod_short.md)]. The setup is divided between two main tasks as described in this article:

1. In Microsoft Azure, set up Universal Print and add the printers you want to use in Business Central to a print share. Learn more in [Set up Universal Print and printers in Microsoft Azure](#set-up-universal-print-and-printers-in-microsoft-azure).
1. In [!INCLUDE[prod_short](includes/prod_short.md)], add the printers from the print shares in Universal Print. Learn more in [Add printers in Business Central online](#add-printers-in-business-central-online) or [Add printers in Business Central on-premises](#add-printers-in-business-central-on-premises).

## Prerequisites for Universal Print

- Supported printers

  [!INCLUDE[prod_short](includes/prod_short.md)] supports the same printers as Universal Print, which can be either Universal Print–compatible or non-compatible printers. Non-compatible printers can't communicate with Universal Print directly, so they require extra connector software, which is provided by Universal Print. Some older printers may not be supported. 

- Universal Print:

  - Your organization has a Universal Print subscription/license.

    Learn more in [License Universal Print](/universal-print/fundamentals/universal-print-license).

  - You have at least the [Printer Administrator](/entra/identity/role-based-access-control/permissions-reference#printer-administrator) role in Microsoft Entra ID.

    To manage Universal Print, your account must have at least the [Printer Administrator](/entra/identity/role-based-access-control/permissions-reference#printer-administrator) role in Microsoft Entra ID. This role is only needed for managing Universal Print. It isn't required by people adding or using the printers from [!INCLUDE[prod_short](includes/prod_short.md)].

- [!INCLUDE[prod_short](includes/prod_short.md)] online and on-premises:

  - [!INCLUDE[prod_short](includes/prod_short.md)] 2021 release wave 1 or later.
  - **Universal Print Integration** extension is installed.

    This extension is published and installed by default as part of [!INCLUDE[prod_short](includes/prod_short.md)] online and on-premises. You can verify whether it's installed on the **Extension Management** page. Learn more in [Install and uninstall extensions in Business Central](ui-extensions-install-uninstall.md).
- [!INCLUDE[prod_short](includes/prod_short.md)] on-premises only:
  - Microsoft Entra ID or NavUserPassword authentication is configured.

    > [!NOTE]
    > Universal Print extension doesn't support service-to-service (S2S) authentication. It requires a signed-in user to send print jobs to the Universal Print service through Graph API.

    > [!CAUTION]
    > Microsoft recommends that you don't use NavUserPassword authentication. Microsoft Entra ID and Windows authentication are more secure alternatives. You should only use NavUserPassword authentication when Microsoft Entra ID and Windows authentication aren't viable.

  - An application for Business Central is registered in your Microsoft Entra tenant and [!INCLUDE[prod_short](includes/prod_short.md)].

    Like other Azure services that work with [!INCLUDE[prod_short](includes/prod_short.md)], Universal Print requires an app registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Entra ID. The app registration provides authentication and authorization services between [!INCLUDE[prod_short](includes/prod_short.md)] and Universal Print.

    Your deployment may already use an app registration for other Azure services, like Power BI. If so, then use the existing app registration for Universal Print as well, instead of adding a new one. Modify the app registration to include the relevant delegated permissions for Microsoft Graph API: `PrinterShare.ReadBasic.All`, `PrintJob.Create`, and `PrintJob.ReadBasic.All`.

    To register an app and set the proper permissions, follow the steps described in [Register an application in Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory).

## Set up Universal Print and printers in Microsoft Azure

Before you can start managing Universal Print printers in Business Central, there are several tasks to get Universal Print up and running in Azure with the printers you want to use.

Learn more in [Get started: Set up Universal Print](/universal-print/fundamentals/universal-print-getting-started). Here's an overview of the steps you'll need to complete. Most of these steps are done in the Azure portal.

1. Assign Universal Print licenses to yourself and other users.

    You can assign licenses in the Microsoft 365 admin center for both Business Central online and on-premises. Learn more in [Assign licenses to users in the Microsoft 365 admin center](/microsoft-365/admin/manage/assign-licenses-to-users).

1. Install the Universal Print connector for registering printers that can't communicate with Universal Print directly.

    Printers that aren't Universal Print ready require the Universal Print connector. Learn more in [Install the Universal Print connector](/universal-print/fundamentals/universal-print-connector-installation).

1. Register your printers in Universal Print.

    Registering a printer makes Universal Print aware of the printer.

    - For printers that can communicate directly with Universal Print, follow the steps provided by the printer manufacturer.

    - For other printers, register the printers by using the Universal Print connector. 

      Learn more in [Printer registration](/universal-print/fundamentals/universal-print-connector-printer-registration).

1. Change printer properties if needed.

    After a printer is registered, you can view and modify printer properties, such as default preferences.

    Learn more in [Manage printer settings using the Universal Print portal](/universal-print/reference/portal/printer-settings).

1. Share the printers with users.

    Any printer you want to use in [!INCLUDE[prod_short](includes/prod_short.md)] must be added to a *printer share* in Universal Print. Give users access to the share individually or through a group. You can also allow everyone in your organization. Learn more in [Share a printer](/universal-print/reference/portal/share-printers).

    > [!TIP]
    > You can add or remove users later. Learn more in [Configure user permissions for a printer share](/universal-print/reference/portal/share-printers#configure-user-permissions-for-a-printer-share).

1. Enable document conversion if the printer requires it.

    Business Central sends PDF documents to Universal Print. If the printer doesn't support PDF, enable document conversion so Universal Print can convert PDF to XPS. Universal Print also supports conversion from XPS to PDF for other applications.

    Learn more in [Document conversion](/universal-print/reference/portal/settings#2-document-conversion).

Now, you're ready to add the printers to [!INCLUDE[prod_short](includes/prod_short.md)], set up default printers for reports, and print.  

## Add printers in Business Central online

After printers are set up and shared in Universal Print, you're ready to add them to [!INCLUDE[prod_short](includes/prod_short.md)] for use. There are two ways to add Universal Print printers. You can add the printers all at once or individually, one at a time.

Adding printers individually lets you set up the same Universal Print printer in [!INCLUDE[prod_short](includes/prod_short.md)] more than once. Then, for each added printer, you can change the print settings, like paper tray, size, and orientation. This way, you can set up printers for different reports and documents with special output requirements.

> [!NOTE]
> Are you using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises? The first-time setup is slightly different. Learn more in [Add printers in Business Central on-premises](#add-printers-in-business-central-on-premises).
<!-- To Do Adding printers individually lets you duplicate printers with custom , like different paper trays and paper size and orientation.  To add printers individually, you'll need to know printer's share name in Universal Print. -->

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Printer Management**, then select the related link.
1. Select **Universal Print**, then choose one of the following options:

   - **Add all Universal Print printers** to add all printers not already added. You can use this option even if there are already printers added.
   - **Add a Universal Print printer** to add a specific printer.  
1. Follow the on-screen instructions.

    - If you chose **Add all Universal Print printers**, then the **Add Universal Print Printers** setup starts. 

    - If you chose to **Add a Universal Print printer**, then the **Universal Printer Settings** page appears. Fill in the **Name** field, then select **...** next to the **Print Share in Universal Print** field to select the printer share that contains the Universal Print printer. Fill in the remaining fields as needed. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

After a printer has been added, you can view and change its settings from the **Printer Management** page. Just select the printer, then choose **Edit printer settings**.

## Add printers in Business Central on-premises

<!--With [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, unlike online, users aren't automatically authenticated with the registered app in Azure used for the Universal Print service. So, before any Business Central user (including admins) can add or even use Universal Print printers, they'll have to authenticate with the Azure app and grant access to the Universal Print service. The following procedure describes how to initiate this authentication flow. Each user typically only has to do this task once.-->

Before a user can add or use Universal Print printers in Business Central, they must authorize access to the Azure services used by Universal Print and grant permission for data and operations like:

- Signing in and reading user profile
- Reading basic print job information
- Creating print jobs

Business Central online obtains the access token without this interactive authorization flow. For Business Central on-premises, the assisted setup first tries to use an existing token. If no usable token is available, each user must sign in and authorize the registered application. Follow the steps below when prompted. You might need to authorize the application again if its configuration or your access changes.

> [!NOTE]
> If you're an admin, we recommend you complete this task before other users. Then inform users who need Universal Print printers how to do it. If the registered application requires admin consent for API permissions, an administrator with permission to grant that consent can do so on behalf of the organization.

<!-- To Do Adding printers individually lets you duplicate printers with custom , like different paper trays and paper size and orientation.  To add printers individually, you'll need to know printer's share name in Universal Print. -->
### Connect to Universal Print for the first time

Complete these steps to connect to the Universal Print service for the first time.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Printer Management**, then select the related link.
1. Select **Universal Print** > **Add all Universal Print printers** to start the **Add Universal Print Printers** assisted setup guide.
1. Follow the on-screen instructions to connect your Microsoft Entra application. When authorization is required, the **Microsoft Entra service permissions** page opens.

    <!--The MICROSOFT ENTRA SERVICE PERMISSIONS page appears. You'll be prompted to give consent to Azure Services. You'll be lead through the process of verifying your Microsoft Entra ID setup, checking your Universal Print license, and then adding the printers.-->

   :::image type="content" source="media/azure-ad-services-permissions.png" alt-text="Microsoft Entra service permissions page with the Authorize Azure Services link.":::

1. Select the **Authorize Azure Services** link.

   1. If Microsoft Entra ID prompts for consent, review the permissions and grant consent to continue. If your account has permission to grant admin consent, you can grant consent on behalf of your organization.

      :::image type="content" source="media/azure-ad-permissions-requested.png" alt-text="Microsoft Entra consent prompt listing the permissions requested by the application.":::

   1. If you're prompted, sign in with your account.

1. When authorization completes successfully, you're returned to the **Add Universal Print Printers** page. Follow the remaining instructions to complete the setup.

After a printer has been added, you can view and change its settings from the **Printer Management** page. Just select the printer, then choose **Edit printer settings**.

Once you complete the initial sign-in, you can use the Universal Print printers to print reports and other print jobs. Learn more in [Print a report](ui-work-report.md#PrintReport). If you want to add or change printers, go back to the **Printer Management** page and select **Universal Print**.

## Common problems and resolutions

In this section, you'll learn about the common problems that users may experience when trying to set up or use Universal Print printers.

### You don't have access to a printer

If a user gets this message when trying to print a document to a Universal Print printer, it may be caused by one of the following conditions:

- The user doesn't have a Universal Print license assigned to their account.
- The user isn't assigned to the printer share in Universal Print.
- (On-premises) The Azure app registration used for Universal Print isn't working or has recently changed since the last time the user signed in.
- (On-premises) The user hasn't yet signed in to the registered application for Universal Print and granted consent.

### An error occurs when fetching shared printers

If a user gets **There was an error fetching printers shared to you** when trying to add a Universal Print printer from the **Printer Management** page, check their Universal Print license and printer-share access. For on-premises, also check whether they have signed in to the registered application and granted consent.
<!--
### Troubleshooting

#### You don't see the a printer in the 

The printer is not shared in Universal Print.

### You get an error when tryong to add all or a single printer

You have'nt been assigned a Uincersla Print license.

There was an error fetching printers shared to you. You don't have access to the data. Make sure your account has been assigned a Universal Print license and you have the required permissions.
or 
You don't seem to have access to Universal Print. Make sure you have a Universal Print subscription, and that your account has been assigned a Universal Print license.

## Could not upload the document to print job 50.

There is a technical problem with the printer. Unsupported document-format: application/pdf. Supported formats: Attribute document-format-supported: SimpleIppValue-Type:MimeMediaType-Value:application/oxps




-->

## Next steps
[Set Up Default Printers](ui-specify-printer-selection-reports.md).

## Related information

[Printers Overview](admin-printer-setup-overview.md)  
[Set Up Email Printers](admin-printer-setup-email.md)
[Printing a Report](ui-work-report.md#PrintReport)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Run Batch Jobs](ui-how-run-batch-jobs.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
