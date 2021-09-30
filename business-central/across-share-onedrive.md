---
    title: Using OneDrive for Business with Business Central
    description: You can use OneDrive for Business to store, manage, and share files, such as reports or file attachments. 
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/11/2021
    ms.author: bholtorf

---
# Opening Business Central Files in OneDrive
[!INCLUDE[prod_short](includes/prod_short.md)] makes it easy to store, manage, and share files with other people through OneDrive for Business. On most pages where files are available, such as the Report Inbox or files that are attached to records, you'll find an **Open in OneDrive** action.

:::image type="content" source="media/Open in OneDrive.PNG" alt-text="The Open in OneDrive action":::

 
:::image type="content" source="media/OneDrive attachment.PNG" alt-text="Share file attachments in OneDrive":::

## Working with Different Types of Files
When you choose **Open in OneDrive**, [!INCLUDE[prod_short](includes/prod_short.md)] identifies Excel, Word, and PowerPoint files and opens them in their online applications, that is, Excel online, Word online and PowerPoint online. You can annotate, edit, and collaborate with others without leaving the browser. 

For other popular file types, such as PDFs, text files, and images, OneDrive provides file viewers that offer features for printing, sharing, and more. If a file cannot be viewed in OneDrive, you might be prompted to download it. 

## Managing Multiple Copies of a File
When you choose **Open in OneDrive**, the file is copied from [!INCLUDE[prod_short](includes/prod_short.md)] to your folder in OneDrive. If you edit the file in OneDrive, the copies of the file will be different. To update [!INCLUDE[prod_short](includes/prod_short.md)] with the latest file, remove the existing file from [!INCLUDE[prod_short](includes/prod_short.md)] and then upload the latest copy.

Additionally, when you use the Open in OneDrive action and a file with that name already exists in OneDrive, [!INCLUDE[prod_short](includes/prod_short.md)] will provide a choice to either replace the file or keep both files. If you choose to keep both files, the new file is copied to OneDrive and its file name is given a suffix, such as “Items (2).xlsx,” and the original file is not changed. 

If you choose to replace the file, the new file is added to the version history for that file. The original file isn't lost, and you can view or restore previous versions of the file. 

## Accessing Your OneDrive
You can access your OneDrive from the **My Settings** page by choosing the link in the **Cloud Storage** field.

:::image type="content" source="media/my-settings-cloud-storage.PNG" alt-text="The Cloud Storage field in My Settings":::

<!--## Extending the Connection to OneDrive
You can create an extension and connect it to... For more information, see...-->

## See Also
[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[OneDrive FAQ](admin-onedrive-faq.md)