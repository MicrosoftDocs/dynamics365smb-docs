---
title: Work with VAT on Sales and Purchases
description: Work with VAT prices and dates in Business Central, correct VAT amounts, post import VAT invoices, and manage certificates of supply for shipments.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: VAT, sales, purchases
ms.search.form: 7, 118, 130, 142, 459, 460, 525
ms.date: 11/11/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---
# Work with VAT on sales and purchases

If your country or region requires you to calculate and report value-added tax (VAT) on sales and purchase transactions, you can set up [!INCLUDE[prod_short](includes/prod_short.md)] to calculate VAT. Learn more in [Set up calculations and posting methods for VAT](finance-setup-vat.md).

There are, however, some VAT-related tasks that you can do manually. For example, you might need to correct a posted amount if you discover that a vendor uses a different rounding method.  

> [!TIP]
> You can let [!INCLUDE[prod_short](includes/prod_short.md)] validate VAT registration numbers and other company information when you create or update documents. Learn more in [Validate VAT registration numbers](finance-how-validate-vat-registration-number.md).

## Calculating and displaying VAT amounts on sales and purchase documents  

When you choose an item number in **No.** on a sales document, [!INCLUDE[prod_short](includes/prod_short.md)] fills in **Unit Price** from the **Item** card or the applicable sales price. On a purchase document, the corresponding field is **Direct Unit Cost**, which uses purchase cost and price information. [!INCLUDE[prod_short](includes/prod_short.md)] calculates **Line Amount** when you enter a quantity.

