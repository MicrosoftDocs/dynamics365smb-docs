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
# How to: Suggest DTA Payment for Vendors
You can suggest vendor payments using the payment journal, and transfer the overdue invoices into the journal for individual vendors. You can also examine each vendor for open credit memos or open payments, and build a list of vendors for DatenTrägerAustausch (DTA) processing. For more information, see [How to: Verify a List of Vendors for DTA Payments](how-to-verify-a-list-of-vendors-for-dta-payments.md).  
  
 During the batch processing of DTA payment suggestions, the foreign currency (FCY) amount is converted to local currency (LCY) at the current rate for FCY payments, and transferred into the payment journal. For more information, see the **Payment Journal** window. In the case of a bank debit, the LCY amount is overwritten with the debited LCY amount, and the exchange rate—or exchange factor—is calculated. For more information, see the General Ledger Setup table and the Currency Exchange Rate table.  
  
### To suggest DTA payment for vendors  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the required journal batch.  
  
3.  Select the required payment line, and on the **Home** tab, in the **Process** group, select **DTA Suggest Vendor Payment**.  
  
4.  In the **DTA Suggest Vendor Payments** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Posting Date**|Specify the credit date for the payment. This date is useful in determining whether a payment discount has been provided.|  
    |**Due Date from**|Specify the starting date for the open invoices to be included in the payment suggestion.|  
    |**Due Date to**|Specify the ending date for the open invoices to be included in the payment suggestion.|  
    |**Process Cash Discounts**|Specify if the cash discount payments outside the due date range will be considered for the payment suggestion.|  
    |**Cash Disc. Date from**|Specify the starting date for the cash discount. The open entries with cash discount dates within this date range are included in the payment suggestion.|  
    |**Cash Disc. Date to**|Specify the ending date for the cash discount. The open entries with cash discount dates within this date range are included in the payment suggestion.|  
    |**Available Amount (LCY)**|Enter the maximum value of the sum of all payments.|  
    |**First Doc. No.**|Specify the payment suggestion document number. This number is assigned according to the number series for the current log.|  
    |**Debit to Bank**|Select the code of the bank that will receive the debit. The bank must be activated for DTA.|  
    |**Auto. Debit Bank**|Specify if the bank will be debited automatically, depending on the currency code.|  
  
5.  Choose the **OK** button.  
  
 During processing, each vendor is checked for open credit memos or open payments, and a message displays at the end of the process. All of the related lines are transferred to the payment journal. The related vendor ledger entries are marked with **DTA** to prevent transfer of duplicate entries to the payment journal. You can view, check, and modify the suggested payments, and you can decide whether to reduce the payments by the credit memo amounts, or to apply the open credit memos and open invoices.  
  
## See Also  
 [Swiss Electronic Payments Using DTA](swiss-electronic-payments-using-dta.md)   
 [How to: Verify a List of Vendors for DTA Payments](how-to-verify-a-list-of-vendors-for-dta-payments.md)   
 [How to: Submit DTA Payments](how-to-submit-dta-payments.md)   
 [How to: Export Payments Using EZAG](how-to-export-payments-using-ezag.md)   
 DTA Setup   
 General Ledger Setup   
 Currency Exchange Rate   
 Payment Journal   
 [How to: Suggest Vendor Payments](how-to-suggest-vendor-payments.md)   
 Suggest Vendor Payments   
 Debit Bank