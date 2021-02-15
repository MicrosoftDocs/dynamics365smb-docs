---
title: Manage storage by deleting documents or compressing data
description: Learn how you can keep your historical data by compressing ledger entries, or delete it.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 10/01/2020
ms.author: edupont

---
# Manage Storage by Deleting Documents or Compressing Data

A central role, such as the application administrator, must regularly deal with accumulating historic documents by deleting or compressing them.  

> [!TIP]
> For information about other ways to reduce the amount of data stored in a database, see [Reducing Data Stored in Business Central Databases](/dynamics365/business-central/dev-itpro/administration/database-reduce-data) in the Developer and IT pro help.

## Delete Documents

In certain situations, you may need to delete invoiced purchase orders that have not been deleted. [!INCLUDE[prod_short](includes/prod_short.md)] checks that you have fully invoiced the deleted purchase orders. You cannot delete orders that you have not fully invoiced and received.  

Return orders are usually deleted after they are invoiced. When you post an invoice, it is transferred to the **Posted Purchase Credit Memo** page. If you selected the **Return Shipment on Credit Memo** check box on the **Purchases & Payable Setup** page, then the invoice is transferred to the **Posted Return Shipment** page. You can delete the documents using the **Delete Invd Purch. Ret. Orders** batch job. Before deleting, the batch job checks if the purchase return orders are fully shipped and invoiced.  

Blanket purchase orders are not deleted after you have processed and invoiced all the related purchase orders. You can delete blanket orders with the **Delete Invoiced Blanket Purchase Orders** batch job.  

Invoiced service orders are usually deleted automatically after having been fully invoiced. When an invoice is posted, a corresponding entry is created on the **Posted Service Invoices** page. The posted document can be viewed on the **Posted Service Invoice** page.  

Service orders are not deleted automatically, however, if the total quantity on the order has been posted not from the service order itself, but from the **Service Invoice** page. Then you may need to delete invoiced orders that were not deleted. You can do this by running the **Delete Invoiced Service Orders** batch job.  

## Compress Data with Date Compression

You can compress data in [!INCLUDE [prod_short](includes/prod_short.md)] so that you save space in the database, which in [!INCLUDE [prod_short](includes/prod_short.md)] online can even save you money. The compression is based on dates and works by combining several old entries into one new entry. You can compress entries from closed fiscal years only, and only vendor ledger entries where the **Open** field is set to *No*.  

For example, vendor ledger entries from previous fiscal years can be compressed so that there is only one credit and one debit entry per account per month. The amount in the new entry is the sum of all the compressed entries. The date assigned is the starting date for the period that is compressed, such as the first day of the month (if the entries are compressed by month). After the compression, you can still see the net change for each account in the previous fiscal year.

The number of entries that result from a date compression depends on how many filters you set, which fields are combined, and which period length you choose. There will always be at least one entry. When the batch job is finished, you can see the result in the **Date Compr. Registers** page.

You can compress the following types of data in [!INCLUDE [prod_short](includes/prod_short.md)] using batch jobs:

* Bank account ledger entries

  After the compression, with the **Retain Field Contents** facility, you can retain the contents of the **Document No., Our Contact**, **Global Dimension 1 Code**, and **Global Dimension 2 Code** fields.
* Vendor ledger entries

  After the compression, the contents of the following fields are always retained: **Posting Date**, **Vendor No.**, **Document Type**, **Currency Code**, **Posting Group**, **Amount**, **Remaining Amount**, **Original Amt. (LCY)**, **Remaining Amt. (LCY)**, **Amount (LCY)**, **Purchase (LCY)**, **Inv. Discount (LCY)**, **Pmt. Disc. Given (LCY)**, and **Pmt. Disc. Possible**.

  With the **Retain Field Contents** facility, you can also retain the contents of these additional fields: **Document No.**, **Buy-from Vendor No.**, **Purchaser Code**, **Global Dimension 1 Code**, and **Global Dimension 2 Code**.

> [!NOTE]
> After you run date compression, all accounts in the ledger are locked. For example, you cannot un-apply vendor or bank ledger entries for any accounts during the period for which dates are compressed.

<!--* General ledger entries
* Customer ledger entries-->
<!--* Fixed asset ledger entries
* G/L budget entries
* VAT entries

  After the compression the contents of the following fields are always retained: **Posting Date**, **Type**, **Closed**, **Gen. Bus. Posting Group**, **Gen. Prod. Posting Group**, **VAT Calculation Type**, **Base**, and **Amount**.

  With the **Retain Field Contents** facility, you can also retain the contents of the following additional fields: **Document No.**, **Bill-to/Pay-to No.**, **EU 3-Party Trade**, **Country/Region Code**, and **Internal Ref. No.**.
* Insurance ledger entries
* Maintenance ledger entries
* Resource ledger entries

  After the compression, the contents of the following fields are retained: **Posting Date**, **Resource No.**, **Resource Group No.**, **Entry Type**, **Quantity**, **Total Cost**, **Total Price**, and **Chargeable**.

  With the **Retain Field Contents** facility, you can also retain the contents of the following additional fields: **Document No.**, **Work Type Code**, **Job No.**, **Unit of Measure Code**, **Source Type**, **Source No.**. **Chargeable**, **
* Warehouse entries

  After the compression the contents of the following fields are always retained: **Registering Date**, **Location Code**, **Zone Code**, **Bin Code**, **Item No.**, **Quantity**, **Qty. (Base)**, **Bin Type Code**, **Entry Type**, **Variant Code**, **Qty. per Unit of Measure**, **Unit of Measure Code**, **Warranty Date**, **Expiration Date**, **Cubage**, and **Weight**.

  With the **Retain Field Contents** facility, you can also retain the contents of the **Serial No.** and **Lot No.** fields. -->

The number of entries that result from a Date Compress batch job depends on how many filters you set, which fields are combined, and which period length you choose. There will always be at least one entry. 

> [!WARNING]
> Date Compression deletes entries, so you should always make a backup copy of the database before you run the batch job.

The following table lists the fields on the **Options** FastTab that are available on all batch jobs. The **Retain Field Contents** section includes additional fields are described above.

|Field  |Description  |
|-------|-------------|
|Starting Date     |Enter the first date to be included in the date compression. The compression will affect all entries from this date to the Ending Date.|
|Ending Date     |Enter the last date to be included in the date compression. The compression will affect all entries from the Starting Date to this date.|
|Period Length |Select the length of the period whose entries will be combined. Choose the field to see the options. If you selected the period length *Quarter*, *Month*, or *Week*, only entries with a common accounting period are compressed.|
|Retain Field Contents     |Place check marks in the boxes if you want to retain the contents of certain fields even though the entries are compressed. The more fields you select, the more detailed the compressed entries will be. If you do not select any of these fields, the batch job will create one entry per day, week, or another period, according to the period selected in the **Period Length** field. |

## See Also

[Administration](admin-setup-and-administration.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]