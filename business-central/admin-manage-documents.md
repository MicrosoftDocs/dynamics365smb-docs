---
title: Manage storage by deleting documents or compressing data
description: Learn how to deal with accumulating historic documents (and reduce the amount of data stored in a database) by deleting or compressing them.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 107, 9035, 9040
ms.date: 09/03/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Manage storage by deleting documents or compressing data

A central role, such as the application administrator, must regularly clean up data storage by deleting or compressing historic documents, media files, various types of entries, and so on. This article describes some built-in tools that make it easier for admins to manage unneeded data.  

> [!TIP]
> Learn more about other ways to reduce the amount of data stored in a database by reading [Reducing Data Stored in Business Central Databases](/dynamics365/business-central/dev-itpro/administration/database-reduce-data) in our Developer and IT pro documentation.

## Clean up data

The **Data Administration** page provides batch jobs and worksheets for deleting obsolete data. To open the page, choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Data Administration**, and then choose the related link. On the **Actions** menu, choose **Data Cleanup**, and then choose an action from one of the following categories.

> [!IMPORTANT]
> Review the filters on the request page before you run a deletion batch job. Some batch jobs don't ask you to confirm the deletion, and blank filters might include all eligible records. Deleted data can't be recovered.

The actions that are available depend on the features that your company uses.

### Document archives

The following action deletes sales quotes that are no longer valid.

|Action|Description|
|---|---|
|**Delete Expired Sales Quotes**|Deletes sales quotes that have a **Quote Valid Until Date** earlier than the date that you specify. You can filter the quotes by number and sell-to customer.|

### Invoiced documents

The following actions delete open documents that remain after they're fully processed. They don't delete the posted documents that provide the transaction history.

|Action|Description|
|---|---|
|**Delete Blanket Sales Orders**|Deletes blanket sales orders that have invoiced lines and no outstanding quantities, shipped quantities that aren't invoiced, or remaining sales lines that refer to the blanket order.|
|**Delete Sales Orders**|Deletes fully shipped and invoiced sales orders. Item charge assignments that aren't fully invoiced can prevent the complete order from being deleted.|
|**Delete Sales Return Orders**|Deletes fully received and invoiced sales return orders. Item charge assignments that aren't fully invoiced can prevent the complete return order from being deleted.|
|**Delete Blanket Purchase Orders**|Deletes blanket purchase orders that have invoiced lines and no outstanding quantities, received quantities that aren't invoiced, or remaining purchase lines that refer to the blanket order.|
|**Delete Purchase Orders**|Deletes fully received and invoiced purchase orders. The order isn't deleted if an item charge assignment isn't fully invoiced.|
|**Delete Purchase Return Orders**|Deletes fully shipped and invoiced purchase return orders. Item charge assignments that aren't fully invoiced can prevent the complete return order from being deleted.|
|**Delete Service Orders**|Deletes fully shipped and invoiced service orders. This action is available when you use Service Management. It doesn't delete posted service documents.|
|**Delete Registered Warehouse Documents**|Deletes registered warehouse activity documents, including their lines and comments, according to the type and number filters that you specify. The batch job doesn't require the documents to be older than a specific date.|

### Marketing

The following actions delete obsolete relationship management records and, where applicable, their related records.

|Action|Description|
|---|---|
|**Delete Campaign Entries**|Deletes canceled campaign entries according to the campaign, date, salesperson, and entry number filters that you specify. Related interaction log entries are also deleted.|
|**Delete Logged Segments**|Deletes canceled logged segments according to the entry number and segment number filters that you specify. Retains related interaction and campaign entries, but removes their links to the logged segment.|
|**Delete Opportunities**|Deletes closed opportunities according to the filters that you specify. Also deletes related opportunity entries and comments.|
|**Delete Tasks**|Deletes canceled relationship management tasks. Also deletes related comments, attendees, and subordinate attendee or member tasks.|
|**Delete Interaction Log Entries**|Deletes canceled interaction log entries according to the filters that you specify. Also deletes related comments, campaign target links, and attachments that aren't used by other interactions.|

### Cost accounting

The following actions delete cost accounting entries by register or posting date.

|Action|Description|
|---|---|
|**Delete Cost Budget Entries**|Deletes a range of open cost budget registers and the entries in those registers. You can't delete closed registers. If you delete allocation registers, [!INCLUDE [prod_short](includes/prod_short.md)] resets the allocation status of the affected entries.|
|**Delete Cost Entries**|Deletes a range of open cost registers and the entries in those registers. You can't delete closed registers, and the range must end with the latest cost register. If you delete allocation registers, [!INCLUDE [prod_short](includes/prod_short.md)] resets the allocation status of the affected entries.|
|**Delete Old Cost Entries**|Deletes cost entries with posting dates up to and including the specified year-ending date. The date must be the end of a calendar year and at least one year before the work date. This action doesn't delete the related cost registers.|

### Miscellaneous

The following actions clean up inventory, media, guided experiences, service, and manufacturing data.

