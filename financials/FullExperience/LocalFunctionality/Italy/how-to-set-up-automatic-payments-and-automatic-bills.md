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
# How to: Set Up Automatic Payments and Automatic Bills
In ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->, you can manage automatic payments and bills.  
  
 To use automatic payments and automatic bills, you must set up the relevant information.  
  
### To add bank information for your company  
  
1.  In the **Search** box, enter **Company Information**, and then choose the related link.  
  
2.  On the **Payments** FastTab, fill in the key fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---
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

    ---------------------------------|---------------------------------------|  
    |**Payment Method**|Select the payment method for the type of payments made to or from this bank account. For example, for the bank account that will be used for automatic payments made by customers, select a payment method for bank transfers.|  
    |**Bills For Collection Acc. No.**|Specify the general ledger account where bills for collection will be credited.|  
    |**Bills For Discount Acc. No.**|Specify the general ledger account where bill discounts will be debited.|  
    |**Bills Subj. to Coll. Acc. No.**|Specify the general ledger account where bills subject to collection will be credited.|  
    |**Expense Bill Account No.**|Specify the general ledger account where expenses for bank receipts will be posted.|  
  
5.  Choose the **OK** button.  
  
    > [!IMPORTANT]  
    >  Before you can export a vendor bill, you must select a payment format in the **Payment Export Format** field in the **Bank Account Card** window.  
    >   
    >  Before you can export a customer bill, you must select a payment format in the **SEPA Direct Debit Exp. Format** field in the **Bank Account Card** window.  
  
 The following procedure describes how to set up automatic bills for sales and receivables, but the same steps also apply to setting up purchases and payables for using automatic payments.  
  
### To set up automatic bills for sales and receivables  
  
1.  In the **Search** box, enter **\($ N\_459 Sales & Receivables Setup $\)**, and then choose the related link.  
  
2.  On the **Bills** FastTab, in the **Temporary Bill List No.** field, select the temporary bill list number. Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Temporary Bill List No.**|Select the number series that will be used for temporary bill lists.|  
    |**Recall Bill Description**|Specify the descriptive text that will be used for recalled bills.|  
    |**Bank Receipts Risk Period**|Specify a date formula to calculate the risk period in days, such as **20D**.<br /><br /> This will be a reference for bank receipt closing. Customer bills will be closed only at the end of the risk period that you specify here.|  
  
3.  Choose the **OK** button.  
  
 Next, you must specify bill codes for those payment methods that you use for automatic payments and automatic bills.  
  
### To specify bill codes for a payment method  
  
1.  In the **Search** box, enter **Payment Methods**, and then choose the related link.  
  
2.  Select the payment method that you use for bank transfers to vendors, and then, in the **Bill Code** field, select a bill code.  
  
    1.  To create a bill code, in the **Bill Code** field, choose the field, and then choose **New**.  
  
    2.  In the **Bill** window, fill in the fields. For more information, see Bill.  
  
 Now, you can process customer bills and vendor bills so that they are handled automatically.  
  
## See Also  
 [How to: Set Up Payment Terms-duplicate](../FullExperience/how-to-set-up-payment-terms-duplicate.md)   
 SEPA Direct Debit Exp. Format   
 Company Information   
 Bank Account Card   
 [\($ N\_459 Sales & Receivables Setup $\)-duplicate](../FullExperience/-$-n_459-sales-receivables-setup-$-duplicate.md)   
 [\($ N\_460 Purchases & Payables Setup $\)](../FullExperience/-$-n_460-purchases-payables-setup-$-.md)   
 Customer Card   
 Vendor Card   
 Bill   
 Bill   
 [Italy Local Functionality](../FullExperience/italy-local-functionality.md)