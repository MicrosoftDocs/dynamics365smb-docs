---
title: Store document attachments in external file storage
description: Learn how you can store attachments. 
author: brentholtorf
ms.topic: how-to
ms.search.keywords: open files, share files, OneDrive
ms.date: 03/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Store document attachments in external file storage

[!INCLUDE [prod_short](includes/prod_short.md)] lets you store document attachments, such as PDFs, images, and scanned documents, outside the [!INCLUDE [prod_short](includes/prod_short.md)] database. For example, in external file storage such as Microsoft Azure or SharePoint. By offloading attachments to a connected external storage service, you can significantly reduce your database size and avoid reaching storage limits. You can access attachments in [!INCLUDE [prod_short](includes/prod_short.md)], but the files are in your external storage account.

Keeping attachments in external storage can help you:

* Stay within capacity limits. Each [!INCLUDE [prod_short](includes/prod_short.md)] tenant has a limited database capacity. For example, 80 GB by default for production and sandbox environments, plus per-license extra storage. Offloading attachments helps keep your database within these limits, preventing the need to purchase extra capacity.
* Improve performance and backups. A smaller database can improve overall system performance and reduce backup and restoration times.
* Use inexpensive storage. External cloud storage such as Azure Blob Storage or SharePoint is typically more cost-effective for large file storage and can provide other features like sharing, content management, and long-term archiving.

## Supported external storage providers

Out of the box, [!INCLUDE [prod_short](includes/prod_short.md)] supports Azure cloud storage and Microsoft 365 services for external attachments. You can connect to Azure Blob Storage, Azure File Share, or SharePoint document libraries. The External File Storage framework is extensible, so partners or developers can add other storage providers (for example, SFTP or OneDrive) via extension if needed.

> [!IMPORTANT]  
> You're responsible for your data management. When you enable external storage for attachments, files are no longer stored in the [!INCLUDE [prod_short](includes/prod_short.md)] database. Instead, they reside in your external storage. This means Microsoft doesn't back up or manage those files as part of your [!INCLUDE [prod_short](includes/prod_short.md)] environment. You, or your system administrator, are responsible for setting up appropriate backups and access control on the external storage. If a file is deleted or becomes unavailable in the external storage, it's no longer be accessible from [!INCLUDE [prod_short](includes/prod_short.md)].

## Set up an external file storage account

Before you can offload attachments, you must create one or more external file accounts in [!INCLUDE [prod_short](includes/prod_short.md)] for the storage services you plan to use. An external file account stores the connection details, such as credentials and endpoints, for your Azure or SharePoint storage. You can set up multiple external file accounts. For example, one for Azure Blob Storage and another for SharePoint.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **External File Accounts**, and choose the related link.
1. Choose the **Add a file account** action to start a setup guide that helps you enter details for your external storage connection. 
1. Select the type of storage you want to connect (for example, **Azure Blob Storage**, **Azure File Share**, or **SharePoint**), and then choose **Next**.
1. Enter the required connection details. The details depend on the storage type you selected.

    * **Azure Blob Storage account:** Enter an **Account Name**, which is a friendly name for use in [!INCLUDE [prod_short](includes/prod_short.md)], and the **Storage Account Name** of your Azure storage account. Select the **Authorization Type**, either a Shared Access Signature (SAS) token or a shared account key. Paste the SAS token or access key in the **Secret** field. Specify the **Container Name** where you store attachments in your blob storage account.
    * **Azure File Share account:** Enter an **Account Name** and the **Storage Account Name**. Choose the authentication method (SAS token or key) and provide the **Secret** value. Enter the **File Share Name** for the Azure Files share where you store attachments.
    * **SharePoint storage account:** Enter an **Account Name** for [!INCLUDE [prod_short](includes/prod_short.md)], and then provide the **Tenant ID**, **Client ID**, and **Client Secret** of your Microsoft Entra ID app registration that can access to your SharePoint site. Specify the **SharePoint Name**, which is the domain or site name (for example, the SharePoint site collection or tenant name), and a **Base Relative Folder Path** where you want to store attachments. For example, the document library and folder path within the site. 
    
    > [!TIP]
    > The base folder path should start from the site root, such as `Shared Documents/Attachments`, in a SharePoint document library URL.

1. Choose **Next**.
1. Review the information, and choose **Finish**. [!INCLUDE [prod_short](includes/prod_short.md)] saves the new external file account. You can repeat these steps to add multiple storage accounts if needed. For example, if you want to connect to both an Azure storage and a SharePoint library. The **External File Accounts** page lists all configured accounts.

At this point, you're connected to your external storage. Next, enable document attachment features to use one of your external file accounts to store attachments.

## Enable external storage for document attachments

