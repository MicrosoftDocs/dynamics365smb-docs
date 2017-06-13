---
title: "How to: Set Up SEPA Direct Debit"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 74374e04-69c5-4fcf-8cf1-13776b3f525a
caps.latest.revision: 7
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up SEPA Direct Debit
From the **Direct Debit Collections** window, you can export instructions to your electronic bank to perform a direct debit collection from the customer’s bank account to your bank account. For more information, see [Collect Payments with SEPA Direct Debit](../../Finance/collect-payments-with-sepa-direct-debit.md).  
  
> [!NOTE]  
>  The generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] supports the SEPA Credit Transfer format. In your country\/region, other formats for electronic payments may be available.  
>   
>  To enable export of a bank file formats that are not supported by the generic or local versions of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)], you can set up a data exchange definition by using the Date Exchange Framework. For more information, see [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md).  
  
 Before you can process customer payments electronically by exporting direct debit instructions in the SEPA Direct Debit format, you must perform the following setup steps:  
  
-   Set up the export format of the bank file that instructs your bank to perform a direct debit collection from the customer’s bank account to your bank account.  
  
-   Set up the customer’s payment method.  
  
-   Set up the direct\-debit mandate that reflects your agreement with the customer to collect their payments in a certain agreement period.  
  
### To set up your bank account for SEPA direct debit  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Open the bank account that you want to use for direct debit.  
  
3.  On the **Transfer** FastTab, in the **SEPA Direct Debit Exp. Format** field, choose the option for SEPA direct debit.  
  
### To set up the customer’s payment method for SEPA direct debit  
  
1.  In the **Search** box, enter **Payment Methods**, and then choose the related link.  
  
2.  In the **Payment Methods** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  Set up a payment method. Fill in the direct debit\-specific fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Direct Debit**|Specify if the payment method is for SEPA direct debit collection.|  
    |**Direct Debit Pmt. Terms Code**|Specify the payment terms, such as DON’T PAY, that are displayed on sales invoices that are paid with SEPA direct debit to indicate to the customer that the payment will be collected automatically. Alternatively, leave the field empty.|  
  
    > [!NOTE]  
    >  Do not enter a value in the **Bal. Account No.** field.  
  
4.  Choose the **OK** button to close the **Payment Methods** window.  
  
5.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
6.  Open the customer card for the customer that you want to set up for SEPA direct debit collection.  
  
7.  Choose the **Payment Method Code** field, and then select the payment method code that you specified in step 3.  
  
8.  Repeat steps 6 and 7 for all customers that you want to set up for SEPA direct debit collection.  
  
#### To set up the direct\-debit mandate that represents the customer agreement  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Open the card for the customer that you want to set up for SEPA direct debits.  
  
3.  In the **Customer Card** window, on the **Navigate** tab, in the **Customer** group, choose **Bank Accounts**.  
  
4.  In the **Customer Bank Account List** window, select the customer bank account that will use direct debits, and then, on the **Home** tab, in the **Process** group, choose **Direct Debit Mandates**.  
  
5.  In the **SEPA Direct Debit Mandates** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Customer Bank Account Code**|Specifies the bank account from which direct\-debit payments are collected. This field is filled automatically.|  
    |**Valid From**|Specify the date when the direct\-debit mandate starts.|  
    |**Valid To**|Specify the date when the direct\-debit mandate ends.|  
    |**Date of Signature**|Specify the date when the customer signed the direct\-debit mandate.|  
    |**Sequence Type**|Specify if the agreement covers multiple \(**Recurring**\) or a single \(**One Off**\) direct debit collection.|  
    |**Expected Number of Debits**|Specify how many direct debit collections you expect to make. This field is only relevant if you selected **Recurring** in the **Sequence Type** field.|  
    |**Debit Counter**|Specifies how many direct debit collections have been made using this direct\-debit mandate. This field is automatically updated.|  
    |**Blocked**|Specify that direct debit collections cannot be made using this direct\-debit mandate.|  
  
6.  Repeat steps 1 through 5 for all customers that you want to set up for SEPA direct debits.  
  
 The direct\-debit mandate is automatically inserted in the **Direct Debit Mandate ID** field when you create a sales invoice for the customer that you selected in step 2. For more information, see [How to: Create Multiple Sales Invoices Based on Standard Sales Codes](../../Finance/how-to-create-multiple-sales-invoices-based-on-standard-sales-codes.md).  
  
## See Also  
 [SEPA Direct Debit Exp. Format](assetId:///c216f572-6171-4a19-ae9e-56091e558897)   
 [SEPA Direct Debit Mandates](../Topic/\($%20N_1230%20SEPA%20Direct%20Debit%20Mandates%20$\).md)   
 [Collect Payments with SEPA Direct Debit](../../Finance/collect-payments-with-sepa-direct-debit.md)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)