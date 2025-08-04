---
title: Archive sales, purchase, project, and service documents
description: You can archive orders, quotes, return orders, and blanket orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 12/09/2024
ms.custom: bap-template
ms.search.form: 42, 49, 50, 459, 460, 5159, 5162, 5164, 5167, 6627, 6630, 6644, 9305, 9306, 9346, 9347, 9348, 9349
ms.service: dynamics-365-business-central
---
# Archive documents

You can archive sales, purchase, and service orders, quotes, return orders, and blanket orders. If you're using Project Management features, you can also archive your projects. You can archive documents and projects several times. A different archived version saves each time.

For sales documents, if the original still exists and isn't posted, you can use the **Restore** action to overwrite it with an archived version.

> [!NOTE]
> You can only restore sales documents and projects. The action isn't available for archived purchase documents.

For archived documents where the original is deleted, you can reuse the content by copying the data, for example, by using the **Copy from Document** action.  

To explore archived documents, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Archive**, and then choose the related link. If the archive you're interested in doesn't display right away in the **Go to Reports and Analysis** section, you might need to choose **Show more**.

## To set up automatic document archiving

You can automate archiving to create a new version of the archived document when someone does the following things:

* Changes the status or deletes a document or project.
* Prints, downloads, or sends a document by email.
* Converts a quote to an order or invoice.
* Posts an order.

The following steps describe how to set up automatic archiving of sales documents from the **Sales & Receivables Setup** page. The steps are similar for purchase documents and projects.

* For purchase documents, use the **Purchase & Payables** page.
* For projects, use the **Project Setup** page.
* For services, use the **Service Management Setup** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.
2. On the **Archiving** FastTab, specify whether to turn on automatic archiving for the various types of sales documents. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

The following table describes the options for the **Archive Quotes** field.

|Option|Description|
|------|-----------|
|**Never**| Don't archive sales quotes when they're deleted.|
|**Question**|Prompt the user to choose whether to archive sales quotes when they're deleted.|
|**Always**|Archive a sales quote automatically when you delete it.|

## To manually archive a sales order

The following procedure describes how to manually archive a sales order. The steps are similar for all documents and projects that you can archive.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Open a sales order that you want to archive.  
3. Choose the **Archive Document** action.

The sales order is archived. You can view it on the **Archived Sales Orders** page.

## To restore a nonposted sales document or a project from the archive

You can restore documents only if the original document isn't posted.

The following procedure describes how to restore an archived sales order to the original sales order. The steps are similar for all orders, blanket orders, return orders, and quotes.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order Archives**, and then choose the related link.
2. Select the archived sales order, or version of it, that you want to restore, and then choose the **Restore** action.  

The contents of the original sales order or project are replaced with the archived version.

## To delete archived versions

Use a retention policy to clean up archived versions that you no longer need. Retention policies let administrators define how long they want to store data. For example, they can set up a policy that deletes data after an expiration date. To learn more, go to [Define Retention Policies](admin-data-retention-policies.md).

There are a few things to note about creating retention policies for archived documents and projects:

* If the original document isn’t deleted, [!INCLUDE [prod_short](includes/prod_short.md)] you can’t delete the archived versions. Archived versions don’t expire as long as the original exists.
* When you set up the retention policy, you can specify that you want the policy to delete all archived versions except the most recent. For example, you might have 10 versions and want to keep a copy of the latest. 
* [!INCLUDE [prod_short](includes/prod_short.md)] calculates the expiration date for documents based on the date of the most recent archived version.

## Related information

[Track Document Lines](across-how-to-track-document-lines.md)  
[Sales](sales-manage-sales.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
