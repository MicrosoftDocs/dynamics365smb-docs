---
title: Business Central and OneDrive for Business Integration
description: You can use OneDrive for Business to store, manage, and share files, such as reports or file attachments. Also if you spell it One Drive. 
author: jswymer
ms.topic: overview
ms.search.keywords:
ms.date: 06/13/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ms.custom: sfi-image-nochange
---

# Business Central and OneDrive integration

OneDrive for work or school (formerly known as OneDrive for Business) is a cloud storage service that is included in Microsoft 365. [!INCLUDE[prod_short](includes/prod_short.md)] makes it easy to store, manage, and share files with other people through OneDrive. When a file is in your OneDrive you enjoy the rich collaborative experiences from the online versions of Microsoft products, such as Word, Excel, and PowerPoint. For example, you can share a Word document, and then you and your colleagues can edit it together in real-time. OneDrive also lets you open other types of files, such as PDFs. 

## Get started with OneDrive features

If you're using [!INCLUDE[prod_short](includes/prod_short.md)] online, we've already created the connection between [!INCLUDE[prod_short](includes/prod_short.md)] online and OneDrive, so it's easy to get started. The only requirement is that users have opened OneDrive at least one time. With [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, an administrator has to configure the connection before you can get started. Learn more at [Managing OneDrive Integration with Business Central](admin-onedrive-integration.md).

<!-- We've created the connection between [!INCLUDE[prod_short](includes/prod_short.md)] online and OneDrive, so it's easy to get started. The only requirement is that users have opened OneDrive at least one time. -->

### Open and share in OneDrive

On most pages where files are available, such as the Report Inbox or files that are attached to records, you'll find an **Open in OneDrive** and **Share** actions.

:::image type="content" source="media/onedrive-overview-report-inbox-w-outline.png" alt-text="The Open in OneDrive and Share actions for reports":::


:::image type="content" source="media/one-drive-attachments-w-outline.png" alt-text="The Open in OneDrive and Share actions for attachments":::

|Select...|To...|See more info...|
|---------|-----|----------------|
|Open in OneDrive|Copy the file to a Business Central folder in your OneDrive and open the file.|[Open in OneDrive](across-share-onedrive.md#open-in-onedrive) |
|Share|Copy the file to your OneDrive and share it with other people.|[Share in OneDrive](across-share-onedrive.md#share) |

### Save Excel workbooks and report files in OneDrive

With OneDrive integration set up, a couple other familiar features will automatically use OneDrive for saving files instead of saving files on your device:

- The **Open in Excel** and **Edit in Excel** actions on list pages will automatically copy the Excel file to OneDrive, then open it in Excel Online. For more information, see [Viewing and Editing in Excel](across-work-with-excel.md).
- Sending a report to an Excel or Word file will automatically copy the file to OneDrive, then open it in the Excel or Word online. For more information, see [Saving a report to a file](ui-work-report.md#save-a-report-to-a-file).

These features aren't turned on by default. But as an administrator, you can easily turn them on by using the **OneDrive Setup** assisted setup guide.

<!--
When you use the **Open in OneDrive** action for the first time, [!INCLUDE[prod_short](includes/prod_short.md)] does the following in your OneDrive:

1. Creates a folder named [!INCLUDE[prod_short](includes/prod_short.md)]. 
2. In the [!INCLUDE[prod_short](includes/prod_short.md)] folder, it creates another folder with the same name as the company you're working in. If you work in more than one company, it will create a folder for the company you're working in when you use the **Open in OneDrive** action. 
3. Puts a copy of the file you selected in the folder, and then opens the file. The next time you use the action, it only copies and opens the file. 

The folder and its content are private until you decide to share them with others. For example, you might decide to share content with one or more of your coworkers, or even people outside of your organization. For more information, see [Share OneDrive files and folders](https://support.microsoft.com/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07) in the content for OneDrive.
-->

> [!NOTE]
> You can also connect your [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to OneDrive. However, there are a few things to do to make it work. For more information, see [Configuring Business Central On-Premises](admin-onedrive-integration-onpremises.md).

## Related information

[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[Opening Business Central Files in OneDrive](across-share-onedrive.md)  
[OneDrive FAQ](admin-onedrive-faq.md)  
