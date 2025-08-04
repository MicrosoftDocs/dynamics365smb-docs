---
title: Opening Business Central Files in OneDrive
description: Learn how you can share Business Central data through OneDrive for Business. 
author: jswymer
ms.topic: how-to
ms.search.keywords:
ms.date: 08/03/2022
ms.author: jswymer

ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Opening and Sharing Business Central Files in Microsoft OneDrive

[!INCLUDE[prod_short](includes/prod_short.md)] makes it easy to store, manage, and share files with other people through Microsoft OneDrive for Business. On most pages with available files, such as the Report Inbox or when files are attached to records, you'll find **Open in OneDrive** and **Share** actions.


:::image type="content" source="media/onedrive-overview-report-inbox-w-outline.png" alt-text="The Open in OneDrive and Share actions for reports":::


:::image type="content" source="media/one-drive-attachments-w-outline.png" alt-text="The Open in OneDrive and Share actions for attachments":::


## Open in OneDrive

The **Open in OneDrive** action copies the file to your OneDrive and then opens the file in an application such as Microsoft Excel online, Microsoft Word online, or Microsoft PowerPoint online. 

<!--## Working with different types of files-->

When you choose **Open in OneDrive**, [!INCLUDE[prod_short](includes/prod_short.md)] identifies Excel, Word, and PowerPoint files and opens them in their online applications, that is, Excel online, Word online and PowerPoint online. 

Using the online versions of these applications, you can annotate, edit, and collaborate with others without leaving the browser.

For other popular file types, such as PDFs, text files, and images, OneDrive provides file viewers that offer features for printing, sharing, and more. If a file can't be viewed in OneDrive, you might be prompted to download it.

## Share

The **Share** action copies the file to your OneDrive so you can see with whom you've already shared it as well as share the file with other people. When you select the **Share** action, the following page opens.

:::image type="content" source="media/share-to-onedrive-dialog-v2.PNG" alt-text="Share file in OneDrive":::

If you're familiar with OneDrive, you may recognize the above-referenced page. You'll see you have two options for sharing the file: **Send link** and **Copy link**.

- **Send link** let's you share the files with specific people. The people you share the file will get an email with a link to the file. The file will also appear in the **Shared** section of their OneDrive. Start by typing the email addresses or contact names in the **Name, group or email field**. Include a message below the  **Name, group or email field**, if you want.

  > [!TIP]
  > If you want to compose your message in Outlook, select the **Outlook** button. The link will be inserted into a draft email and everyone you entered to share with will be in the **To** list. With this option, you can author emails using all of Outlook's features, including formatting text, adding other attachments, inserting pictures or tables, and adding CC or BCC recipients.

- **Copy link** copies a file link you can use to share the file through applications such as Facebook, Twitter, or email. 

Before you send or copy a file link, set the permission level you want people to have. You can see the current setting under **Send link** or **Copy link**. In most cases, it will be **Anyone with the link can edit**, depending on your administrator's settings. To change the permissions, select the link and make changes on the **Link Settings** page.

The sharing feature in Business Central is based on OneDrive. Learn more about OneDrive sharing and permissions at [Share OneDrive files and folders](https://support.microsoft.com/en-us/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

> [!NOTE]
> The **Share** action isn't available in the Business Central app for mobile devices.

## First-time sign in from Business Central

When you use the **Open in OneDrive** or **Share** action for the first time, [!INCLUDE[prod_short](includes/prod_short.md)] does the following things:

1. Opens the **Please review terms and conditions** page. Read the page, and if you agree with the terms and conditions, select **Agree** to continue.
2. Creates a folder named [!INCLUDE[prod_short](includes/prod_short.md)] in OneDrive. 
3. Within the [!INCLUDE[prod_short](includes/prod_short.md)] folder, it creates a folder with the same name as the company you're working in. If you work in more than one company, [!INCLUDE[prod_short](includes/prod_short.md)] creates a folder for each company you're working in when you use the **Open in OneDrive** or **Share** action. 
4. Puts a copy of the file you selected in the company name folder, and then opens the file. 

Then, the next time you use the **Open in OneDrive** or **Share** action, [!INCLUDE[prod_short](includes/prod_short.md)] only copies and opens the file. 

## Managing multiple copies of a file

When you choose **Open in OneDrive** or **Share**, the file is copied from [!INCLUDE[prod_short](includes/prod_short.md)] to your folder in OneDrive. If you edit the file in OneDrive, that file will be different from the [!INCLUDE[prod_short](includes/prod_short.md)] file. To update [!INCLUDE[prod_short](includes/prod_short.md)] with the latest file version, remove the existing file from [!INCLUDE[prod_short](includes/prod_short.md)] and upload the latest copy.

If a file with the same name already exists in OneDrive, you'll be given the following choices:

- **Use existing**

  This option opens or shares the file that's already stored in OneDrive, instead of copying the file from Business Central.
  
- **Replace**
  
  This option replaces the existing file in OneDrive with the file you selected from Business Central. The original file isn't lost&mdash;you can see and restore it using the version history in OneDrive. Learn more at [Restore a previous version of a file stored in OneDrive](https://support.microsoft.com/office/restore-a-previous-version-of-a-file-stored-in-onedrive-159cad6d-d76e-4981-88ef-de6e96c93893).

- **Keep both**

  This option keeps the existing file as-is and saves the file you selected from Business Central under a different name. The new name is similar to the existing name, except with a suffix number such  “Items (2).xlsx”.

## About your Business Central folder on OneDrive

The folder and its content are private until you decide to share them with others. So you might decide to share content with one or more of your coworkers, or even people outside of your organization. 

You can access your OneDrive from the **My Settings** page by choosing the link in the **Cloud Storage** field. Learn more at [Share OneDrive files and folders](https://support.microsoft.com/en-us/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

:::image type="content" source="media/my-settings-cloud-storage.PNG" alt-text="The Cloud Storage field in My Settings":::

<!--## Extending the Connection to OneDrive
You can create an extension and connect it to... For more information, see...-->

## Related information

[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[OneDrive FAQ](admin-onedrive-faq.md)
