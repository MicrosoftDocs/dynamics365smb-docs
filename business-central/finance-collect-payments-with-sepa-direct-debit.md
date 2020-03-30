---
    title: SEPA Direct Debit in Business Central | Microsoft Docs
    description: You can collect payments directly from the customer's bank account according to the SEPA format.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Collect Payments with SEPA Direct Debit
With your customer's consent, you can collect payments directly from the customer's bank account according to the SEPA format.  

 First, set up the export format of the bank file that instructs your bank to perform a direct debit. Then, set up the customer's payment method. Last, set up the direct-debit mandate that reflects your agreement with the customer to collect their payments in a certain agreement period.  

 To instruct the bank to transfer the payment amount from the customer's bank account to your company's account, you create a direct-debit collection entry, which holds information about bank accounts, the affected sales invoices, and the direct-debit mandate. You then export an XML file that is based on the collection entry, which you send to your bank for processing. Any payments that could not be processed will be communicated to you by your bank, and you must then manually reject the direct debit-collection entries in question.  

 You can set up standard customer sales codes with the direct-debit payment method and mandate information. You can then use the **Create Standard Cust. Invoices** batch job to generate multiple sales invoices with the direct-debit information prefilled. This is can be done manually or automatically, according to the payment due date.  

 When payments are successfully processed, as communicated by your bank, you can post the payment receipts either directly from the **Direct Debit Collect. Entries** page or by moving the payment lines to the journal where you post payment receipts, such as the **Cash Receipt Journal** page. Alternatively, depending on your cash management process, you can wait and just apply the payments as a part of bank reconciliation.  

> [!NOTE]  
>  To collect payments using SEPA Direct Debit, the currency on the sales invoice must be EURO.  

## Setting Up SEPA Direct Debit
From the **Direct Debit Collections** page, you can export instructions to your electronic bank to perform a direct debit collection from the customer's bank account to your bank account according to the SEPA Direct Debit format.

> [!NOTE]
> The global version of [!INCLUDE[d365fin](includes/d365fin_md.md)] supports the SEPA direct debit format only. Your country/region version may support other formats for electronic payment. See under **Local Functionality** in the table of contents.  

To enable export of a bank file formats that are not supported out of the box in [!INCLUDE[d365fin](includes/d365fin_md.md)] , you can set up a data exchange definition by using the data exchange framework. For more information, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).  

Before you can process customer payments electronically by exporting direct debit instructions in the SEPA Direct Debit format, you must perform the following setup steps:  

* Set up the export format of the bank file that instructs your bank to perform a direct debit collection from the customer's bank account to your bank account.  
* Set up the customer's payment method.  
* Set up the direct-debit mandate that reflects your agreement with the customer to collect their payments in a certain agreement period.  

### To set up your bank account for SEPA direct debit  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.  
2. Open the bank account that you want to use for direct debit.  
3. On the **Transfer** FastTab, in the **SEPA Direct Debit Export Format** field, choose the option for SEPA direct debit.  

### To set up the customer's payment method for SEPA direct debit  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Methods**, and then choose the related link.  
2. Choose the **New** action.  
3. Set up a payment method. Fill in the direct debit\-specific fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Direct Debit**|Specify if the payment method is for SEPA direct debit collection.|  
    |**Direct Debit Pmt. Terms Code**|Specify the payment terms, such as DON'T PAY, that are displayed on sales invoices that are paid with SEPA direct debit to indicate to the customer that the payment will be collected automatically. Alternatively, leave the field empty.|  

    > [!NOTE]  
    >  Do not enter a value in the **Bal. Account No.** field.  

4. Choose the **OK** button to close the **Payment Methods** page.  
5. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
6. Open the customer card for the customer that you want to set up for SEPA direct debit collection.  
7. Choose the **Payment Method Code** field, and then select the payment method code that you specified in step 3.  
8. Repeat steps 6 and 7 for all customers that you want to set up for SEPA direct debit collection.  

#### To set up the direct-debit mandate that represents the customer agreement  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. Open the card for the customer that you want to set up for SEPA direct debits.  
3. Choose the **Bank Accounts** action.  
4. On the **Customer Bank Account List** page, select the customer bank account that will use direct debits, and then choose the **Direct Debit Mandates** action.  
5. On the **SEPA Direct Debit Mandates** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Customer Bank Account Code**|Specifies the bank account from which direct\-debit payments are collected. This field is filled automatically.|  
    |**Valid From**|Specify the date when the direct\-debit mandate starts.|  
    |**Valid To**|Specify the date when the direct\-debit mandate ends.|  
    |**Date of Signature**|Specify the date when the customer signed the direct\-debit mandate.|  
    |**Sequence Type**|Specify if the agreement covers multiple (**Recurring**) or a single (**One Off**) direct debit collection.|  
    |**Expected Number of Debits**|Specify how many direct debit collections you expect to make. This field is only relevant if you selected **Recurring** in the **Sequence Type** field.|  
    |**Debit Counter**|Specifies how many direct debit collections have been made using this direct\-debit mandate. This field is automatically updated.|  
    |**Blocked**|Specify that direct debit collections cannot be made using this direct\-debit mandate.|  

6.  Repeat steps 1 through 5 for all customers that you want to set up for SEPA direct debits.  

 The direct-debit mandate is automatically inserted in the **Direct Debit Mandate ID** field when you create a sales invoice for the customer that you selected in step 2. For more information, see [Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md).

