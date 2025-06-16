---
title: How to work with VAT on sales and purchases
description: This article describes the various ways of working with VAT both manually and with automatic setup, to help you meet country/region specific regulations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: VAT, sales, purchases
ms.search.form: 7, 118, 130, 142, 459, 460, 525
ms.date: 05/29/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Work with VAT on sales and purchases

If your country or region requires you to calculate and report value-added tax (VAT) on sales and purchase transactions, you can set up [!INCLUDE[prod_short](includes/prod_short.md)] to calculate VAT. For more information, see [Setting Up to Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md).

There are, however, some VAT-related tasks that you can do manually. For example, you might need to correct a posted amount if you discover that a vendor uses a different rounding method.  

> [!TIP]
> You can let [!INCLUDE[prod_short](includes/prod_short.md)] validate VAT registration numbers and other company information when you create or update documents. For more information, see [Validate VAT Registration Numbers](finance-how-validate-vat-registration-number.md).

## Calculating and displaying VAT amounts on sales and purchase documents  

When you choose an item number in the **No.** field on a sales or purchase document, [!INCLUDE[prod_short](includes/prod_short.md)] fills in the **Unit Price** and **Line Amount** fields. The unit price comes from either the **Item** card or the item prices allowed for the item and customer. [!INCLUDE[prod_short](includes/prod_short.md)] calculates the line amount when you enter a quantity for the line.  