After you set up a file account for external storage, the next step is to assign the document attachments scenario to it. This step tells [!INCLUDE [prod_short](includes/prod_short.md)] to offload attachments to the storage instead of the database.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **File Scenario Assignment**, and choose the related link.
1. Choose the **Assign scenarios** action. The **Assign scenarios to account** page opens, listing available file accounts and their assigned scenarios. Locate the file account you would like to assign the scenario to, and choose **OK**.
1. To assign a document attachments scenario to storage account, select the file account line, and then choose **Assign Scenarios** or **Edit**. Select the **Document Attachments - External Storage** file scenario. Confirm that you want to configure storage for document attachments.
1. After you confirm, the **External Storage Setup** page opens. Set up how to offload attachments:

    * Turn on the **Enabled** toggle for the Document Attachments scenario. This setting confirms that [!INCLUDE [prod_short](includes/prod_short.md)] offloads attachments to the specified storage. [!INCLUDE [prod_short](includes/prod_short.md)] displays a warning that using external storage is at your own risk and that you're responsible for managing and backing up the files. Read the warning, and then choose **Yes** to proceed. The **Document Attachments** scenario is now active.
    * In the **Root folder** field, choose a folder in your external storage where you store attachments for this [!INCLUDE [prod_short](includes/prod_short.md)] environment. You can only select an existing container/folder. [!INCLUDE [prod_short](includes/prod_short.md)] automatically organizes subfolders in this root using a structured hierarchy of environment, company, table, and so on, to group files by their source record type. For example, it stores attachments for records in the **Sales Header** table (sales orders, and so on) in a **Sales Header** folder in your storage.
    * To specify whether to delete an attachment record in your external storage when someone deletes the record in [!INCLUDE [prod_short](includes/prod_short.md)], turn on the **Delete External File on Attachment Delete** toggle. If you disable this option, deleting an attachment in [!INCLUDE [prod_short](includes/prod_short.md)] removes the link in [!INCLUDE [prod_short](includes/prod_short.md)], but the file remains in external storage until you manually remove it.

1. Review your settings, and then choose **Close** to complete the scenario setup. The Document Attachments feature is now linked to your external storage account. From this point on, new attachments you add to records in [!INCLUDE [prod_short](includes/prod_short.md)] are stored in the external location instead of the [!INCLUDE [prod_short](includes/prod_short.md)] database.

    > [!NOTE]  
    > Only attachments people add after you enable this feature are kept in your external storage. To move existing attachments from your [!INCLUDE [prod_short](includes/prod_short.md)] database to external storage, go to the **File Scenarios** or **External Storage Setup** pages and use the **Storage Sync** action. You can specify the direction you want to move files, and the operation to do so.
    >
    > You can also use the action if you need to stop using external storage and revert to storing attachments in the [!INCLUDE [prod_short](includes/prod_short.md)] database. The action can move all files back into the database from the external storage. Afterward, you can turn off external storage.

## Work with attachments after you offload them

Document attachment features don't change for users after you enable external file storage. You still manage attachments using the **Attachments** FactBox on records, or the **Document Attachments** page, as usual. The difference is behind the scenes. When you attach a file, [!INCLUDE [prod_short](includes/prod_short.md)] uploads it to your external storage. When you view or download an attachment, [!INCLUDE [prod_short](includes/prod_short.md)] retrieves it from external storage automatically.

## Attach a file to a record when external storage is enabled 

You attach files to records using the **Attachments** tab on the FactBox, or the **Attachments** action on the **Lines** FastTab for line-level attachments in the same way as with standard attachments. For example, on the **Sales Order** page, you can drag and drop a file onto the **Attachments** FactBox, or choose the **Attach file** action and select a file from your device. The file appears in the **Documents** section of the FactBox, showing its name and size.

* If you configure external storage for attachments, [!INCLUDE [prod_short](includes/prod_short.md)] immediately transfers the file to the external file account you set up.
* [!INCLUDE [prod_short](includes/prod_short.md)] ensures that each file name is unique in the external storage by appending a unique ID to the file name. The ID prevents different records with the same original file name from overwriting each other in a flat storage container. For example, it gives two different invoices named *invoice.pdf* distinct names in the external storage. The attachment’s title in [!INCLUDE [prod_short](includes/prod_short.md)] remains the original file name without the unique ID, but the file in external storage has the ID.

## View or download an attached file

To open or save an attachment, select it from the **Attachments** FactBox or **Document Attachments** page, and choose **Open** or **Download**. [!INCLUDE [prod_short](includes/prod_short.md)] gets the file from the external storage and you can open it in your browser or download it to your device. 

> [!NOTE]
> If the file doesn't exist in the external storage, for example, because you deleted it, an error displays because the link is broken in [!INCLUDE [prod_short](includes/prod_short.md)].

## Delete an attached file

To remove an attachment, use the **Delete** action on the record from the FactBox or **Document Attachments** list. [!INCLUDE [prod_short](includes/prod_short.md)] deletes the attachment record from its database. If you enabled the option to also delete external files, [!INCLUDE [prod_short](includes/prod_short.md)] sends a request to remove the file from the external storage as well. If that option is off, the file remains in external storage but is no longer linked to a record in [!INCLUDE [prod_short](includes/prod_short.md)].

## Move or copy records

If you use features like **Copy Company** or environment backup/restore, keep in mind that attachments you store externally aren't automatically copied. The attachment records (metadata) might be copied, but they still point to files in the original external storage location unless you migrate those files manually. To do so, go to the **External Storage Setup** page, and run the **Migrate Files** action. This report migrates all document attachments from a previous environment or company folder to the current environment/company folder in external storage.

> [!NOTE]  
> You can browse and manage your external file storage from within [!INCLUDE [prod_short](includes/prod_short.md)]. On the **External File Accounts** page, select your storage account, and choose the **Storage Browser** action to open the **External Storage Browser** page. This page displays the folders and files in your connected storage. It shows all files in a selected Azure blob container, and allows you to upload, download, or delete files. You can also create new folders in the external storage. This page can be useful for verifying that files are saving as expected, or for manually managing external documents.

## Related information

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Administration](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]