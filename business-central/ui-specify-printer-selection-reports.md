---
title: Setting Up Reports to Print on Specific Printers | Microsoft Docs
description: Learn about specifying a printer for a report and using the Printer Selections page.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: online printing
ms.date: 04/17/2020
ms.author: sgroespe

---
# Set Up Printers
Because [!INCLUDE[prodshort](includes/prodshort.md)] is a cloud service, it cannot reach local printers connected to users' machines. However, it can connect to cloud-enabled printers. In the generic version of [!INCLUDE[prodshort](includes/prodshort.md)], a cloud printer named **Email Printer** is installed as an extension and is ready to use after initial setup.

If a cloud printer is not installed and set up, or if an installed printer fails, then printing will default to the printing options for the browser. This is indicated by this value in the **Printer** field on the report request page: *(none, handled by the browser)*.

On the **Printer Management** page, you can see the printers that are set up. When you have set up one or more printers, you can open the **Printer Selections** page to set up for your user account which specific reports to print with which printer.

When a printer is set up and assigned to specific reports, you print a report by choosing the **Print** button on the report request page. For more information, see [Printing a Report](ui-work-report.md#PrintReport).

### Sizing Print Jobs
Cloud printing is designed for documents of a reasonable size. Most cloud services, including PrintNode and HP ePrint, have a limit of 10 MB per job. If you need to print larger reports, you may have to split them in multiple printouts.

## To set up a printer
On the **Printer Management** page, you can see the printers that are set up and you can access the **Settings** page for each printer to edit an existing setup or set up a new printer.

The following procedure describes how to set up the existing **Email Printer** printer, which is a preinstalled extension.

> [!NOTE]
> To use email printing, email functionality must be set up. For more information, see [Set Up Email](admin-how-setup-email.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Printer Management**, and then select the related link.
2. Select the line for the **Email Printer** printer, and then choose the **Edit printer settings** action.
3. On the **Settings** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > You must manually select the appropriate paper size for a printer as no local printer or user settings can be stored.
    >
    > Beware that the Email Printer extension is set to **A4** paper size by default, which is not suited in North America, for example.
4. To make a printer your default, On the **Printer Management** page, choose the **Set as my default printer**.

### Privacy Notice
If you use the Email Printer extension, then all or some print jobs will be sent to the email address that you provided when configuring the printer. We strongly recommend that a unique email ID be tied to a printer device using only the official services provided by the hardware manufacturer, such as HP ePrint, KonicaMinolta EveryonePrint, or Epson Email Print.

You must take all necessary privacy precautions, including ensuring that the email printing solution has properly configured permissions, privacy settings, and retention policies. It is your responsibility to provide a correct, verified, and operational email address. For more information, see [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement).

## To select which printers print which reports
On the **Printer Selections** page, you can set up for your user account which reports are printed by which printer. This is useful if you work with different reports that require different printers because of their placement in the company or their output capabilities.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Printer Selections**, and then select the related link. Alternatively, from the **Printer Management** page, select a printer, and then choose the **Printer Selections** action.
2. Choose the **New** action to add a printer selection for a specific report.
3. Fill in the fields as necessary.

The specified report is now set up to print to the selected printer by default.

> [!NOTE]
> When you print the report in question, you can override this setup by selecting another printer on the **Print Settings** request page.

> [!NOTE]
> If you do not set a report up for a specific printer on the **Printer Selections** page, then it will be printed to the default printer of the company, as defined from the **Printer Management** page.

You or the administrator can also use the **Printer Selections** page to define other variations of printing for users and reports. The following table describes the combination of values to specify different printing setup for a report.

|To                                                 |Set the following values                                             |
|---------------------------------------------------|---------------------------------------------------------------------|
|Print a report to a specific printer for all users |Specify values in the **Report ID** and **Printer Name** fields and leave the **User ID** field blank.|
|Print all reports to a specific printer for a specific user|Specify values in the **User ID** and **Printer Name** fields and leave the **Report ID** field blank.|
|Set the default printer for all reports|Specify a value in the **Printer Name** field and leave the **User ID** and **Report ID** fields blank.|
|Print a specific report to the user’s default printer|Specify a value in the **Report ID** field and leave the **Printer Name** and **User ID** fields blank.|
|Print a specific report to a specific printer for a specific user|Specify values in all three fields.|

> [!NOTE]
> More specific printer selections take precedence over a more general printer selections. For example, a printer selection that has values in the **User ID**, **Report ID**, and **Printer Name** fields takes precedence over a printer selection that has blank entries in the **User ID** or **Report ID** fields.

## See Also
[Printing a Report](ui-work-report.md#PrintReport)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Run Batch Jobs](ui-how-run-batch-jobs.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
