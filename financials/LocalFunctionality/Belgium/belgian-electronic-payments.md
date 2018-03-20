---
    title: Belgian Electronic Payments
    description: In the electronic banking module in [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can make domestic, international, SEPA, and non-Euro SEPA electronic payments.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 03/16/2018
    ms.author: sgroespe

---
# Belgian Electronic Payments
In the electronic banking module in [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can make domestic, international, SEPA, and non-Euro SEPA electronic payments.  

|Electronic payment|Description|  
|------------------------|---------------------------------------|  
|Domestic|These payments are in the local currency (LCY) and are processed by a local financial institution for beneficiaries who have accounts that have a local financial institution. The validity of the bank account numbers will be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|International|These payments are either in foreign currencies or in LCY and are processed by a local financial institution for beneficiaries who have accounts that have foreign financial institutions. The validity of the bank account numbers will not be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|SEPA|These payments are in euro and are processed in countries/regions that accept SEPA payments. The validity of the bank account numbers will be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|Non-Euro SEPA|These payments are in currency other than euro and made to a country/region outside the European Economic Association (EEA). The validity of the bank account numbers will be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  

 In electronic banking, because the standard for electronic payments is different for countries/regions, electronic payments created in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] can only be processed by financial institutions in Belgium. For international payments, the local financial institutions will then have to process the payment with the foreign institutions.  

> [!NOTE]  
>  Credit memos cannot be processed separately because payments must not have a negative balance. To process a credit memo, the credit memo must be added to one or more invoices by summarizing payments.  

Before you can make electronic payments, you must set up use electronic banking in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

## Generate Payment Suggestions
After you have set up electronic banking, you can start generating payment suggestions. You can do this in the payment journal.  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2.  Select the appropriate journal batch, and then choose the **Suggest Vendor Payments** action.  
3.  In the **Suggest Vendor Payments EB**  window, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Last Due Date**|Enter the last due date that can appear on the vendor ledger entries to be included in the batch job.|  
    |**Take Credit Memos**|Select to include outstanding credit memos for vendors. The credit memos will be subtracted from the amount due. When selecting credit memos, the due date is not used.|  
    |**Take Payment Discounts**|Select to include vendor ledger entries for which you can receive a payment discount.|  
    |**Payment Discount Date**|Enter the date that will be used to calculate a payment discount.|  
    |**Available Amount**|If there is a maximum amount available for payments, you can enter it here. The batch job will then create a payment suggestion based on this amount and the priority of vendors.|  
    |**Posting Date**|Enter the date that will appear as the posting date on the lines that the batch job inserts in the payment journal.|  

4.  On the **Vendor** FastTab, enter the filter criteria.  
5.  Choose the **OK** button to start the batch job.  

When the batch job is finished, the payment journal contains all vendor ledger entries that match the filters.  

## Correcting Payment Lines  
You must correct all errors before you can post the electronic payment lines. You can correct payment lines in the following ways.  

|Correction|Description|  
|----------------|---------------------------------------|  
|Add a payment journal line|If the payment journal already contains many lines and you want to add an additional line, you can enter the journal line manually. For example, if you want to reimburse a credit memo to a customer. These types of customer payments are not suggested automatically by the **Suggest Vendor Payments** batch job.|  
|Edit a payment journal line|If you have not assigned a bank account to the payment journal or if you have not specified a preferred bank account on the Vendor card, you will have to manually enter this information on each journal line before posting the journal. If you specify a bank account for a vendor, the bank account will be copied to all payment journal lines for that vendor. For more information, see [Set Up Electronic Banking](how-to-set-up-electronic-banking.md).|  
|Delete a payment journal line|The **Suggest Vendor Payments** batch job creates payment suggestions for all vendors matching the specified criteria. If you want to prevent payment for a specific vendor ledger entry or vendor, you can delete the corresponding journal lines.|  

For more information, see [Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md).  

## Test Electronic Payments
> [!Note]
> [!INCLUDE[onprem_only](../../includes/onprem_only_md.md)]

After you have set up electronic banking and generated payment suggestions, you can test the payment journal lines for errors before posting them.  

Some of the information that is validated includes:  

- Bank accounts numbers are valid.  
- Positive payment lines are present.  
- If domestic and international payments are made from only one bank account.  
- If only one bank account can be used for Isabel.  
- If payment lines are in Euro for SEPA.  
- If a number series has been defined for SEPA.  

You can view any errors in the **Export Check Error Logs** window.  

> [!IMPORTANT]  
>  You have to correct all errors before you can post the lines.  

## To test payment journal lines  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select the required journal batch.  
3.  In the **Export Protocol** field, select the export protocol.  
4.  Enter the payment journal line information, and then choose the **Check Payment Lines** action to validate the payment journal lines. The validation that is performed on the journal lines depends on the type of check that is specified in the **Export Protocols** window.  

## Export Payment Files
After you have printed a test report and corrected all errors, you can export the payment journal lines to a payment file that contains either domestic, international, SEPA, or non-euro SEPA payments. The file can be sent to a bank either on disk, by modem, or via Interbanks Standards Association Belgium (Isabel). You can only create one file for each posting date and each currency code. When you export the payments to a file,an accompanying note is printed, which can also be sent to the bank.  

In the payment journal, the **Status** field on the exported lines will be set to **Posted**.  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journal**, and then choose the related link.  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Batch Name**|Specify the batch name of the payment journal.|  
    |**Bank Account**|Specify the bank account of the payment journal.|  
    |**Export Protocol**|Specify the export protocol code of the payment journal line. Export protocols control which payment file will be generated in the payment journal.<br /><br /> You can have a mixture of export formats in a single batch, such as domestic, international, SEPA, or a combination of these. However, when exporting the payment lines to a file, you can only use one export format, or export protocol. **Note:**  By defining the export protocol, you also define the type of validation that will be performed in the payment journal.|  

3.  Choose the **Check Payment Lines** action.

    The **Export Check Error Logs** window displays any errors that may exist. If there are errors, you must fix the errors before you can continue.

4. If there are no errors, choose the **Export Payment Lines** action.  

    The report that you specified in the **Test Report ID** field in the **EB Payment Journal Templates** will open.  

5.  Choose the **Print** button.  


## See Also  
[Belgium Local Functionality](belgium-local-functionality.md)  
[Belgian Electronic Banking](belgian-electronic-banking.md)   
[Set Up Electronic Banking](how-to-set-up-electronic-banking.md)   
[Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
[Generate Payment Suggestions](how-to-generate-payment-suggestions.md)   
[Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
[Test Electronic Payments](how-to-test-electronic-payments.md)   
[Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md)   
[Print Payment Files](how-to-print-payment-files.md)
