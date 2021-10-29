---
title: Manage storage by deleting documents or compressing data
description: Learn how to deal with accumulating historic documents (and reduce the amount of data stored in a database) by deleting or compressing them.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 06/14/2021
ms.author: edupont

---
# Manage Storage by Deleting Documents or Compressing Data

A central role, such as the application administrator, must regularly deal with accumulating historic documents by deleting or compressing them.  

> [!TIP]
> For information about other ways to reduce the amount of data stored in a database, see [Reducing Data Stored in Business Central Databases](/dynamics365/business-central/dev-itpro/administration/database-reduce-data) in our Developer and IT pro documentation.

## Delete Documents

In certain situations, you may need to delete invoiced purchase orders that have not been deleted. [!INCLUDE[prod_short](includes/prod_short.md)] checks that you have fully invoiced the deleted purchase orders. You cannot delete orders that you have not fully invoiced and received.  

Return orders are usually deleted after they are invoiced. When you post an invoice, it is transferred to the **Posted Purchase Credit Memo** page. If you selected the **Return Shipment on Credit Memo** check box on the **Purchases & Payable Setup** page, then the invoice is transferred to the **Posted Return Shipment** page. You can delete the documents using the **Delete Invd Purch. Ret. Orders** batch job. Before deleting, the batch job checks if the purchase return orders are fully shipped and invoiced.  

Blanket purchase orders are not deleted after you have processed and invoiced all the related purchase orders. You can delete blanket orders with the **Delete Invoiced Blanket Purchase Orders** batch job.  

Invoiced service orders are usually deleted automatically after having been fully invoiced. When an invoice is posted, a corresponding entry is created on the **Posted Service Invoices** page. The posted document can be viewed on the **Posted Service Invoice** page.  

Service orders are not deleted automatically, however, if the total quantity on the order has been posted not from the service order itself, but from the **Service Invoice** page. Then you may need to delete invoiced orders that were not deleted. You can do this by running the **Delete Invoiced Service Orders** batch job.  

## Compress Data with Date Compression

You can compress data in [!INCLUDE [prod_short](includes/prod_short.md)] to save space in the database, which in [!INCLUDE [prod_short](includes/prod_short.md)] online can even save you money. The compression is based on dates and works by combining several old entries into one new entry. 

You can compress entries under the following conditions:

* They're from closed fiscal years
* The **Open** field is set to **No** 
* They're at least five years old. If you want to compress data that is less than five years old, contact your Microsoft partner.

For example, vendor ledger entries from previous fiscal years can be compressed so that there is only one credit and one debit entry per account per month. The amount in the new entry is the sum of all the compressed entries. The date assigned is the starting date for the period that is compressed, such as the first day of the month (if the entries are compressed by month). After the compression, you can still see the net change for each account in the previous fiscal year.

The number of entries that result from a date compression depends on how many filters you set, which fields are combined, and which period length you choose. There will always be at least one entry. When the batch job is finished, you can see the result in the **Date Compr. Registers** page.

You can compress the following types of data using batch jobs. There is a batch job for each type of data.

* Finance entries - G/L entries, VAT entries, bank account ledger entries, G/L budget entries, customer ledger entries, vendor ledger entries.
* Warehouse entries 
* Resource entries
* Item budget entries
* Fixed asset - Fixed asset ledger entries, FA maintenance ledger entries, FA insurance ledger entries.

When you are defining criteria for the compression, you can use the options under **Retain Field Contents** to keep the contents of certain fields. The fields that are available depend on the data that you are compressing.

> [!NOTE]
> Before you can run date compression, your analysis views must be up to date. For more information, see [To update an analysis view](bi-how-analyze-data-dimension.md#to-update-an-analysis-view).

After the compression, the contents of the following fields are always retained: **Posting Date**, **Vendor No.**, **Document Type**, **Currency Code**, **Posting Group**, **Amount**, **Remaining Amount**, **Original Amt. (LCY)**, **Remaining Amt. (LCY)**, **Amount (LCY)**, **Purchase (LCY)**, **Inv. Discount (LCY)**, **Pmt. Disc. Given (LCY)**, and **Pmt. Disc. Possible**.

## Posting Compressed Entries
Compressed entries are posted slightly differently than standard posting. This is to reduce the number of new general ledger entries created by date compression, and is especially important when you keep information such as dimensions and document numbers. Date compression creates new entries as follows:
* On the **General Ledger Entries** page, new entries are created with new entry numbers for the compressed entries. The **Description** field contains **Date Compressed** so that the compressed entries are easy to identify. 
* On ledger pages, such as the **Customer Ledger Entries** page, one or more entries are created with new entry numbers. 

The posting process creates gaps in the number series for entries on the **General Ledger Entries** page. Those numbers are assigned to the entries on the ledger pages only. The number range that was assigned to the entries is available on the **G/L Register page**  in the **From Entry No.** and **To Entry No.** fields. 

> [!NOTE]
> After you run date compression, all accounts in the ledger are locked. For example, you cannot un-apply vendor or bank ledger entries for any accounts during the period for which dates are compressed.

The number of entries that result from a date compression depends on how many filters you set, which fields are combined, and which period length you choose. There will always be at least one entry. 

> [!WARNING]
> Date compression deletes entries, so you should always make a backup copy of the database before you run the batch job.

### To run a date compression
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Data Administration**, and then choose the related link.
2. Do one of the following:
    * To use an assisted setup guide to set up date compression for one or more types of data, choose **Data Administration Guide**.
    * To set up compression for an individual type of data, choose **Date Compression**, **Compress Entries**, and then choose the data to compress.

   > [!NOTE]
   > You can only compress data that is more than five years old. If you want to compress data that is less than five years old, contact your Microsoft partner.

## See Also

[Administration](admin-setup-and-administration.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]