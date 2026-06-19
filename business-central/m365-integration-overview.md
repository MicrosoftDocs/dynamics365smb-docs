---
title: Integrating with Office apps and Microsoft 365 
description: Learn how to integrate Business Central with Office apps and Microsoft 365.
author: kennienp
ms.reviewer: jswymer
ms.topic: overview
ms.author: kepontop
ms.date: 06/19/2026
ms.custom: bap-template
---

# Integrating with Office apps and Microsoft 365

[!INCLUDE[prod_short](includes/prod_short.md)] integrates with [!INCLUDE[m365](includes/m365-name.md)] to gain extra features. This article introduces some of these features.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/m365-integrations-detail.svg" alt-text="Shows how Business Central integrates to Microsoft 365" lightbox="/dynamics365/business-central/dev-itpro/developer/media/m365-integrations-detail.svg":::

## Using [!INCLUDE[m365_excel](includes/m365-excel-name.md)] with [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE[m365_excel](includes/m365-excel-name.md)] is used in [!INCLUDE [prod_short](includes/prod_short.md)] in the following scenarios:

- View or edit [!INCLUDE [prod_short](includes/prod_short.md)] data in Excel.
- Support analytical reporting.
- Manage G/L budgets (export to, or import from Excel).
- Import data from other systems.

With pages that display a list of records in rows and columns, like a list of customers, sale orders, or invoices, you can export the list to [!INCLUDE[m365_excel](includes/m365-excel-name.md)] and work with it there. Depending on the page, there are two options:

- **Open in Excel**, where [!INCLUDE [prod_short](includes/prod_short.md)] produces an Excel workbook with the data on the page. This option is useful for slicing and dicing the data for various analyses and keeping a copy.
- **Edit in Excel** also produces an Excel workbook with the data on the page. However, it goes a step further and uses the [!INCLUDE [prod_short](includes/prod_short.md)] add-in for Excel to let you publish changes you make to the data in the workbook back to [!INCLUDE [prod_short](includes/prod_short.md)]. For example, Edit in Excel is a fast way to update information in a large number of records.

Learn more at [Viewing and Editing in Excel From Business Central](across-work-with-excel.md).

Power users can use Excel as the design tool for the layout of analytical reports and then upload the Excel layout workbook to [!INCLUDE [prod_short](includes/prod_short.md)]. Anyone who has access to these reports can run them. When the [!INCLUDE [prod_short](includes/prod_short.md)] server generates the Excel report, it merges the Excel layout workbook with data and returns the resulting Excel workbook to you as a downloaded file. Learn more at [Working with Microsoft Excel Layouts](ui-excel-report-layouts.md?tabs=any-report).

> [!TIP]
> If you also enable integration to [!INCLUDE[m365_onedrive_for_business](includes/m365-onedrive-for-business-name.md)], you can open Excel workbooks from [!INCLUDE [prod_short](includes/prod_short.md)] in a browser by using Excel for the web.

