---
    title: How to: Set Up SEPA Direct Debit | Microsoft Docs
    description: From the **Direct Debit Collections** window, you can export instructions to your electronic bank to perform a direct debit collection from the customer’s bank account to your bank account. For more information, see [Collect Payments with SEPA Direct Debit](../collect-payments-with-sepa-direct-debit.md).
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
# How to: Set Up SEPA Direct Debit
From the **Direct Debit Collections** window, you can export instructions to your electronic bank to perform a direct debit collection from the customer’s bank account to your bank account. For more information, see [Collect Payments with SEPA Direct Debit](../collect-payments-with-sepa-direct-debit.md).  
  
> [!NOTE]  
>  The generic version of ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/dyn_nav_md.md)]--> supports the SEPA Credit Transfer format. In your country/region, other formats for electronic payments may be available.  
>   
>  To enable export of a bank file formats that are not supported by the generic or local versions of ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/how-to-set-up-data-exchange-definitions.md).  
  
 Before you can process customer payments electronically by exporting direct debit instructions in the SEPA Direct Debit format, you must perform the following setup steps:  
  
-   Set up the export format of the bank file that instructs your bank to perform a direct debit collection from the customer’s bank account to your bank account.  
  
-   Set up the customer’s payment method.  
  
-   Set up the direct-debit mandate that reflects your agreement with the customer to collect their payments in a certain agreement period.  
  
### To set up your bank account for SEPA direct debit  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.  
  
2.  Open the bank account that you want to use for direct debit.  
  
3.  On the **Transfer** FastTab, in the **SEPA Direct Debit Exp. Format** field, choose the option for SEPA direct debit.  
  
### To set up the customer’s payment method for SEPA direct debit  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Methods**, and then choose the related link.  
  
2.  In the **Payment Methods** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  Set up a payment method. Fill in the direct debit-specific fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Direct Debit**|Specify if the payment method is for SEPA direct debit collection.|  
    |**Direct Debit Pmt. Terms Code**|Specify the payment terms, such as DON’T PAY, that are displayed on sales invoices that are paid with SEPA direct debit to indicate to the customer that the payment will be collected automatically. Alternatively, leave the field empty.|  
  
    > [!NOTE]  
    >  Do not enter a value in the **Bal. Account No.** field.  
  
4.  Choose the **OK** button to close the **Payment Methods** window.  
  
5.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
  
6.  Open the customer card for the customer that you want to set up for SEPA direct debit collection.  
  
7.  Choose the **Payment Method Code** field, and then select the payment method code that you specified in step 3.  
  
8.  Repeat steps 6 and 7 for all customers that you want to set up for SEPA direct debit collection.  
  
#### To set up the direct-debit mandate that represents the customer agreement  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
  
2.  Open the card for the customer that you want to set up for SEPA direct debits.  
  
3.  In the **Customer Card** window, on the **Navigate** tab, in the **Customer** group, choose **Bank Accounts**.  
  
4.  In the **Customer Bank Account List** window, select the customer bank account that will use direct debits, and then, on the **Home** tab, in the **Process** group, choose **Direct Debit Mandates**.  
  
5.  In the **SEPA Direct Debit Mandates** window, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Customer Bank Account Code**|Specifies the bank account from which direct-debit payments are collected. This field is filled automatically.|  
    |**Valid From**|Specify the date when the direct-debit mandate starts.|  
    |**Valid To**|Specify the date when the direct-debit mandate ends.|  
    |**Date of Signature**|Specify the date when the customer signed the direct-debit mandate.|  
    |**Sequence Type**|Specify if the agreement covers multiple (**Recurring**) or a single (**One Off**) direct debit collection.|  
    |**Expected Number of Debits**|Specify how many direct debit collections you expect to make. This field is only relevant if you selected **Recurring** in the **Sequence Type** field.|  
    |**Debit Counter**|Specifies how many direct debit collections have been made using this direct-debit mandate. This field is automatically updated.|  
    |**Blocked**|Specify that direct debit collections cannot be made using this direct-debit mandate.|  
  
6.  Repeat steps 1 through 5 for all customers that you want to set up for SEPA direct debits.  
  
 The direct-debit mandate is automatically inserted in the **Direct Debit Mandate ID** field when you create a sales invoice for the customer that you selected in step 2. For more information, see [How to: Create Multiple Sales Invoices Based on Standard Sales Codes](../how-to-create-multiple-sales-invoices-based-on-standard-sales-codes.md).  
  
## See Also  
 SEPA Direct Debit Exp. Format   
 SEPA Direct Debit Mandates   
 [Collect Payments with SEPA Direct Debit](../collect-payments-with-sepa-direct-debit.md)   
 [Data Exchange](../data-exchange.md)