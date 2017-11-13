---
    title: How to Create Additional Sheets 
    description: In [!INCLUDE[navnow](../../includes/navnow_md.md)], you can create additional sheets based on VAT purchase ledgers and VAT sales ledgers.
    
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
# How to: Create Additional Sheets
In [!INCLUDE[navnow](../../includes/navnow_md.md)], you can create additional sheets based on VAT purchase ledgers and VAT sales ledgers.  
  
### To create entries for an additional sheet for a VAT purchase or sales ledger  
  
1.  Select the VAT purchase or sales line in the **VAT Ledger List** window with the required accounting period.  
  
2.  On the **Actions** tab, choose **Functions**, and then choose **Create Additional Sheet**.  
  
3.  Fill in the batch job according to the guidelines at Create VAT Sales Led. Ad. Sh..  
  
 The parameters for creating a VAT purchase ledger additional sheet and VAT sales ledger additional sheet are the same as the parameters for creating the VAT Purchase Ledger and the VAT Sales Ledger.  
  
### To print additional sheets on a VAT Purchase Ledger report  
  
1.  In the **VAT Ledger List**, on the **Actions** tab, choose **Print**, and then choose **Additional sheet**.  
  
2.  In the **VAT Purch. Ledger Add. Sheet** window, choose the **Options** tab.  
  
3.  In the **Period Type** field, select one of the following options:  
  
    -   **Day**  
  
    -   **Month**  
  
    -   **Quarter**  
  
    > [!NOTE]  
    >  In the **VAT Ledger** tab, the **Type** field and the **Code** field are automatically created.  
  
4.  Choose **Preview** or choose **Print**.  
  
### To print additional sheets on a VAT Sales Ledger report  
  
1.  In the **VAT Ledger List**, on the **Actions** tab, choose **Print**, and then choose **Additional sheet**.  
  
2.  In the **VAT Sales Ledger Add. Sheet** window, choose the **Options** tab.  
  
3.  In the **Sorting** field, select one of the following options:  
  
    -   **Document Date**  
  
    -   **Document No.**  
  
    -   **Customer No.**  
  
4.  In the **Period Type** field, select one of the following options:  
  
    -   **Day**  
  
    -   **Month**  
  
    -   **Quarter**  
  
    > [!NOTE]  
    >  In the **VAT Ledger** tab, the **Type** field and the **Code** field are automatically created.  
  
5.  Choose **Preview** or choose **Print**.  
  
## Creating Corrective Documents to Include in Additional Sheets  
 The information changed in the tax invoice after the invoice is registered in the previous purchase book must be reflected in the additional sheet of the previous book (corrected book). The additional sheet is part of the purchase book.  
  
 The first line contains the totals of the purchase book at the end of the period when the tax invoice is registered. The next lines are the annulled tax invoices. The annulled tax invoices have a negative sign if the corrected invoice amount is lesser than the initial amount, and a positive sign if the corrected invoice amount is greater than the initial amount. The last line is calculated as the sum of the amounts of the first total line and the annulled tax invoices.  
  
 The information changed in the tax invoice after the invoice is registered in the previous sales book must be reflected in the additional sheet of the previous book (corrected book). The additional sheet is part of the sales book.  
  
 The first line contains totals of the sales book at the end of the period when the tax invoice is registered. The next lines are the annulled tax invoices with a negative sign. The corrected invoices with positive amounts belong to the previous period. The last line is calculated as the sum of the amounts of the first total line, annulled tax invoices, and the corrected invoices.  
  
 Processing of corrective documents for sales book is similar to processing for purchases book with one difference. In additional sheets, the number and the date of initial factura must be reflected.  
  
#### To create a correction entry for posted purchase credit memos  
  
1.  Create and post a purchase credit memo.  
  
2.  Choose the **VAT** tab.  
  
3.  Select the **Additional VAT Ledger Sheet** field.  
  
4.  Enter information in the following fields:  
  
    -   **Corrected Document Date**  
  
    -   **Vendor VAT Invoice Date**  
  
    -   **Vendor VAT Invoice Rcvd Date**  
  
    -   **Vendor VAT Invoice No.**  
  
#### To create a correction entry for a posted purchase invoice  
  
1.  Create and post a purchase invoice.  
  
2.  Choose the **VAT** tab.  
  
3.  Select the **Corrected Document Date** field.  
  
4.  Enter information in the following fields:  
  
    -   **Vendor VAT Invoice Date**  
  
    -   **Vendor VAT Invoice Rcvd. Date**  
  
    -   **Vendor VAT Invoice No.**  
  
    > [!NOTE]  
    >  You can also create corrective documents in the general journal. General journal lines contain all the fields mentioned above.  
  
#### To post additional VAT  
  
1.  In the **Sales Invoice** window or the **Credit Memo** window, choose the **VAT** tab.  
  
2.  Enter the **Posting No.** field.  
  
    > [!NOTE]  
    >  You cannot post an invoice with the same number as the initial invoice. You must use an extra symbol in addition to the initial number.  
  
3.  Select the **Additional VAT Ledger Sheet** field.  
  
4.  Enter information in the **Corrected Document Date** field.  
  
5.  In the additional sheet, the **Date of Facture** field reflects the corrected document date.  
  
## See Also  
 [VAT Ledgers](vat-ledgers.md)