If you want the unit prices and line amounts to include VAT, for example, if you sell to retail consumers, choose the **Prices Including VAT** checkbox on the document. Learn more in [Including or excluding VAT in prices and line amounts](#including-or-excluding-vat-in-prices-and-line-amounts).

You can calculate and display VAT amounts in sales and purchase documents differently. The difference depends on the type of customer or vendor you're dealing with. You can also change the calculated VAT amount manually, for example, so that it matches the VAT amount calculated by your vendor on a given transaction.

### Including or excluding VAT in prices and line amounts

If you choose the **Prices Including VAT** checkbox on a sales document, the **Unit Price** and **Line Amount** fields include VAT. By default, the values in these fields don't include VAT. The names of the fields reflect whether prices include VAT.  

You can set up the default setting of the **Prices Including VAT** for all sales documents for a customer in the **Prices Including VAT** field on the **Customer** card. You can also set up item prices to include or exclude VAT. Typically, prices on the Item Card exclude VAT.

The following table describes how the unit price is calculated for a sales document when it comes from the item card rather than a price list:

|**Price Includes VAT field on Item Card**|**Prices Including VAT field**|**Action Performed**|  
|-----------------------------------------------|----------------------------------------------------|--------------------------|  
|Not Enabled|Not Enabled|The **Unit Price** on the Item Card is copied to **Unit Price Excl. VAT** field on the sales lines.|  
|Not Enabled|Enabled|The application calculates the VAT amount per unit and adds it to **Unit Price** on the item card. This total is entered in **Unit Price Incl. VAT** on the sales lines.|
|Enabled|Not Enabled|The application calculates the VAT included in **Unit Price** on the item card, using the combination of **VAT Bus. Posting Gr. (Price)** and **VAT Prod. Posting Group**. It removes that VAT to calculate **Unit Price Excl. VAT** on the sales lines. Learn more in [Using VAT business posting groups and customer price groups](#using-vat-business-posting-groups-and-customer-price-groups).|
|Enabled|Enabled|If the VAT rate included in the item price matches the document's VAT rate, **Unit Price** is copied to **Unit Price Incl. VAT** on the sales lines. If the rates differ, the price is recalculated using the document's VAT rate.|

#### Using VAT business posting groups and customer price groups 

If you want prices to include VAT, you can use VAT business posting groups to calculate the amount based on the VAT posting setup for the group. Learn more in [Set up VAT business posting groups](finance-setup-vat.md#set-up-vat-business-posting-groups).

Different fields control the VAT included in a stored price and the VAT calculated on a sales document:

* To set the default VAT business posting group for VAT-inclusive item prices, choose a group in **VAT Bus. Posting Gr. (Price)** on the **Sales & Receivables Setup** page.
* To set the default VAT business posting group for a customer's documents, choose a group in **VAT Bus. Posting Group** on the customer card.
* To specify the VAT included in prices for a customer price group, choose a group in **VAT Bus. Posting Gr. (Price)** on the **Customer Price Groups** page. For example, use this setting for customers in a certain geographical region or industry.
* On a sales document, use **VAT Bus. Posting Group** to specify the group for that document.

> [!NOTE]
> **Prices Including VAT** controls whether sales document prices include VAT. **VAT Bus. Posting Gr. (Price)** identifies the VAT already included in a stored price. It doesn't replace the customer's VAT business posting group.

#### Examples

Factors such as the country or region you're selling in, or the type of industries you sell to, can affect the amount of VAT that you must account for. For example, a restaurant might charge 6% VAT for meals that are eaten in-house, and 17% for takeaway. To represent these different product rates, create separate VAT product posting groups and combine them with the relevant VAT business posting group in VAT posting setup.

## Working with VAT dates

### VAT date in documents

When you create new sales or purchase documents, the **VAT Date** is based on the setting in the **Default VAT Date** field on the **General Ledger Setup** page. This default value can be the same as **Posting Date** or **Document Date**. If you need a different VAT date, you can manually change the value in the **VAT Date** field. When you post the document, the **VAT Date** is shown on the posted document and on the VAT and G/L entries.

> [!NOTE]
> If the **VAT Date** field isn't available on your documents or journals, that means that **Do not use VAT Date functionality** is chosen in the **VAT Date Usage** field on the **General Ledger Setup** page.  

> [!IMPORTANT]
> If you set **Control VAT Period** on the **General Ledger Setup** page to **Block posting within closed period** or **Block posting within closed and warn for released period**, you can post a document or journal only if its **VAT Date** isn't in a closed VAT return period. Even if the period is open, you might get a warning based on **VAT Return Status** and **Control VAT Period**.

> [!IMPORTANT]
> Starting in version 23.1, use **Allow VAT Date From** and **Allow VAT Date To** on the **VAT Setup** and **User Setup** pages to control the allowed VAT date range. In older versions, use **Allow Posting From** and **Allow Posting To** on the **General Ledger Setup** and **User Setup** pages.

> [!NOTE]
> If you leave the **VAT Date** blank, [!INCLUDE [prod_short](includes/prod_short.md)] will use your default setup from **Default VAT Date** in the **General Ledger Setup** as a **VAT Date** in the posted transaction.  

### Modifying the VAT date in posted entries

If needed, you can change the VAT date in posted documents. To change **VAT Date** for a posted document, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Entries**, and then choose the related link. 
1. Find the entry with the wrong VAT date.
1. Choose **Edit List**, and then enter the correct date in **VAT Date**.
1. Close the page. The change updates the related VAT entries, G/L entries, and posted document.

> [!NOTE]
> To change **VAT Date**, **VAT Date Usage** must be **Enabled** and the VAT entry must not be closed. The new date must be in the allowed VAT date range. The existing and new dates are checked against **Control VAT Period**, so a closed period can block the change or cause a warning, depending on your setup.

> [!NOTE]
> If your document has more than one VAT entry for the same transaction, change **VAT Date** in only one of those entries. [!INCLUDE[prod_short](includes/prod_short.md)] updates the other VAT entries, G/L entries, and posted document related to that transaction.

## Correcting VAT amounts manually on sales and purchase documents  

You can make corrections to posted VAT entries so that you can change the total sales or purchase VAT amounts without changing the VAT base. For example, if you receive an invoice from a vendor with an incorrect VAT amount.  

Although you might have one or more combinations set up to handle import VAT, you must set up at least one VAT product posting group. For example, you can name it **CORRECT** for correction purposes, unless you can use the same general ledger account in the **Purchase VAT Account** field on the VAT posting setup line. Learn more in [Set up calculations and posting methods for VAT](finance-setup-vat.md).

If a payment discount was calculated based on an invoice amount that includes VAT, you reverse the payment discount part of the VAT amount when you grant the discount. Select **Adjust for Payment Disc.** on **General Ledger Setup** and **Adjust for Payment Discount** on **VAT Posting Setup** for the relevant combinations of VAT business and VAT product posting groups.

### To set the system up for manual VAT entry in sales documents

To enable manual VAT changes on sales documents, follow these steps. The steps are similar on the **Purchases & Payables Setup** page.

1. On the **General Ledger Setup** page, specify a **Max. VAT Difference Allowed** between the amount calculated by the application and the manual amount.
1. On the **Sales & Receivables Setup** page, turn on the **Allow VAT Difference** toggle.

### To adjust VAT for a sales document

1. Open the relevant sales order.  
1. Choose the **Statistics** action.
1. On the **Invoicing** FastTab, choose the value in **No. of Tax Lines**.
1. Edit **VAT Amount**.

> [!NOTE]  
> The total VAT amount for the invoice, grouped by VAT identifier, is displayed in the lines. You can manually adjust **VAT Amount** for each VAT identifier. When you change the amount, [!INCLUDE[prod_short](includes/prod_short.md)] checks that the difference doesn't exceed **Max. VAT Difference Allowed**. If it does, an error shows the maximum allowed difference. Select **OK** and enter an amount within the allowed range to continue. An allowed VAT difference is divided proportionally among the document lines with the same VAT identifier.

## Calculating VAT manually using journals  

You can also adjust VAT amounts in general, sales, and purchase journals. For example, you might need an adjustment if you enter a vendor invoice in your journal and the VAT amount that [!INCLUDE[prod_short](includes/prod_short.md)] calculated and the VAT amount on the vendor's invoice differ.  

### To set the system up for manual VAT entry in general journals

You must perform the following steps before you manually enter VAT in a general journal.  

1. On the **General Ledger Setup** page, specify a **Max. VAT Difference Allowed** between the amount calculated by the application and the manual amount.
1. On the **General Journal Templates** page, choose the **Allow VAT Difference** checkbox for the relevant journal.
1. On the **General Journal Batches** page, verify that **Allow VAT Difference** is selected for the batch you use.

### To set up manual VAT entry in sales and purchase journals

You must perform the following steps before you manually enter VAT in a sales or purchase journal.

1. On **General Journal Templates**, select **Allow VAT Difference** for the relevant sales or purchase journal template.
1. On **General Journal Batches**, verify that **Allow VAT Difference** is selected for the batch you use.
1. After you complete the setup, you can adjust **VAT Amount** on the general journal line or **Bal. VAT Amount** on the sales or purchase journal line. [!INCLUDE[prod_short](includes/prod_short.md)] verifies that the difference isn't greater than the specified maximum.

> [!NOTE]  
> If the difference is greater, an error states the maximum allowed difference. Choose **OK** and enter an amount within the allowed range. An allowed difference is shown in **VAT Difference** or **Bal. VAT Difference**, depending on which VAT amount you changed.

## Posting import VAT with purchase invoices
Instead of using journals to post an import VAT invoice, you can use a purchase invoice.  

### To set up purchasing for posting import VAT invoices

1. Set up a vendor card for the import authority that sends you the import VAT invoice. The vendor's **Gen. Bus. Posting Group** and **VAT Bus. Posting Group** determine the posting setup combinations used on the invoice.
1. Create a general product posting group for import VAT and set its **Def. VAT Prod. Posting Group** to the import VAT product posting group.
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Chart of Accounts**, and then choose the related link.
1. Select the import VAT general ledger account, and then choose **Edit**.
1. On the **Posting** FastTab, select **Gen. Prod. Posting Group** for import VAT. [!INCLUDE[prod_short](includes/prod_short.md)] fills in **VAT Prod. Posting Group**.
1. On **VAT Posting Setup**, set up the combination of the vendor's VAT business posting group and the import VAT product posting group. Set **VAT Calculation Type** to **Full VAT** and **Purchase VAT Account** to the import VAT G/L account.
1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Posting Setup**, and then choose the related link.
1. Create a combination of **Gen. Bus. Posting Group** for the VAT authority and **Gen. Prod. Posting Group** for import VAT. In **Purch. Account**, choose the import VAT G/L account.

### To create a new invoice for the import authority vendor after you complete the setup  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.  
1. Create a new purchase invoice.
1. In **Buy-from Vendor No.**, choose the import authority vendor.
1. On the purchase line, set **Type** to **G/L Account** and **No.** to the import VAT G/L account.
1. Set **Quantity** to **1**.
1. In **Direct Unit Cost Excl. VAT**, specify the VAT amount.
1. Post the invoice.

## Processing certificates of supply

If your VAT reporting requirements call for a certificate of supply, send the certificate to the customer for signature and return. The following procedures are for sales shipments, but the same steps apply to service shipments of items and return shipments to vendors.

### To view certificate of supply details  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Sales Shipments**, and then choose the related link.  
1. Choose the relevant sales shipment to a customer in another EU country/region.
1. Choose **Certificate of Supply Details**.
1. Update **Status** to indicate whether the customer returned the certificate.
1. Choose **Print Certificate of Supply**.

> [!NOTE]
> If **Certificate of Supply Required** is selected in VAT posting setup, **Status** defaults to **Required**. Otherwise, a certificate record is created with **Status** set to **Not Applicable**. You can change the status to reflect whether a certificate is required or received.

> [!TIP]  
>  You can use the **Certificates of Supply** page to get a view of the status of all posted shipments for which a certificate of supply has been created.  

> [!NOTE]
> You can preview or print the document. When you choose **Print Certificate of Supply** and print the document, the **Printed** check box is automatically selected. In addition, if not already specified, the status of the certificate is updated to **Required**. If needed, you include the printed certificate with the shipment.  

### To print a certificate of supply

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Sales Shipments**, and then choose the related link.  
1. Choose the relevant sales shipment to a customer in another EU country/region.
1. Choose **Print Certificate of Supply**.
1. To include shipment line information, turn on **Print Line Details**.
1. To create certificates for posted shipments without one, turn on **Create Certificates of Supply if Not Already Created**. New certificates are created for shipments without certificates within the selected range.
1. Review the filters. By default, they're set to the selected shipment.
1. On the **Certificate of Supply** report request page, choose **Print** or **Preview**.
1. Send the printed certificate to the customer for signature.

> [!NOTE]
> You can also print a certificate from the **Certificates of Supply** page. Printing, but not previewing, selects **Printed** and changes **Status** to **Required** if it was **Not Applicable**.

### To update the status of a certificate of supply for a shipment  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Sales Shipments**, and then choose the related link.  
1. Choose the relevant sales shipment to a customer in another EU country/region.
1. Choose **Certificate of Supply Details**.
1. In **Status**, choose the relevant option.

   If the customer returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  

   You can modify the date to reflect the date that you received the customer's signed certificate of supply. You can also add a link to the signed certificate using standard [!INCLUDE[prod_short](includes/prod_short.md)] linking.  

   If the customer doesn't return the signed certificate, choose **Not Received**. Check with your tax authority or accountant whether a VAT correction is required. Changing the certificate status doesn't create or post a new invoice.

To view a group of certificates, start from the **Certificates of Supply** page, and then update the information about the status of outstanding certificates as you receive them from your customers. The updated information can be useful when you want to search for all certificates that have a certain status, for example, **Required**, for which you want to update their status to **Not Received**.  

### To update the status of a group of certificates of supply  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Certificates of Supply**, and then choose the related link.
1. Filter **Status** to the value for the certificates you want to manage.
1. Choose **Edit List**.
1. In **Status**, choose the relevant option.

   If the customer returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  

   You can modify the date to reflect when you received the signed certificate. You can also add a link to the signed certificate using standard [!INCLUDE[prod_short](includes/prod_short.md)] document linking.

> [!NOTE]
> You can't create a new certificate directly on the **Certificates of Supply** page. To create one for a shipment that wasn't set up to require a certificate, open the posted sales shipment and use either of these procedures:
>
> * [View certificate of supply details](#to-view-certificate-of-supply-details).
> * [Print a certificate of supply](#to-print-a-certificate-of-supply).

## Related information

[Setting Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Validate a VAT Registration Number](finance-how-validate-vat-registration-number.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