|Action|Description|
|---|---|
|**Delete Phys. Inventory Ledger**|Deletes physical inventory ledger entries in the date range and for the item and inventory posting group filters that you specify. You must provide an ending date, and [!INCLUDE [prod_short](includes/prod_short.md)] validates the entries against closed inventory periods.|
|**Delete Detached media**|Opens a page where you can find and delete media that isn't referenced by a record. Before deleting selected media, [!INCLUDE [prod_short](includes/prod_short.md)] reverifies that the media is still detached. You can also schedule cleanup of detached media and media sets.|
|**Delete Duplicated Guided Experience Item**|Opens a page that finds guided experience item codes with more than 100 versions. For a selected code, the cleanup deletes older versions and keeps the version with the highest version number.|
|**Delete Service Email Queue**|Deletes service email queue entries according to the status and sending date filters that you specify. Without filters, the batch job deletes the entire queue. This action is available when you use Service Management.|
|**Delete Service Document Log**|Deletes service document log entries according to the change date, document type, and document number filters that you specify. You can limit the deletion to logs for documents that no longer exist. This action is available when you use Service Management.|
|**Delete Service Item Log**|Deletes service item log entries according to the change date and service item number filters that you specify. This action is available when you use Service Management.|
|**Delete Expired Components**|Deletes production BOM lines with an ending date earlier than the date that you specify, but doesn't delete production BOM headers. This action is available when you use Manufacturing.|

## Compress data with date compression

You can compress data in [!INCLUDE [prod_short](includes/prod_short.md)] to save space in the database&mdash;which in [!INCLUDE [prod_short](includes/prod_short.md)] online can even save you money. The compression, based on dates and functions, combines several old entries into one new entry.

You can compress entries that meet all of the following conditions:

* They're from closed fiscal years.
* The **Open** field is set to **No**.
* They're at least five years old. If you want to compress data less than five years old, contact your Microsoft partner.

So, for example, vendor ledger entries from previous fiscal years can be compressed so there's only one credit and one debit entry per account per month. The amount in the new entry is the sum of all the compressed entries. The date assigned is the starting date for the compressed period, such as the first day of the month (if you compress entries by month). After compression, you can still see the net change for each account in the previous fiscal year.

The number of entries that result from a date compression depends on how many filters you set, which fields are combined, and which period length you choose. There's always at least one entry. When the batch job is finished, you can see the result on the **Date Compr. Registers** page.

You can compress the following data types using batch jobs.

* Finance entries - general ledger (G/L) entries, value added tax (VAT) entries, bank account ledger entries, G/L budget entries, customer ledger entries, and vendor ledger entries.
* Warehouse entries
* Resource entries
* Item budget entries
* Fixed asset (FA) ledger entries, FA maintenance ledger entries, and FA insurance ledger entries.

When you're defining criteria for the compression, you can keep the contents of certain fields using the options under **Retain Field Contents**. The available fields depend on the data you're compressing.

> [!NOTE]
> Before you can run date compression, your analysis views must be current. Learn more in the [Update an analysis view](bi-how-analyze-data-dimension.md#update-an-analysis-view) section.

After the compression, the contents of the following fields are always retained: **Posting Date**, **Vendor No.**, **Document Type**, **Currency Code**, **Posting Group**, **Amount**, **Remaining Amount**, **Original Amt. (LCY)**, **Remaining Amt. (LCY)**, **Amount (LCY)**, **Purchase (LCY)**, **Inv. Discount (LCY)**, **Pmt. Disc. Given (LCY)**, and **Pmt. Disc. Possible**.

## Posting compressed entries

Compressed entries are posted a little differently than standard posting. This difference is to reduce the number of new general ledger entries created by date compression, and is especially important when you keep information such as dimensions and document numbers. Date compression creates new entries as follows:

* On the **General Ledger Entries** page, new entries are created for the compressed entries. The **Description** field contains **Date Compressed** so the compressed entries are easy to identify. 
* On ledger pages, such as the **Customer Ledger Entries** page, one or more new entries are created.

The posting process creates gaps in the number series for entries on the **General Ledger Entries** page. You assign those numbers to the entries on the ledger pages only. You can view the number range assigned to the entries on the **G/L Register** page in the **From Entry No.** and **To Entry No.** fields. 

> [!NOTE]
> After you run date compression, you can't reverse vendor or bank ledger entries for any transactions that are affected by the compression.

The number of entries that result from a date compression depends on how many filters you set, which fields are combined, and the length of the time period you choose. There's always at least one entry.

> [!WARNING]
> Date compression deletes entries, so you should always make a backup copy of the database before you run the batch job.

### To run a date compression

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Data Administration**, then choose the related link.
2. Do one of the following, depending on your needs:
    * To use an assisted guide to set up date compression for one or more types of data, choose **Data Administration Guide**.
    * To set up compression for an individual type of data, choose **Data Compression**, **Compress Entries**, then choose the data to compress.

   > [!NOTE]
   > You can only compress data more than five years old. If you want to compress data less than five years old, contact your Microsoft partner. They need to use the `OnSetMinimumNumberOfYearsToKeep` event in the "Date Compression" codeunit to set the threshold.


## Related information

[Administration](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