If you want the unit prices and line amounts to include VAT, for example, if you sell to retail consumers, choose the **Prices Including VAT** check box on the document. For more information, see [Including or Excluding VAT in Prices and Line Amounts](#including-or-excluding-vat-in-prices-and-line-amounts). 

You can calculate and display VAT amounts in sales and purchase documents differently. The difference depends on the type of customer or vendor you're dealing with. You can also change the calculated VAT amount manually, for example, so that it matches the VAT amount calculated by your vendor on a given transaction.

### Including or excluding VAT in prices and line amounts

If you choose the **Prices Including VAT** checkbox on a sales document, the **Unit Price** and **Line Amount** fields include VAT. By default, the values in these fields don't include VAT. The names of the fields reflect whether prices include VAT.  

You can set up the default setting of the **Prices Including VAT** for all sales documents for a customer in the **Prices Including VAT** field on the **Customer** card. You can also set up item prices to include or exclude VAT. Typically, prices on the Item Card exclude VAT.

The following table provides an overview of how the application calculates the unit price amounts for a sales document when prices aren't set up on the **Sales Prices** page:  

|**Price Includes VAT field on Item Card**|**Prices Including VAT field**|**Action Performed**|  
|-----------------------------------------------|----------------------------------------------------|--------------------------|  
|Not Enabled|Not Enabled|The **Unit Price** on the Item Card is copied to **Unit Price Excl. VAT** field on the sales lines.|  
|Not Enabled|Enabled|The application calculates the VAT amount per unit and adds to the **Unit Price** on the Item Card. This total unit price is then entered in the **Unit Price Incl. VAT field** on the sales lines.|  
|Enabled|Not Enabled|The application calculates the VAT amount included in the **Unit Price** field on the **Item Card** using the VAT percentage related to the VAT Bus. Posting Gr. (Price) and the VAT Prod. Posting Group combination. The **Unit Price** on the Item Card, reduced by the VAT amount, is then entered in the **Unit Price Excl. VAT** field in the sales lines. For more information, see [Using VAT Business Posting Groups and Customer Price Groups](finance-work-with-vat.md#using-vat-business-posting-groups-and-customer-price-groups).|  
|Enabled|Enabled|The **Unit Price** on the Item Card is copied to **Unit Price Incl. VAT** field on the sales lines.|

#### Using VAT business posting groups and customer price groups 

If you want prices to include VAT, you can use VAT business posting groups to calculate the amount based on the VAT posting setup for the group. For more information, see [Set up VAT business posting groups](finance-setup-vat.md#set-up-vat-business-posting-groups).

Depending on what you want to do, you can assign a VAT business posting group to customers or sales documents in the following ways:

* To use the same VAT rate for all customers, you can choose a group in the **VAT Business Posting Group (Price)** field on the **Sales & Receivables Setup** page.
* To use a VAT rate for a specific customer, you can choose a group in the **VAT Business Posting Group (Price)** field on the **Customer Card** page. 
* To use a VAT rate for a specific of customers, you can choose a group in the **VAT Business Posting Group (Price)** field on the **Customer Price Group** page. For example, this setting is useful when you want a price to apply to all customers in a certain geographical region or a specific industry.
* On all sales documents, in the **VAT Business Posting Group** field. The VAT amount specified for the group is used only for the document you're currently working on.

> [!NOTE]
> If you do not specify a group in the **VAT Business Posting Group (Price)** field VAT will not be included in prices.

#### Examples

Factors such as the country or region you're selling in, or the type of industries you sell to, can affect the amount of VAT that you must account for. For example, a restaurant might charge 6% VAT for meals that are eaten in-house, and 17% for takeaway. To accomplish that, you create a VAT business posting group (price) for in-house and one for takeaway.

## Working with VAT Date

### VAT Date in documents

When you create new sales or purchase documents, the **VAT Date** is based on the setting in the **Default VAT Date** field on the **General Ledger Setup** page. This default value can be the same as **Posting Date** or **Document Date**. If you need a different VAT date, you can manually change the value in the **VAT Date** field. When you post the document, the **VAT Date** is shown on the posting document and on the VAT and G/L entries.

> [!NOTE]
> If the **VAT Date** field isn't available on your documents or journals, that means that **Do not use VAT Date functionality** is chosen in the **VAT Date Usage** field on the **General Ledger Setup** page.  

> [!IMPORTANT]
> If you configure **Control VAT Period** in the **General Ledger Setup** as **Block posting within closed period**, or **Block posting within closed and warn for released period**, you can post document or journal only if the date in the **VAT Date** field is not in a closed period in **VAT Return Periods**. Even if the period in **VAT Return Periods** is open, you might get a warning based on the **VAT Return Status** and configuration in the **Control VAT Period**.

> [!IMPORTANT]
> Starting in version 23.1, you can prevent or allow posting of the **VAT Date** for specific data range, using the **Allow VAT Date From** and **Allow VAT Date To** fields in the **VAT Setup** and the **User Setup**. If you are using older versions, you can prevent or allow posting of the **VAT Date** for specific data range, using the **Allow Posting From** and **Allow Posting To** fields in the **General Ledger Setup** and the **User Setup**.  

> [!NOTE]
> If you leave the **VAT Date** blank, [!INCLUDE [prod_short](includes/prod_short.md)] will use your default setup from **Default VAT Date** in the **General Ledger Setup** as a **VAT Date** in the posted transaction.  

### Modifying the VAT Date in posted entries

If needed, you can change the VAT date posted documents. To change the date in the **VAT Date** field for posted documents, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Entries**, and then choose the related link. 
2. Find the entry with wrong VAT date.  
3. Choose the **Edit list** action, and then enter the correct date in the **VAT Date** field.  
4. When you close the page, the VAT date changes in related **G/L Entries** and in the posted document.  

> [!NOTE]
> You can change the **VAT Date** field in **VAT Entries** only if your current date is not in a closed VAT return period. Even if the period in the **VAT Return Periods** field is open, you might get a warning based on the **VAT Return Status**.  

> [!NOTE]
> If your document has more than one **VAT Entry**, you only need to change the value in the **VAT Date** field in one entry related to the document. To keep entries consistent, [!INCLUDE[prod_short](includes/prod_short.md)] automatically changes the VAT date in VAT entries related to this transaction. [!INCLUDE [prod_short](includes/prod_short.md)] will update the **VAT Date** in other tables (GL Entries and documents), but only related to this transaction.  

## Correcting VAT amounts manually on sales and purchase documents  

You can make corrections to posted VAT entries so that you can change the total sales or purchase VAT amounts without changing the VAT base. For example, if you receive an invoice from a vendor with an incorrect VAT amount.  

Although you might have one or more combinations set up to handle import VAT, you must set up at least one VAT product posting group. For example, you can name it **CORRECT** for correction purposes, unless you can use the same general ledger account in the **Purchase VAT Account** field on the VAT posting setup line. For more information, see [Setting Up to Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md).

If a payment discount was calculated based on an invoice amount that includes VAT, you revert the payment discount part of the VAT amount when you grant the payment discount. You must activate the **Adjust for Payments Disc.** field in both the general ledger setup in general and the VAT posting setup for specific combinations of a VAT business posting group and a VAT product posting group.  

### To set the system up for manual VAT entry in sales documents

To enable manual VAT changes on sales documents, follow these steps. The steps are similar on the **Purchases & Payables Setup** page.

1. On the **General Ledger Setup** page, specify a **Max. VAT Difference Allowed** between the amount calculated by application and the manual amount.  
2. On the **Sales & Receivables Setup** page, turn on the **Allow Vat Difference** toggle.  

### To adjust VAT for a sales document

1. Open the relevant sales order.  
2. Choose the **Statistics** action.  
3. On the **Invoicing** FastTab, choose the value in the **No. of Tax Lines** field.
4. Edit the **VAT Amount** field.   

> [!NOTE]  
> The total VAT amount for the invoice, grouped by VAT identifier, is displayed in the lines. You can manually adjust the amount in the **VAT Amount** field on the lines for each VAT identifier. When you modify the **VAT Amount** field, application checks to ensure that you have not changed the VAT by more than the amount you have specified as the maximum difference allowed. If the amount is outside the range of the **Max. VAT Difference Allowed**, a warning will be displayed stating the maximum allowed difference. You will be unable to proceed until the amount is adjusted to within the acceptable parameters. Click **OK** and enter another **VAT Amount** that is within the allowed range. If the VAT difference is equal to or lower than the maximum allowed, the VAT will be divided proportionally among the document lines that have the same VAT identifier.  

## Calculating VAT manually using journals  

You can also adjust VAT amounts in general, sales, and purchase journals. For example, you might need an adjustment if you enter a vendor invoice in your journal and the VAT amount that [!INCLUDE[prod_short](includes/prod_short.md)] calculated and the VAT amount on the vendor's invoice differ.  

### To set the system up for manual VAT entry in general journals

You must perform the following steps before you manually enter VAT in a general journal.  

1. On the **General Ledger Setup** page, specify a **Max. VAT Difference Allowed** between the amount calculated by application and the manual amount.  
2. On the **General Journal Templates** page, choose the **Allow VAT Difference** check box for the relevant journal.  

### To set the system up for manual VAT entry in a sales and purchase journals

You must perform the following steps before you manually enter VAT in a sales or purchase journal.

1. On the **Purchases & Payables Setup** page, choose the **Allow VAT Difference** check box.  
2. Repeat step 1 for the **Sales & Receivables Setup** page.
3. After you complete the setup, you can adjust the **VAT Amount** field on the general journal line, or the **Bal. VAT Amount** field on the sales or purchase journal line. [!INCLUDE[prod_short](includes/prod_short.md)] verifies that the difference isn't greater than the specified maximum.  

> [!NOTE]  
> If the difference is greater, a warning will be displayed stating the maximum allowed difference. To continue, you must adjust the amount. Choose **OK** and then enter an amount that is within the allowed range. If the VAT difference is equal to or lower than the maximum allowed, [!INCLUDE[prod_short](includes/prod_short.md)] will show the difference in the **VAT Difference** field.  

## Posting Import VAT with Purchase Invoices
Instead of using journals to post an import VAT invoice, you can use a purchase invoice.  

### To set up purchasing for posting import VAT invoices

1. Set up a vendor card for the import authority that sends you the import VAT invoice. The **Gen. Bus. Posting Group** and **VAT Bus. Posting Group** must be set up in the same way as the general ledger account for the import VAT.  
2. Create a **Gen. Product Posting Group** for the import VAT and set up an import VAT **Def. VAT Product Posting Group** for the related **Gen. Product Posting Group**.  
3. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
4. Select the import VAT general ledger account, and then choose the **Edit** action.  
5. On the **Posting** FastTab, select the **Gen. Prod. Posting Group** setup for import VAT. [!INCLUDE[prod_short](includes/prod_short.md)] automatically fills in the **VAT Prod. Posting Group** field.  
6. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Posting Setup**, and then choose the related link.  
7. Create a combination of the **Gen. Bus. Posting Group** for the VAT authority and the **Gen. Prod. Posting Group** for import VAT. For this combination, in the **Purchase Account** field, choose the import VAT general ledger account.  

### To create a new invoice for the import authority vendor after you complete the setup  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2. Create a new purchase invoice.  
3. In the **Buy-from Vendor No.** field, choose the import authority vendor, and then choose the **OK** button.  
4. In the purchase line, in the **Type** field, choose **G/L Account**, and in the **No.** field, choose the import VAT general ledger account.  
5. In the **Quantity** field, type **1**.  
6. In the **Direct Unit Cost Excl. VAT** field, specify the VAT amount.  
7. Post the invoice.  

## Processing certificates of supply

When you sell goods to a customer in another EU country/region, you must send the customer a certificate of supply that the customer must sign and return to you. The following procedures are for processing certificates of supply for sales shipments, but the same steps apply for service shipments of items, and return shipments to vendors.  

### To view certificate of supply details  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Shipments**, and then choose the related link.  
2. Choose the relevant sales shipment to a customer in another EU country/region.  
3. Choose **Certificate of Supply Details**.  
4. By default, if the **Certificate of Supply Required** check box is selected for VAT Posting Group setup for the customer, the **Status** field is set to **Required**. You can update the field to indicate whether the customer returned the certificate.  

> [!Note]  
>  If the VAT Posting Group setup does not have the **Certificate of Supply Required** check box selected, then a record is created and the **Status** field is set to **Not Applicable**. You can update the field to reflect the correct status information. You can manually change the status from **Not Applicable** to **Required**, and from **Required** to **Not Applicable** as needed.  

   When you update the **Status** field to **Required**, **Received**, or **Not Received**, a certificate is created.  

> [!TIP]  
>  You can use the **Certificates of Supply** page to get a view of the status of all posted shipments for which a certificate of supply has been created.  

5. Choose **Print Certificate of Supply**.  

> [!Note]  
> You can preview or print the document. When you choose **Print Certificate of Supply** and print the document, the **Printed** check box is automatically selected. In addition, if not already specified, the status of the certificate is updated to **Required**. If needed, you include the printed certificate with the shipment.  

### To print a certificate of supply

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Shipments**, and then choose the related link.  
2. Choose the relevant sales shipment to a customer in another EU country/region.  
3. Choose the **Print Certificate of Supply** action.  

> [!NOTE]  
> Alternatively, you can print a certificate from the **Certificate of Supply** page.  

4. To include information from the lines on the shipment document in the certificate, turn on the **Print Line Details** toggle.  
5. To have [!INCLUDE[prod_short](includes/prod_short.md)] create certificates for posted shipments that didn't have one, turn on the **Create Certificates of Supply if Not Already Created** toggle. When you turn on the toggle, new certificates are created for all posted shipments that don't have certificates within the selected range.  
6. By default, the filter settings are for the shipment document that you selected. Fill in the filter information to select a specific certificate of supply that you want to print.  
7. On the **Certificate of Supply** page, choose the **Print** action to print the report, or choose the **Preview** action to view it on the screen.  

   > [!Note]  
   > The **Certificate of Supply Status** field and the **Printed** field are updated for the shipment on the **Certificates of Supply** page.  

8. Send the printed certificate of supply to the customer for signature.  

### To update the status of a certificate of supply for a shipment  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Shipments**, and then choose the related link.  
2. Choose the relevant sales shipment to a customer in another EU country/region.  
3. In the **Status** field, choose the relevant option.  

   If the customer returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  

   You can modify the date to reflect the date that you received the customer's signed certificate of supply. You can also add a link to the signed certificate using standard [!INCLUDE[prod_short](includes/prod_short.md)] linking.  

   If the customer doesn't return the signed certificate of supply, choose **Not Received**. You must then send the customer a new invoice that includes VAT, because the tax authority won't accept the original invoice.  

To view a group of certificates, start from the **Certificates of Supply** page, and then update the information about the status of outstanding certificates as you receive them from your customers. The updated information can be useful when you want to search for all certificates that have a certain status, for example, **Required**, for which you want to update their status to **Not Received**.  

### To update the status of a group of certificates of supply  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Certificates of Supply**, and choose the related link.  
2. Filter the **Status** field to the value that you want in order to create the list of certificates that you want to manage.  
3. To update the status information, choose **Edit List**.  
4. In the **Status** field, choose the relevant option.  

   If the customer returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  

   You can modify the date to reflect the date that you received the signed the certificate of supply. You can also add a link to the signed certificate using standard [!INCLUDE[prod_short](includes/prod_short.md)] document linking.  

> [!NOTE]
> You cannot create a new certificate of supply on the **Certificate of Supply** page when you navigate to it using this procedure. To create a certificate for a shipment that was not set up to require one, open the posted sales shipment, and use either of two procedures described earlier:  
>
> * To manually create a certificate of supply certificate  
> * To print a certificate of supply.

## Related information

[Setting Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Validate a VAT Registration Number](finance-how-validate-vat-registration-number.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