## Creating SEPA Direct Debit Collection Entries and Export to a Bank File
 To instruct the bank to transfer the payment amount from the customer's bank account to your company's account, you create a direct-debit collection, which holds information about the customer's bank account, the affected sales invoices, and the direct-debit mandate. From the resulting direct-debit collection entry, you then export an XML file that you send or upload to your electronic bank for processing. Any payments that could not be processed by the bank will be communicated to you by your bank, and you must then manually reject the direct debit-collection entries in question.  

 > [!NOTE]  
 >  To collect payments using SEPA Direct Debit, the currency on the sales invoice must be EURO.  

### To create a direct-debit collection  

 1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Direct Debit Collections**, and then choose the related link.  
 2. On the **Direct Debit Collections** page, choose the **Create Direct Debit Collection** action.  
 3. On the **Create Direct Debit Collection** page, fill in the fields as described in the following table.  

     |Field|Description|  
     |---------------------------------|---------------------------------------|  
     |**From Due Date**|Specify the earliest payment due date on sales invoices that you want to create a direct-debit collection for.|  
     |**To Due Date**|Specify the latest payment due date on sales invoices that you want to create a direct-debit collection for.|  
     |**Partner Type**|Specify if the direct-debit collection is made for customers of type **Company** or **Person**.|  
     |**Only Customers With Valid Mandate**|Specify if a direct-debit collection is created for customers who have a valid direct-debit mandate. **Note:**  A direct-debit collection is created even if the **Direct Debit Mandate ID** field is not filled on the sales invoice.|  
     |**Only Invoices With Valid Mandate**|Specify if a direct-debit collection is only created for sales invoices if a valid direct-debit mandate is selected in the **Direct Debit Mandate ID** field on the sales invoice.|  
     |**Bank Account No.**|Specify which of your company's bank accounts the collected payment will be transferred to from the customer's bank account.|  
     |**Bank Account Name**|Specifies the name of the bank account that you select in the **Bank Account No.** field. This field is filled automatically.|  

 4. Choose the **OK** button.  

A direct-debit collection is added to the **Direct Debit Collections** page, and one or more direct-debit collection entries are created.  

### To export a direct-debit collection entry to a bank file  
 1. On the **Direct Debit Collections** page, choose the **Direct Debit Collect. Entries** action.  
 2. On the **Direct Debit Collect. Entries** page, select the entry that you want to export, and then choose the **Create Direct Debit File** action.  
 3. Save the export file to the location from where you send or upload it to your electronic bank.  

      On the **Direct Debit Collect. Entries** page, the **Direct Debit Collection Status** field is changed to File Created. On the **SEPA Direct Debit Mandates** page, the **Debit Counter** field is updated with one count.  

 If the exported file cannot be processed, for example because the customer is insolvent, you can reject the direct-debit collection entry. If the exported file is successfully processed by the bank, the due payments of the involved sales invoices are automatically collected from the involved customers. In that case you can close the collection.  

### To reject a direct-debit collection entry  

 * On the **Direct Debit Collect. Entries** page, select the entry that was not successfully processed, and then choose the **Reject Entry** action.  

      The value in the **Status** field on the **Direct Debit Collect. Entries** page is changed to **Rejected**.  

### To close a direct-debit collection  
 *  On the **Direct Debit Collect. Entries** page, select the entry that was successfully processed, and then choose the **Close Collection** action.  

      The related direct-debit collection is closed.  

 You can now proceed to post receipts of payment for the involved sales invoices. You can do this as you typically post payment receipts, such as on the **Payment Registration** page, or you can post the related payment receipts directly from the **Direct Debit Collect. Entries** page. For more information, see [Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md).

## Posting SEPA Direct Debit Payment Receipts
 When a direct debit collection is successfully processed by your bank, you can proceed to post receipt of the payment for the involved sales invoices. For more information, see [Create SEPA Direct Debit Collection Entries and Export to a Bank File](finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file).  

 You can post the payment receipt directly from the **Direct Debit Collections** page or the **Direct Debit Collect. Entries** page. Alternatively, you can relay the work to another user by preparing the related journal lines.  

### To post a direct-debit payment receipt from the Direct Debit Collections page  
 1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Direct Debit Collections**, and then choose the related link.  
 2. Select a line for a direct debit collection that has been exported to a bank file and successfully processed by the bank.
 3. Choose the **Post Payment Receipts** action.  
 4. On the **Post Direct Debit Collection** page, fill in the fields as described in the following table.  

     |Field|Description|  
     |---------------------------------|---------------------------------------|  
     |**Direct Debit Collection No.**|Specify the direct debit collection that you want to post payment receipt for.|  
     |**General Journal Template**|Specify which general journal template to use for posting the payment receipt, such as the template for cash receipts.|  
     |**General Journal Batch Name**|Specify which general journal batch to use for posting the payment receipt.|  
     |**Create Journal Only**|Select this check box if you do not want to post the payment receipt when you choose the **OK** button. The payment receipt will be prepared in the specified journal and will not be posted until someone posts the journal lines in question.|  

 5. Choose the **OK** button.

## See Also  
[Managing Receivables](receivables-manage-receivables.md)  
[Service Management](service-service.md)
