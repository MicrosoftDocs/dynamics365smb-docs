---
    title: How to Record VAT | Microsoft Docs
    description: In EU countries/regions, every sales and purchase transaction is subject to VAT calculations. For more information about recording VAT, see [Recording VAT](../recording-vat.md).
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Record VAT on Sales and Purchases
If your country or region requires you to calculate value-added tax (VAT) on sales and purchase transactions so that you can report the amounts to a tax authority, you can set up [!INCLUDE[d365fin](includes/d365fin_md.md)] to calculate VAT automatically on sales and purchase documents. For more information, see [Setting Up to Calculations and Posting Methods for Value-Added Tax] (finance-setup-vat.md). 

However, you can also enter VAT manually. For example, this is useful if you need to make a correction.

## Calculating and Displaying VAT Amounts in Sales and Purchase Documents  
You can calculate and display VAT amounts in sales and purchase documents differently, depending on the type of customer or vendor that you are dealing with. You can also override the calculated VAT amount to match the VAT amount calculated by your vendor on a given transaction.  
  
### Correcting or reverting VAT amounts  
You can make corrections to posted VAT entries. This allows you to change the total sales or purchase VAT amounts without changing the VAT base. <!-- not sure about this section -->

If a payment discount has been calculated on the basis of an invoice amount that includes VAT, you revert the payment discount part of the VAT amount when the payment discount is granted. Note that you must activate the **Adjust for Payments Disc.** field in both the general ledger setup in general and the VAT posting setup for specific combinations of a VAT business posting group and a VAT product posting group.  
  
### Unit Price and Line Amount Including/Excluding VAT on sales documents  
When you choose an item number in the **No.** field on a sales document, [!INCLUDE[d365fin](includes/d365fin_md.md)] fills in the **Unit Price** field. The unit price comes from either the **Item** card or the item prices allowed for the item and customer. [!INCLUDE[d365fin](includes/d365fin_md.md)]calculates the **Line Amount** when you enter a quantity for the line.  
  
If you are selling to retail consumers, you may want prices on sales documents to include VAT. To do this, choose the **Prices Including VAT** check box on the document.  
  
### Checked and unchecked fields  
<!--include this in the previous section, and remove this heading-->
If the **Prices Including VAT** check box is chosen on a sales document, the **Unit Price** and **Line Amount** fields include VAT, and the field names will also reflect this. By default, VAT is not included in these fields.  
  
If the field is not selected, the program will fill in the **Unit Price** and **Line Amount** field excluding VAT and the field names will reflect this.  
  
### Prices Including VAT Defaults on Customer and Item Cards  

<!--Might want to move this to the setting up topic-->
You can set up the default setting of the **Prices Including VAT** for all sales documents for a customer in the **Prices Including VAT** field on the **Customer** card.  
  
You can also set up item prices to include or exclude VAT. Normally, item prices contained in the Item Card will be the price excluding VAT. The program uses the information from the **Price Includes VAT** field on the **Item** card to determine the unit price amount for sales documents.  
  
The following table provides an overview of how the program calculates the unit price amounts for a sales document when you have not set up prices in the **Sales Prices** window:  
  
|**Price Includes VAT field on Item Card**|**Prices Including VAT field in Sales Header**|**Action Performed**|  
|-----------------------------------------------|----------------------------------------------------|--------------------------|  
|No check mark|No check mark|The **Unit Price** on the Item Card is copied to **Unit Price Excl. VAT** field on the sales lines.|  
|No check mark|Check mark|The program calculates the VAT amount per unit and adds to the **Unit Price** on the Item Card. This total Unit Price is then entered in the **Unit Price Incl. VAT field** on the sales lines.|  
|Check mark|No check mark|The program calculates the VAT amount included in the **Unit Price** on the Item Card using the VAT% related to the VAT Bus. Posting Gr. (Price) and the VAT Prod. Posting Group combination. The **Unit Price** on the Item Card, reduced by the VAT amount, is then entered in the **Unit Price Excl. VAT** field in the sales lines.|  
|Check mark|Check mark|The **Unit Price** on the Item Card is copied to **Unit Price Incl. VAT** field on the sales lines.|

