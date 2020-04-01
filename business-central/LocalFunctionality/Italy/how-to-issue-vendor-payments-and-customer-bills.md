---
    title: How to Issue Vendor Payments and Customer Bills
    description: The vendor and customer bill pay feature supports SEPA-based formats in addition to Italian file formats.
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
# Issue Vendor Payments and Customer Bills

The vendor and customer bill pay feature supports SEPA-based formats in addition to Italian file formats. You can pay vendors according to the SEPA Credit Transfer standard and collect payment from customers according to the SEPA Direct Debit standard. The following procedure describes the process for sending a SEPA-based payment to a vendor. The steps are similar for collecting payment from a customer.  

Before starting the following procedure, make sure that information for your company's bank has been provided on the **Bank Account Card** page. On the card, include information for the following fields:  

- IBAN  
- SWIFT Code (optional)  
- Payment Export Format  
- SEPA CT Msg. ID No. Series  

In addition, there must be a posted purchased invoice against which you can send a payment.  

## To issue payment to a vendor  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendors**, and then choose the related link.  
2. Select the vendor to which you want to send payment. On the **Payment** FastTab, in the **Payment Method Code** field, choose the **TRASFBANC** option.
3. Choose the **Bank Accounts** action.  
4. In the **Vendor Bank Account List**, select the vendor's bank account, and then choose the **Edit** action.
5. On the **Transfer** FastTab, specify information for the **IBAN** field.  
6. Choose the **OK** button.  
7. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendor Bill Card**, and then choose the related link.  
8. Choose the **New** action.  
9. On the **General** FastTab, enter information in the following fields: **Bank Account No.** of the vendor and **Payment Method Code**.  
10. Choose the **Suggest Payment** action.
11. Set filters, as appropriate, and then choose the **OK** button to run the batch job.  
12. Choose the **Create List** action.
13. Choose the **Yes** button to send the bill payment.  
14. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendor Bill List Issued**, and choose the related link.
15. Select the bill payment that you issued from the list, and then choose the **Edit** action. The **Vendor Bill List Sent Card** page opens.  
16. To export the payment information, choose the **Export Bill List to File** action. You can review the xml file that was sent.  

    1. Export to File (for standard SEPA format files)  
    2. Export Bill List to File  

You can review the .xml file before sending it. To review and fix errors, you can refer to the **File Export Errors** FactBox.  

## See Also

[Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file)
