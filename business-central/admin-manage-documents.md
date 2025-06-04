---
title: Manage storage by deleting documents or compressing data
description: Learn how to deal with accumulating historic documents (and reduce the amount of data stored in a database) by deleting or compressing them.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 107, 9035, 9040
ms.date: 04/16/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Manage storage by deleting documents or compressing data

A central role, such as the application administrator, must regularly deal with accumulating historic documents by deleting or compressing them.  

> [!TIP]
> Learn more about other ways to reduce the amount of data stored in a database by reading [Reducing Data Stored in Business Central Databases](/dynamics365/business-central/dev-itpro/administration/database-reduce-data) in our Developer and IT pro documentation.

## Delete documents

In certain situations, you might need to delete invoiced purchase orders. However, you can't delete them unless you fully invoice and received the items in the purchase orders. [!INCLUDE[prod_short](includes/prod_short.md)] helps you out by checking for that.

Businesses usually delete return orders after they're invoiced. When you post an invoice, [!INCLUDE [prod_short](includes/prod_short.md)] transfers it to the **Posted Purchase Credit Memo** page. If you selected the **Return Shipment on Credit Memo** check box on the **Purchases & Payable Setup** page, the invoice is transferred to the **Posted Return Shipment** page. You can delete the documents using the **Delete Invd Purch. Ret. Orders** batch job. Before it deletes documents, the batch job checks whether the purchase return orders are fully shipped and invoiced.  

Blanket purchase orders aren't automatically deleted after you process and invoice all the related purchase orders. Instead, you can delete them with the **Delete Invoiced Blanket Purchase Orders** batch job.  

Businesses typically delete invoiced service orders automatically after they're fully invoiced. When an invoice is posted, a corresponding entry is created and can then be viewed on the **Posted Service Invoices** page.  

Service orders aren't deleted automatically, however, if the total quantity on the order was posted from the **Service Invoice** page rather than from service order itself. You might need to manually delete such invoiced orders by running the **Delete Invoiced Service Orders** batch job.  

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

The posting process creates gaps in the number series for entries on the **General Ledger Entries** page. Those numbers are assigned to the entries on the ledger pages only. The number range assigned to the entries is available on the **G/L Register** page in the **From Entry No.** and **To Entry No.** fields. 

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