**********************************************************************************************************************************


## Manually Adjusting VAT Amounts in Sales and Purchase Documents  
[!INCLUDE[d365fin](includes/d365fin_md.md)] can automatically calculate the VAT amount using the customer's VAT Bus. Posting Group and the item's VAT Prod. Posting Group. However, you can also manually enter VAT amounts if, for example, your customer or vendor uses a different rounding method and you need to make an adjustment.  
  
#### To manually enter VAT in sales documents  
1. On the **General Ledger Setup** page, specify a **Max. VAT Difference Allowed** between the amount calculated by the program and the manual amount.  
2. On the **Sales & Receivables Setup** page, place a check mark in the **Allow Vat Difference** field.  
  
#### To adjust VAT for a sales document  
1. Open the relevant sales order.  
2. Choose the **Statistics** action.  
3. Choose the **Invoicing** FastTab.  
  
    > [!NOTE]  
    >  The total VAT amount for the invoice, grouped by VAT identifier, is displayed in the lines. You can manually adjust the amount in the **VAT Amount** field on the lines for each VAT identifier. When you modify the **VAT Amount** field, the program checks to ensure that you have not changed the VAT by more than the amount you have specified as the maximum difference allowed. If the amount is outside the range of the **Max. VAT Difference Allowed**, a warning will be displayed stating the maximum allowed difference. You will be unable to proceed until the amount is adjusted to within the acceptable parameters. Click **OK** and enter another **VAT Amount** that is within the allowed range. If the VAT difference is equal to or lower than the maximum allowed, the VAT will be divided proportionally among the document lines that have the same VAT identifier.  
  
## Manual VAT Calculation Using Journals  
You can also adjust VAT amounts in general, sales, and purchase journals. For example, you might need to do this when you enter a vendor invoice in your journal and there is a difference between the VAT amount that [!INCLUDE[d365fin](includes/d365fin_md.md)] calculated and the VAT amount on the vendor's invoice.  
  
#### Before you manually enter VAT on a general journal  
1. On the **General Ledger Setup** page, specify a **Max. VAT Difference Allowed** between the amount calculated by the program and the manual amount.  
2. On the **General Journal Templates** page, choose the **Allow VAT Difference** check box for the relevant journal.  
  
#### Before you manually enter VAT on sales and purchase journals  
1. On the **Purchases & Payables Setup** page, choose the **Allow VAT Difference** check box.  
2. After you complete the setup described above, you can adjust the **VAT Amount** field on the general journal line, or the **Bal. VAT Amount** field on the sales or purchase journal line. [!INCLUDE[d365fin](includes/d365fin_md.md)] will check that the difference is not greater than the specified maximum.  
  
    > [!NOTE]  
    >  If the difference is greater, a warning will be displayed stating the maximum allowed difference. To continue, you must adjust the amount. Choose **OK** and then enter an amount that is within the allowed range. If the VAT difference is equal to or lower than the maximum allowed, [!INCLUDE[d365fin](includes/d365fin_md.md)] will show the difference in the **VAT Difference** field.  



**************************************************************************************************************

# How to: Process Certificates of Supply
When you sell goods to a customer in another EU country/region, you must send the customer a certificate of supply that the customer must sign and return to you. The following procedures are for processing certificates of supply for sales shipments, but the same steps apply for service shipments of items, and return shipments to vendors.  
  
### To view certificate of supply details  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Shipments**, and then choose the related link.  
2. Choose the relevant sales shipment to a customer in another EU country/region.  
3. On the **Home** tab, in the **Shipment** group, choose **Certificate of Supply Details**.  
4. By default, if the VAT Posting Group setup for the customer has the **Certificate of Supply Required** check box selected, then the **Status** field is set to **Required**. You can update the field to indicate whether the certificate has been received back from the customer.  
  
     If the VAT Posting Group setup does not have the **Certificate of Supply Required** check box selected, then a record is created and the **Status** field is set to **Not Applicable**. You can update the field to reflect the correct status information. You can manually change the status from **Not Applicable** to **Required**, and from **Required** to **Not Applicable** as needed.  
  
     When you update the **Status** field to **Required**, **Received**, or **Not Received**, a certificate is created.  
  
    > [!TIP]  
    >  You can use the **Certificates of Supply** window to get a view of the status of all posted shipments for which a certificate of supply has been created.  
  
