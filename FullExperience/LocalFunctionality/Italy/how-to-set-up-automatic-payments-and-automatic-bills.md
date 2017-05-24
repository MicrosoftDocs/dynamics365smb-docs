---
title: "How to: Set Up Automatic Payments and Automatic Bills"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "customer bills, setting up"
  - "bills, setting up"
  - "vendor bills, setting up"
ms.assetid: fcf22c63-8ac2-493d-9c8c-778e1c060d6c
caps.latest.revision: 44
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Set Up Automatic Payments and Automatic Bills
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can manage automatic payments and bills.  
  
 To use automatic payments and automatic bills, you must set up the relevant information.  
  
### To add bank information for your company  
  
1.  In the **Search** box, enter **\($ N\_1 Company Information $\)**, and then choose the related link.  
  
2.  On the **Payments** FastTab, fill in the key fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_79\_12112 SIA Code $\)**|Specify the company identification number that your company has been assigned by the bank.|  
    |**\($ T\_79\_12114 Autoriz. No. $\)**|Specify the authorization number that your company has been assigned by the bank.|  
    |**\($ T\_79\_12115 Autoriz. Date $\)**|Specify the date of when the bank assigned your company the authorization number.|  
    |**\($ T\_79\_12116 Signature on Bill $\)**|Specify the signature that will appear on bills and bank receipts.|  
    |**\($ T\_79\_38 IBAN $\)**|Specify the International Bank Account Number \(IBAN\) for the bank account that you specified in the **\($ T\_79\_14 Bank Account No. $\)** field.|  
    |**\($ T\_79\_39 SWIFT Code $\)**|If you do trade with customers or vendors abroad, specify the Society for Worldwide Interbank Financial Telecommunication \(SWIFT\) code for your bank.|  
    |**\($ T\_79\_12118 BBAN $\)**|Specify the Basic Bank Account Number \(BBAN\) for your bank account.|  
  
    > [!NOTE]  
    >  All of these entries are used during automatic payments and automatic billing.  
  
3.  Choose the **OK** button.  
  
### To set up a bill posting group for a bank account  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  In the **\($ N\_371 Bank Account List $\)** window, select the relevant bank account, and then, on the **Home** tab, choose **Edit**.  
  
3.  In the **\($ N\_370 Bank Account Card $\)** window, on the **Navigate** tab, choose **Bill Posting Group**.  
  
4.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12179\_2 Payment Method $\)**|Select the payment method for the type of payments made to or from this bank account. For example, for the bank account that will be used for automatic payments made by customers, select a payment method for bank transfers.|  
    |**\($ T\_12179\_3 Bills For Collection Acc. No. $\)**|Specify the general ledger account where bills for collection will be credited.|  
    |**\($ T\_12179\_4 Bills For Discount Acc. No. $\)**|Specify the general ledger account where bill discounts will be debited.|  
    |**\($ T\_12179\_5 Bills Subj. to Coll. Acc. No. $\)**|Specify the general ledger account where bills subject to collection will be credited.|  
    |**\($ T\_12179\_6 Expense Bill Account No. $\)**|Specify the general ledger account where expenses for bank receipts will be posted.|  
  
5.  Choose the **OK** button.  
  
    > [!IMPORTANT]  
    >  Before you can export a vendor bill, you must select a payment format in the **\($ T\_270\_1210 Payment Export Format $\)** field in the **\($ N\_370 Bank Account Card $\)** window.  
    >   
    >  Before you can export a customer bill, you must select a payment format in the **\($ T\_270\_117 SEPA Direct Debit Exp. Format $\)** field in the **\($ N\_370 Bank Account Card $\)** window.  
  
 The following procedure describes how to set up automatic bills for sales and receivables, but the same steps also apply to setting up purchases and payables for using automatic payments.  
  
### To set up automatic bills for sales and receivables  
  
1.  In the **Search** box, enter **\($ N\_459 Sales & Receivables Setup $\)**, and then choose the related link.  
  
2.  On the **Bills** FastTab, in the **\($ T\_311\_12175 Temporary Bill List No. $\)** field, select the temporary bill list number. Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_311\_12175 Temporary Bill List No. $\)**|Select the number series that will be used for temporary bill lists.|  
    |**\($ T\_311\_12176 Recall Bill Description $\)**|Specify the descriptive text that will be used for recalled bills.|  
    |**\($ T\_311\_12174 Bank Receipts Risk Period $\)**|Specify a date formula to calculate the risk period in days, such as **20D**.<br /><br /> This will be a reference for bank receipt closing. Customer bills will be closed only at the end of the risk period that you specify here.|  
  
3.  Choose the **OK** button.  
  
 Next, you must specify bill codes for those payment methods that you use for automatic payments and automatic bills.  
  
### To specify bill codes for a payment method  
  
1.  In the **Search** box, enter **\($ N\_427 Payment Methods $\)**, and then choose the related link.  
  
2.  Select the payment method that you use for bank transfers to vendors, and then, in the **\($ T\_289\_12171 Bill Code $\)** field, select a bill code.  
  
    1.  To create a bill code, in the **\($ T\_289\_12171 Bill Code $\)** field, choose the field, and then choose **New**.  
  
    2.  In the **\($ N\_12184 Bill $\)** window, fill in the fields. For more information, see [\($ T\_12180 Bill $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-t_12180-bill-$-.md).  
  
 Now, you can process customer bills and vendor bills so that they are handled automatically.  
  
## See Also  
 [How to: Set Up Payment Terms\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-set-up-payment-terms-duplicate.md)   
 [\($ T\_270\_117 SEPA Direct Debit Exp. Format $\)](assetId:///c216f572-6171-4a19-ae9e-56091e558897)   
 [\($ N\_1 Company Information $\)](assetId:///45c9cfb7-ca1f-4323-99cd-9360a5631648)   
 [\($ N\_370 Bank Account Card $\)](assetId:///c44f01ce-a89a-441e-a543-1a1e951edcaa)   
 [\($ N\_459 Sales & Receivables Setup $\)\-duplicate](../../Sales/-$-n_459-sales-receivables-setup-$-duplicate.md)   
 [\($ N\_460 Purchases & Payables Setup $\)](../../Purchasing/-$-n_460-purchases-payables-setup-$-.md)   
 [\($ N\_21 Customer Card $\)](../Topic/\($%20N_21%20Customer%20Card%20$\).md)   
 [\($ N\_26 Vendor Card $\)](../Topic/\($%20N_26%20Vendor%20Card%20$\).md)   
 [\($ N\_12184 Bill $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-n_12184-bill-$-.md)   
 [\($ T\_12180 Bill $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-t_12180-bill-$-.md)   
 [Italy Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/italy-local-functionality.md)