If your organization uses G/L budgets, you can export a budget to Excel where you can process or analyze the budget data, and then import the data back to [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more at [Exporting and importing G/L budgets with Excel](finance-how-create-budgets.md#exporting-and-importing-gl-budgets-with-excel).

You can import master data and some transactional data from other applications using configuration packages in [!INCLUDE [prod_short](includes/prod_short.md)]. For example, you can export the configuration package to Excel and set up your data there. Then, you can import the data from Excel again. Learn more at [Using Excel to import data from other systems](across-import-data-configuration-packages.md).

## Integrate with OneDrive

[!INCLUDE[m365_onedrive_for_business](includes/m365-onedrive-for-business-name.md)] is a cloud storage service that is included in Microsoft 365. [!INCLUDE[prod_short](includes/prod_short.md)] makes it easy to store, manage, and share files with other people through OneDrive.

When an administrator enables [!INCLUDE[m365_onedrive_for_business](includes/m365-onedrive-for-business-name.md)] in [!INCLUDE[prod_short](includes/prod_short.md)], more features become available. For example:

- The **Open in OneDrive** and **Share** actions are available on most pages that contain files, such as the **Report Inbox** page or pages where you can attach files to records.
- The **Open in Excel** and **Edit in Excel** actions on list pages automatically copy the Excel file to OneDrive, then open it in Excel Online.
- The **Send to Microsoft Excel document** and **Send to Microsoft Word document** actions automatically copy the file to OneDrive, then open it in Excel or Word online.

Learn more at [Business Central and OneDrive Integration](across-onedrive-overview.md).

## Use [!INCLUDE[m365_outlook](includes/m365-outlook-name.md)] with [!INCLUDE [prod_short](includes/prod_short.md)]

With [!INCLUDE [prod_short](includes/prod_short.md)], you can manage business interactions with your customers and vendors directly in [!INCLUDE[m365_outlook](includes/m365-outlook-name.md)]. Install the [!INCLUDE [prod_short](includes/prod_short.md)] add-in for [!INCLUDE[m365_outlook](includes/m365-outlook-name.md)] to get the following capabilities:

- **Contact insights**: This add-in lets you look up [!INCLUDE [prod_short](includes/prod_short.md)] customer or vendor information in [!INCLUDE[m365_outlook](includes/m365-outlook-name.md)] emails and calendar appointments. It also lets you create and send emails including [!INCLUDE [prod_short](includes/prod_short.md)] business documents, such as a sales quote or invoice to a contact.
- **Document view**: When a business document is sent in an email, the add-in provides a direct link from the email to the actual business document in [!INCLUDE [prod_short](includes/prod_short.md)].

Learn more at [Get the Business Central Add-in for Outlook](/dynamics365/business-central/admin-outlook).

## Integrate with [!INCLUDE[m365_teams](includes/m365-teams-name.md)]

[!INCLUDE [prod_short](includes/prod_short.md)] offers an app that connects [!INCLUDE[m365_teams](includes/m365-teams-name.md)] to the data in [!INCLUDE [prod_short](includes/prod_short.md)] so that you can quickly share details across team members and respond faster to inquiries.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/teams-intro-v3.png" alt-text="Shows how Business Central integrates to Teams" lightbox="/dynamics365/business-central/dev-itpro/developer/media/teams-intro-v3.png":::

Learn more at [Share Business Central records and page links in Microsoft Teams](across-working-with-teams.md).

## Using [!INCLUDE[m365_word](includes/m365-word-name.md)] with [!INCLUDE [prod_short](includes/prod_short.md)]

Power users in [!INCLUDE [prod_short](includes/prod_short.md)] can use [!INCLUDE[m365_word](includes/m365-word-name.md)] for the following scenarios:

- To change the layout of their outgoing documents.
- To make it easy to mass communicate in print or email.

If your organization wants to change the layout of its customer-facing documents, such as quotes, sales orders, or sales invoices, a power user can use Word as a design tool to change the layout. When [!INCLUDE [prod_short](includes/prod_short.md)] generates the document report, it merges the Word layout with data and sends the resulting PDF document to the user as a downloaded file (or to a printer). Learn more at [Work with Word Layouts](ui-how-add-fields-word-report-layout.md).

To make it easy to mass communicate in print or email, power users can use mail merge commands in Word to use Word as the design tool to create the layout of the message. They can then upload the Word document to [!INCLUDE [prod_short](includes/prod_short.md)]. When you run the campaign, the [!INCLUDE [prod_short](includes/prod_short.md)] platform merges data from entities such as contacts, customers, and vendors with the template to produce the final documents to send to clients. Learn more at [Using Word Templates for Bulk Communication](ui-mail-merge.md).

## Related information

[Viewing and Editing in Excel From Business Central](across-work-with-excel.md)  
[Working with Microsoft Excel Layouts](ui-excel-report-layouts.md?tabs=any-report)  
[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Using Outlook with Business Central](admin-outlook.md)  
[Work with Word Layouts](ui-how-add-fields-word-report-layout.md)  
[Use Word Templates for Bulk Communication](ui-mail-merge.md)  
[Business Central integrations overview](integration-overview.md)