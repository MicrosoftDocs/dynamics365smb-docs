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
# How to: Generate Electronic Payments
When you select electronic payment in the payment journal, the information is exported to a file, which is transmitted to your bank. The bank then transfers the payment from your bank account to the payee's bank account. If you are using the electronic payment option, journal lines must be exported and transmitted before they can be posted.  
  
### To suggest payments  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related entry.  
  
2.  On the **Home** tab, in the **Process** group, choose **Suggest Vendor Payments**.  
  
3.  In the **Suggest Vendor Payments** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Last Payment Date**|The last valid payment date for vendor ledger entries.|  
    |**Find Payment Discounts**|Select to include vendor ledger entries for which you can receive a payment discount.|  
    |**Summarize per Vendor**|Select to make one line per vendor for each currency in which the vendor has existing ledger entries.<br /><br /> If selected, you avoid transmitting multiple transfers and sending multiple pieces of remittance advice to the same vendor. The remittance advice lists the individual invoices that are being paid. All the open invoices and credit memos are combined in a single payment line.<br /><br /> If not selected, the batch job suggests one line per invoice.|  
    |**By Dimension**|The dimensions by which you want to group the suggested payments. You receive one suggested payment per combination of dimension values for each currency in which the vendor has existing ledger entries. For more information, see [How to: Set Up Dimensions and Dimension Values](../how-to-set-up-dimensions-and-dimension-values.md).|  
    |**Use Vendor Priority**|The content of the Priority field on the vendor cards determines the order in which vendor entries are suggested for payment by the batch job. Vendors are prioritized for payment suggestions if you specify an available amount in the **Available Amount** field.|  
    |**Available Amount \($\)**|The maximum amount available for payments in United States dollars \(USD\). The batch job creates a payment suggestion based on this amount and on the prioritization of vendors. It includes only vendor entries that can be paid in full.|  
    |**Posting Date**|The posting date.|  
    |**Starting Document No.**|The document number that appears on the first payment journal line.|  
    |**New Doc. No. per Line**|Select to fill in the payment journal lines with consecutive document numbers.|  
    |**Bal. Account Type**|Select **Bank Account** for the balance account type.|  
    |**Bal. Account No.**|The balance account number.|  
    |**Bank Payment Type**|Select **Electronic Payment** to export payment journal entries to a file using the Automated Clearing House \(ACH\) standard file format.<br /><br /> –or–<br /><br /> Select **Electronic Payment-IAT** to export payment journal entries to a file using the International ACH Transaction \(IAT\) file format. This file format is required if a payment transaction involves financial agencies outside of the United States.|  
  
4.  On the **Vendor** FastTab, select the appropriate filters.  
  
5.  To suggest payments, choose the **OK** button.  
  
## See Also  
 [How to: Set Up Dimensions and Dimension Values](../how-to-set-up-dimensions-and-dimension-values.md)   
 [How to: Apply Vendor Ledger Entries](../how-to-apply-vendor-ledger-entries.md)   
 [How to: Void Checks](../how-to-void-checks.md)   
 Priority   
 [How to: Set Up Electronic Payments for Bank Accounts](../how-to-set-up-electronic-payments-for-bank-accounts.md)   
 [How to: Void Posted Checks](../how-to-void-posted-checks.md)   
 [Bank Payment Type-duplicate](../-$-t_81_70-bank-payment-type-$-duplicate.md)   
 [Electronic Payments for United States, Canada, and Mexico](../electronic-payments-for-united-states-canada-and-mexico.md)   
 [How to: Transmit Electronic Payments](../how-to-transmit-electronic-payments.md)   
 [How to: Export Electronic Payments-duplicate](../how-to-export-electronic-payments-duplicate.md)