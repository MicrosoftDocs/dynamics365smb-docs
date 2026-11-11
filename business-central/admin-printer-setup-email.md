---
title: Set Up Email Printers in Business Central
description: Set up email-enabled printers in Business Central to send reports and documents directly to a printer, and choose the paper size for print jobs.
author: jswymer
ms.author: jswymer
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 01/26/2023
ms.custom: bap-template
ai-usage: ai-assisted
---
# Set up email printers in Business Central

This article explains how to set up email-enabled printers in [!INCLUDE[prod_short](includes/prod_short.md)]. With these printers, [!INCLUDE[prod_short](includes/prod_short.md)] sends print jobs to the printer using the printer's email address.

> [!TIP]
> Learn more in [Printer management overview](admin-printer-setup-overview.md).

## Prerequisites for email printing

- [!INCLUDE[prod_short](includes/prod_short.md)] 2020 release wave 1 or later
- **Send to Email Printer** extension is installed

    This extension is installed by default. Learn more in [Install and uninstall extensions in Business Central](ui-extensions-install-uninstall.md).
- Email functionality is set up.

   Learn more in [Set up email](admin-how-setup-email.md).

## Add an email printer

The **Printer Management** page shows you the printers currently set up. The page also enables you to access the **Settings** page for each printer to edit an existing setup or set up a new printer.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Printer Management**, then select the related link.
1. Select **Email Print** > **Add an email printer**.
1. On the **Email Printer Settings** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > You must manually select the appropriate paper size for a printer as no local printer or user settings can be stored.
    >
    > Be aware that the Email Printer extension is set to **A4** paper size by default, which isn't suited in North America, for example.

## Protect print job privacy

If you use the Email Printer extension, all or some print jobs are sent to the email address configured for the printer. We strongly recommend that a unique email ID is tied to a printer device using only the official services provided by the hardware manufacturer, such as HP ePrint, KonicaMinolta EveryonePrint, or Epson Email Print.

Take all necessary privacy precautions, including ensuring that the email printing solution has properly configured permissions, privacy settings, and retention policies. It is your responsibility to provide a correct, verified, and operational email address. Learn more in [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839)<!--(https://privacy.microsoft.com/privacystatement)-->.

## Next steps

[Set Up Default Printers](ui-specify-printer-selection-reports.md)

## Related information

[Printer Management Overview](admin-printer-setup-overview.md)  
[Set Up Universal Print Printers](admin-printer-setup-universal-print.md)
[Printing a Report](ui-work-report.md#PrintReport)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Run Batch Jobs](ui-how-run-batch-jobs.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
