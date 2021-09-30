---
    title: Business Central and OneDrive for Business Integration
    description: You can use OneDrive for Business to store, manage, and share files, such as reports or file attachments. 
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/11/2021
    ms.author: bholtorf

---

# Business Central and OneDrive for Business Integration
OneDrive for Business is a cloud storage service that is included in Microsoft 365. [!INCLUDE[prod_short](includes/prod_short.md)] makes it easy to store, manage, and share files with other people through OneDrive. When a file is in your OneDrive you can enjoy the rich collaborative experiences from the online versions of Microsoft products, such as Word, Excel, and PowerPoint. For example, you can share a Word document, and then you and your colleagues can edit it together in real-time. OneDrive also lets you open other types of files, such as PDFs. 

## Getting Started
We've created the connection between [!INCLUDE[prod_short](includes/prod_short.md)] online and OneDrive, so it's easy to get started. The only requirement is that users have opened OneDrive at least one time. 

On most pages where files are available, such as the Report Inbox or files that are attached to records, you'll find an **Open in OneDrive** action.

:::image type="content" source="media/Open in OneDrive.PNG" alt-text="The Open in OneDrive action":::

 
:::image type="content" source="media/OneDrive attachment.PNG" alt-text="Share file attachments in OneDrive":::

When you use the **Open in OneDrive** action for the first time, [!INCLUDE[prod_short](includes/prod_short.md)] does the following in your OneDrive:

1. Creates a folder named [!INCLUDE[prod_short](includes/prod_short.md)]. 
2. In the [!INCLUDE[prod_short](includes/prod_short.md)] folder, it creates another folder with the same name as the company you're working in. If you work in more than one company, it will create a folder for the company you're working in when you use the **Open in OneDrive** action. 
3. Puts a copy of the file you selected in the folder, and then opens the file. The next time you use the action, it only copies and opens the file. 

The folder and its content are private until you decide to share them with others. For example, you might decide to share content with one or more of your coworkers, or even people outside of your organization. For more information, see [Share OneDrive files and folders](https://support.microsoft.com/en-us/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

> [!NOTE]
> You can also connect your [!INCLUDE[prod_short](includes/prod_short.md)] on-premises to OneDrive. However, there are a few things to do to make it work. For more information, see [Configuring Business Central On-Premises](admin-onedrive-integration.md#configuring-business-central-on-premises).

## See Also
[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[Opening Business Central Files in OneDrive](across-share-onedrive.md)  
[OneDrive FAQ](admin-onedrive-faq.md)