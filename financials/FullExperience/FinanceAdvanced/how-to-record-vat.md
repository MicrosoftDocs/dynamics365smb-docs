---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Record VAT
In EU countries\/regions, every sales and purchase transaction is subject to VAT calculations. For more information about recording VAT, see [Recording VAT](../recording-vat.md).  
  
## Manually Adjusting VAT Amounts in Sales and Purchase Documents  
 The program automatically calculates the VAT using the customer's VAT Bus. Posting Group and the item's VAT Prod. Posting Group. However, you can also manually enter the VAT amounts, if the amount calculated by the program is slightly different to that calculated by your customer or vendor, for example, due to rounding.  
  
#### To manually enter VAT in sales documents  
  
1.  In the ![Shortcut icon](../media/shortcutcoldicon.gif "shortcutColdIcon")**General Ledger Setup** window, specify a **Max. VAT Difference Allowed** between the amount calculated by the program and the manual amount.  
  
2.  In the **Sales & Receivables Setup** window, place a check mark in the **Allow Vat Difference** field.  
  
#### To adjust VAT for a sales document  
  
1.  Open the relevant sales order.  
  
2.  Open the **Sales Order Statistics** window.  
  
3.  Click the **Invoicing** FastTab.  
  
    > [!NOTE]  
    >  The total VAT amount for the invoice, grouped by VAT identifier, is displayed in the lines. You can manually adjust the amount in the **VAT Amount** field on the lines for each VAT identifier. When you modify the **VAT Amount** field, the program checks to ensure that you have not changed the VAT by more than the amount you have specified as the maximum difference allowed. If the amount is outside the range of the **Max. VAT Difference Allowed**, a warning will be displayed stating the maximum allowed difference. You will be unable to proceed until the amount is adjusted to within the acceptable parameters. Click **OK** and enter another **VAT Amount** that is within the allowed range. If the VAT difference is equal to or lower than the maximum allowed, the VAT will be divided proportionally among the document lines that have the same VAT identifier.  
  
## Manual VAT Calculation Using Journals  
 You can also adjust the VAT amounts calculated by the program in general, sales, and purchase journals. It may be necessary to do this when you enter a vendor invoice in your journal and there is a difference between the program's calculated VAT amount and the VAT amount on the vendor's invoice you have received.  
  
#### Before you manually enter VAT on a general journal  
  
1.  In the ![Shortcut icon](../media/shortcutcoldicon.gif "shortcutColdIcon")**General Ledger Setup** window, specify a **Max. VAT Difference Allowed** between the amount calculated by the program and the manual amount.  
  
2.  Place a check mark in the **Allow VAT Difference** field for the relevant journal in the ![Shortcut icon](../media/shortcutcoldicon.gif "shortcutColdIcon")**General Journal Templates** window.  
  
#### Before you manually enter VAT on sales and purchase journals  
  
1.  Check the **Allow VAT Difference** field in the ![Shortcut icon](../media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_460 Purchases & Payables Setup $\)](DynamicsNAV:////runpage?Page=460)** windows, respectively.  
  
2.  Once you have completed the setup described above, you can adjust the **VAT Amount** field on the general journal line, or the **Bal. VAT Amount** field on the sales or purchase journal line, to equal the invoice VAT amount. The program will check that the difference is not greater than the specified maximum.  
  
    > [!NOTE]  
    >  If the difference is greater, a warning will be displayed stating the maximum allowed difference and you will be unable to proceed until the amount is adjusted accordingly. Click **OK** and enter another amount that is within the allowed range. If the VAT difference is equal to or lower than the maximum allowed, the program will show the difference in the **VAT Difference** field.  
  
## See Also  
 [Recording VAT](../recording-vat.md)   
 [Import VAT](../import-vat.md)   
 [VAT Reporting and Settlement](../vat-reporting-and-settlement.md)   
 [How to: Enter VAT-liable Amounts Without VAT in General Journals](../how-to-enter-vat-liable-amounts-without-vat-in-general-journals.md)   
 [How to: Set Up and Record Intrastat](../how-to-set-up-and-record-intrastat.md)   
 [How to: Create a VAT Combination Setup](../how-to-create-a-vat-combination-setup.md)   
 [How to: View VAT Entries](../how-to-view-vat-entries.md)