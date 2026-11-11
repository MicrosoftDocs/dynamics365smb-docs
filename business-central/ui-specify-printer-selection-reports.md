---
title: Specify a Default Printer in Business Central
description: Set default printers for users and reports in Business Central, understand printer selection priority, and override the printer when running a report.
author: jswymer
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.custom: bap-template
ms.search.keywords: online printing, email printing, cloud printing, Universal Print
ms.search.form: 2650, 2750, 2752, 2753, 2754, 8900
ms.date: 11/11/2026
ms.author: jswymer
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# Specify a default printer in Business Central

After printers have been set up in Business Central, you can then specify which printer you want to use by default for all companies in the environment. There are a couple of ways to specify printers to be used by default for reports and other print jobs. A default printer is useful if you work with different reports that require different printers because of their placement or their output capabilities.

> [!IMPORTANT]
> Choose a default from the printers available in Business Central. Cloud printers, such as email printers and Universal Print printers, must be set up first, typically by an administrator. On-premises, available printers can also include printers installed on the server. Learn more in [Printer setup and management](admin-printer-setup-overview.md).

## Set a printer as a default printer for all print jobs

Through the **Printer Management** page you set up a printer as a default printer for all print jobs. You can specify the printer as default for you only or for all users.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Printer Management**, then select the related link.

    > [!TIP]
    > You can also open the **Printer Management** page from the **Printer Selections** page by choosing **Printer Management**.  
1. On the **Printer Management** page, select a printer from the list, choose **Manage**, then choose **Set as my default printer** or **Set as default printer for all users**.

> [!NOTE]
> Setting a default printer from the **Printer Management** page adds or updates an entry on the **Printer Selections** page.

## Set a default printer for specific reports

The **Printer Selections** page lets you specify the printer a report uses by default. Default printers are set on a user-account basis. You can set a default printer for just yourself, another user, or all users.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Printer Selections**, then select the related link. Alternatively, select a printer on the **Printer Management** page, then choose the **Printer Selections** action.
1. Choose the **New** action to add a printer selection for a specific report.
1. Fill in the fields as necessary.

The specified report is now set up to print to the selected printer by default.

> [!NOTE]
> When you print the report, you can select a different printer in the **Printer** field on the report request page.

> [!NOTE]
> If you don't set a report up for a specific printer on the **Printer Selections** page, then it's printed to the default printer, as defined on the **Printer Management** page.

You or the administrator can also use the **Printer Selections** page to define other variations of printing for users and reports. The following table describes the combination of values to specify different printing setups for a report.

|To                                                 |Set the following values                                             |
|---------------------------------------------------|---------------------------------------------------------------------|
|Print a report to a specific printer for all users |Specify values in the **Report ID** and **Printer Name** fields and leave the **User ID** field blank.|
|Print all reports to a specific printer for a specific user|Specify values in the **User ID** and **Printer Name** fields and leave the **Report ID** field blank. This entry does the same as the **Set as my default printer** action on the **Printer Management** page.|
|Set the default printer for all reports for all users|Specify a value in the **Printer Name** field and leave the **User ID** and **Report ID** fields blank. This entry does the same as the **Set as default printer for all users** action on the **Printer Management** page.|
|Use no designated printer for a specific report|Specify a value in the **Report ID** field and leave the **Printer Name** and **User ID** fields blank. Browser printing is used when available. This entry doesn't fall back to the user's default printer.|
|Print a specific report to a specific printer for a specific user|Specify values in all three fields.|

> [!NOTE]
> Business Central checks printer selections in this order: the current user and report, all users and the report, the current user and all reports, then all users and all reports. The first matching entry is used, even if its **Printer Name** field is blank.

## Choose a printer when running a report

Instead of using the default printer when running a report, you can override this setting from the request page. Simply choose the printer you want to use for this report generation in the **Printer** dropdown menu.

## Keep print jobs within size limits

The Business Central Universal Print integration limits each print job to 10 MB. Other cloud printing providers can have different limits. If you need to print a larger report, filter it into smaller print jobs.

## Related information

[Printer Management](admin-printer-setup-overview.md)  
[Set Up Universal Print Printers](admin-printer-setup-universal-print.md)  
[Set Up Email Printers](admin-printer-setup-email.md)  
[Printing a Report](ui-work-report.md#PrintReport)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Run Batch Jobs](ui-how-run-batch-jobs.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
