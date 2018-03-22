---
    title: Set up SEPA credit transfer | Microsoft Docs
    description: Learn how to set up SEPA credit transfer in Business Central .
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: sepa, credit, transfer, payment,
    ms.date: 08/21/2017
    ms.author: sgroespe

---
# Set Up SEPA Credit Transfer
From the **Payment Journal** window, you can export payments to a file for upload to your electronic bank for processing of the related money transfers. [!INCLUDE[d365fin](includes/d365fin_md.md)] supports the SEPA Credit Transfer format, but in your country/region, other formats for electronic payments may be available.  

To enable export of a bank file formats that are not supported out of the box in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can set up a data exchange definition by using the data exchange framework. For more information, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).  

Before you can process payment electronically by exporting payment files in the SEPA Credit Transfer format, you must perform the following setup steps:  

* Set up the bank account in question to handle the SEPA Credit Transfer format  
* Set up vendor cards to process payments by exporting files in the SEPA Credit Transfer format  
* Set up the related general journal batch to enable payment export from the **Payment Journal** window  
* Connect the data exchange definition for one or more payment types with the relevant payment method or methods  

### To set up a bank account for SEPA Credit Transfer  
1. In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
2. Open the card of the bank account from which you will export payment files in the SEPA Credit Transfer format.  
3. On the **Transfer** FastTab, in the **Payment Export Format** field, choose **SEPADD**.  
4. In the **SEPA CT Msg. ID No. Series** field, choose a number series from which numbers are assigned to SEPA credit transfer entries.  
5. Make sure the **IBAN** field is filled.  

    > [!NOTE]  
    >  The **Currency Code** field must be set to **EUR**, because SEPA credit transfers can only be made in the EURO currency.  

### To set up a vendor card for SEPA Credit Transfer  
1. In the **Search** box, enter **Vendors**, and then choose the related link.  
2. Open the card of the vendor whom you will pay electronically by export payment files in the SEPA Credit Transfer format.  
3. On the **Payment** FastTab, in the **Payment Method Code** field, choose **BANK**.  
4. In the **Preferred Bank Account** field, choose the bank to which the money will be transferred when it is processed by your electronic bank.  

     The value in the **Preferred Bank Account** field is copied to the **Recipient Bank Account** field in the **Payment Journal** window.  

### To set the payment journal up to export payment files  
1. In the **Search** box, enter **Payment Journals**, and then choose the related link.  
2. Open the payment journal that you use to process payments by exporting files in the SEPA Credit Transfer format.  
3. In the **Batch Name** field, choose the drop\-down button.  
4. In the **General Journal Batches** window, on the **Home** tab, in the **Manage** group, choose **Edit List**.  
5. On the line for the payment journal that you will use to export payments, select the **Allow Payment Export** check box.  

### To connect the data exchange definition for one or more payment types with the relevant payment method or methods  
1. In the **Search** box, enter **Payment Methods**, and then choose the related link.  
2. In the **Payment Methods** window, select the payment method that is used to export payments from, and then choose the **Pmt. Export Line Definition** field.  
3. In the **Pmt. Export Line Definitions** window, select the code that you specified in the **Code** field on the **Line Definitions** FastTab in step 4 in the “To describe the formatting of lines and columns in the file” section in the [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md) procedure.  

    The direct-debit mandate is automatically inserted in the **Direct Debit Mandate ID** field when you create a sales invoice for the customer that you selected in step 2. For more information, see [Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md).  

## See Also  
[Collecting Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)  
[Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md)  
[Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md)  
[Exchanging Data Electronically](across-data-exchange.md)  
