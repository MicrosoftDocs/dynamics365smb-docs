---
title: Opening Business Central Files in OneDrive
description: Learn how you can share Business Central data through OneDrive for Business. 
author: jswymer
ms.topic: conceptual
ms.workload: na
ms.search.keywords:
ms.date: 02/28/2022
ms.author: jswymer

---
# Opening and Sharing Business Central Files in OneDrive

[!INCLUDE[prod_short](includes/prod_short.md)] makes it easy to store, manage, and share files with other people through OneDrive for Business. On most pages where files are available, such as the Report Inbox or files that are attached to records, you'll find an **Open in OneDrive** and **Share** action.


:::image type="content" source="media/onedrive-overview-report-inbox-w-outline.png" alt-text="The Open in OneDrive and Share actions for reports":::


:::image type="content" source="media/one-drive-attachments-w-outline.png" alt-text="The Open in OneDrive and Share actions for attachments":::

<!--
:::image type="content" source="media/Open in OneDrive.PNG" alt-text="The Open in OneDrive action":::

 
:::image type="content" source="media/OneDrive attachment.PNG" alt-text="Share file attachments in OneDrive":::
-->

## Open in OneDrive

The **Open in OneDrive** action copies the file to your OneDrive and opens the file in their online applications, like Excel online, Word online, and PowerPoint online. 

<!--## Working with Different Types of Files-->

When you choose **Open in OneDrive**, [!INCLUDE[prod_short](includes/prod_short.md)] identifies Excel, Word, and PowerPoint files and opens them in their online applications, that is, Excel online, Word online and PowerPoint online. You can annotate, edit, and collaborate with others without leaving the browser.

For other popular file types, like PDFs, text files, and images, OneDrive provides file viewers that offer features for printing, sharing, and more. If a file can't be viewed in OneDrive, you might be prompted to download it.

## Share

The **Share** action copies the file to your OneDrive and let's you share the file with other people and see who you've already shared the file with. When you select the **Share** action, the following page opens.

:::image type="content" source="media/share-to-onedrive-dialog.PNG" alt-text="Share file in OneDrive":::

If you're familiar with OneDrive, you may recognize the page. You have two options for sharing the file: **Send link** and **Copy link**.

- **Send link** let's you share the files with specific people. The people you share the file will get an email with a link to the file. The file will also appear in the **Shared** section of their OneDrive. Start by typing the email addresses or contact names in the **Name, group or email field**.

- **Copy link** copies a link to the file on your OneDrive so you can use the link in other places like Facebook, Twitter, or emails. 

Before you send or copy the link, set the permission to the file that you want people to have. You can see the current setting under **Send link** and **Copy link**. In most cases, it will be **Anyone with the link can edit to open the link**, depending on settings set by your administrator. To change the permissions, select the link and make changes on the **Link Settings** page.

The sharing feature in Business Central is based on OneDrive. So to learn more about sharing and permissions, see [Share OneDrive files and folders](https://support.microsoft.com/en-us/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

> [!NOTE]
> The **Share** action isn't available in the Business Central app for mobile devices.

## First-time sign in from Business Central

When you use the **Open in OneDrive** or **Share** action for the first time, [!INCLUDE[prod_short](includes/prod_short.md)] does the following things:

1. Opens the **Please review terms and conditions** page. Read the page, and if you agree with the terms and conditions, select **Agree** to continue.
2. Opens the **Pick an account** page  Select your account or **use another account** if you don't see your own, then enter the user name and password when prompted.
3. Creates a folder named [!INCLUDE[prod_short](includes/prod_short.md)] in OneDrive. 
4. In the [!INCLUDE[prod_short](includes/prod_short.md)] folder, it creates another folder with the same name as the company you're working in. If you work in more than one company, it will create a folder for the company you're working in when you use the **Open in OneDrive** and **Share** actions. 
5. Puts a copy of the file you selected in the folder, and then opens the file. The next time you use the action, it only copies and opens the file. 

## Managing multiple copies of a file

When you choose **Open in OneDrive** or **Share**, the file is copied from [!INCLUDE[prod_short](includes/prod_short.md)] to your folder in OneDrive. If you edit the file in OneDrive, the copies of the file will be different. To update [!INCLUDE[prod_short](includes/prod_short.md)] with the latest file, remove the existing file from [!INCLUDE[prod_short](includes/prod_short.md)] and then upload the latest copy.

Also, when a file with the same name already exists in OneDrive, [!INCLUDE[prod_short](includes/prod_short.md)] will provide a choice to either replace the file or keep both files. If you choose to keep both files, the new file is copied to OneDrive and given a filename with suffix number, like  “Items (2).xlsx,”. The original file isn't changed. 

If you choose to replace the file, the new file is added to the version history for that file. The original file isn't lost, and you can view or restore previous versions of the file. 

## About your Business Central folder on OneDrive

The folder and its content are private until you decide to share them with others. For example, you might decide to share content with one or more of your coworkers, or even people outside of your organization. 
You can access your OneDrive from the **My Settings** page by choosing the link in the **Cloud Storage** field. For more information, see [Share OneDrive files and folders](https://support.microsoft.com/en-us/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

:::image type="content" source="media/my-settings-cloud-storage.PNG" alt-text="The Cloud Storage field in My Settings":::

<!--## Extending the Connection to OneDrive
You can create an extension and connect it to... For more information, see...-->

## See Also
[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[OneDrive FAQ](admin-onedrive-faq.md)