5. On the **Home** tab, in the **Process** group, choose **Print Certificate of Supply**.  
  
     You can preview or print the document. When you choose **Print Certificate of Supply** and print the document, the **Printed** check box is automatically selected. In addition, if not already specified, the status of the certificate is updated to **Required**.  
  
 You include the printed certificate with the shipment.  
  
### To print a certificate of supply  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Shipments**, and then choose the related link.  
2. Choose the relevant sales shipment to a customer in another EU country/region.  
  
3.  On the **Home** tab, in the **Shipment** group, choose **Print Certificate of Supply**.  
  
    > [!NOTE]  
    >  Alternatively, you can print a certificate from the  **Certificate of Supply** window.  
  
4.  To include information from the lines on the shipment document in the certificate, select the **Print Line Details** check box.  
  
5.  Select the **Create Certificates of Supply if Not Already Created** check box to have [!INCLUDE[d365fin](includes/d365fin_md.md)] create certificates for posted shipments that do not have one at the moment of execution. When you select the check box, new certificates will be created for all posted shipments that do not have certificates within the selected range  
  
6.  By default, the filter settings are for the shipment document that you have selected. Fill in the filter information to select a specific certificate of supply that you want to print.  
  
7.  In the **Certificate of Supply** window, choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
     The **Certificate of Supply Status** field and the **Printed** field are updated for the shipment in the **Certificates of Supply** window.  
  
 You must send the printed certificate of supply to the customer for signature.  
  
### To update the status of a certificate of supply for a shipment  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Shipments**, and then choose the related link.  
  
2.  Choose the relevant sales shipment to a customer in another EU country/region.  
  
3.  In the **Status** field, choose the relevant option.  
  
     If the customer has returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  
  
     You can modify the date to reflect the date that you received the customer's signed certificate of supply. You can also add a link to the signed certificate using standard [!INCLUDE[d365fin](includes/d365fin_md.md)] linking.  
  
     If the customer does not return the signed certificate of supply, choose **Not Received**. You must then send the customer a new invoice that includes VAT, because the original invoice will not be accepted by the tax authority.  
  
 To view a group of certificates, you start from the **Certificates of Supply** window, and then update the information about the status of outstanding certificates as you receive them back from your customers. This can be useful when you want to search for all certificates that have a certain status, for example, **Required**, for which you want to update their status to **Not Received**.  
  
### To update the status of a group of certificates of supply  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Certificates of Supply**, and choose the related link.  
  
2.  Filter the **Status** field to the value that you want in order to create the list of certificates that you want to manage.  
  
3.  To update the status information, on the **Home** tab, in the **Manage** group, choose **Edit List**.  
  
4.  In the **Status** field, choose the relevant option.  
  
     If the customer has returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  
  
     You can modify the date to reflect the date that you received the signed the certificate of supply. You can also add a link to the signed certificate using standard Microsoft Dynamics NAV document linking.  
  
    > [!NOTE]  
    >  You cannot create a new certificate of supply in the **Certificate of Supply** window when you navigate to it using this procedure. To create a certificate for a shipment that was not set up to require one, open the posted sales shipment, and use either of two procedures described above:  
    >   
    >  -   To manually create a certificate of supply certificate  
    > -   To print a certificate of supply.
  
## See Also  
 [Recording VAT](../recording-vat.md)   
 [Import VAT](../import-vat.md)   
 [VAT Reporting and Settlement](../vat-reporting-and-settlement.md)   
 [How to: Enter VAT-liable Amounts Without VAT in General Journals](../how-to-enter-vat-liable-amounts-without-vat-in-general-journals.md)   
 [How to: Set Up and Record Intrastat](../how-to-set-up-and-record-intrastat.md)   
 [How to: Create a VAT Combination Setup](../how-to-create-a-vat-combination-setup.md)   
 [How to: View VAT Entries](../how-to-view-vat-entries.md)