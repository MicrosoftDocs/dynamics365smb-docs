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
# How to: Issue Vendor Payments and Customer Bills
The vendor and customer bill pay feature supports SEPA-based formats in addition to Italian file formats. You can pay vendors according to the SEPA Credit Transfer standard and collect payment from customers according to the SEPA Direct Debit standard. The following procedure describes the process for sending a SEPA-based payment to a vendor. The steps are similar for collecting payment from a customer.  
  
 Before starting the following procedure, make sure that information for your company's bank has been provided in the **Bank Account Card** window. On the card, include information for the following fields:  
  
-   IBAN  
  
-   SWIFT Code (optional)  
  
-   Payment Export Format  
  
-   SEPA CT Msg. ID No. Series  
  
 In addition, there must be a posted purchased invoice against which you can send a payment.  
  
### To issue payment to a vendor  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link.  
  
2.  Select the vendor to which you want to send payment. On the **Payment** FastTab, in the **Payment Method Code** field, choose, **TRASFBANC**. On the **Navigate** tab, in the **Vendor** group, choose **Bank Accounts**.  
  
3.  In the **Vendor Bank Account List**, select the vendor's bank account, and on the **Home** tab, in the **Manage** group, choose **Edit**. On the **Transfer** FastTab, specify information for the **IBAN** field.  
  
     Choose the **OK** button.  
  
4.  In the **Search** box, enter **Vendor Bill Card**, and then choose the related link.  
  
5.  On the **Home** tab, in the **Manage** group, choose **New**.  
  
6.  On the **General** FastTab, enter information for the following fields: **Bank Account No.** of the vendor and **Payment Method Code**.  
  
7.  On the **Home** tab, in the **Process** group, choose **Suggest Payment**. Set filters, as appropriate, and then choose the **OK** button to run the batch job.  
  
8.  On the **Home** tab, in the **Process** group, choose **Create List**. Choose the **Yes** button to send the bill payment.  
  
9. In the **Search** box, enter **Vendor Bill List Issued**, and select bill payment that you issued from the list. On the **Home** tab, choose **Edit**. The **Vendor Bill List Sent Card** window opens.  
  
10. To export the payment information, on the **Home** tab, in the **Report** group, chose one of the following: **Export Bill List to File**. You can review the xml file that was sent.  
  
    1.  Export to File (for standard SEPA format files)  
  
    2.  Export Bill List to File  
  
     You can review the .xml file before sending it. To review and fix errors, you can refer to the **File Export Errors** Fact Box.  
  
## See Also  
 [Make Payments with Bank Data Conversion Service or SEPA Credit Transfer](make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)   
 [How to: Set Up SEPA Credit Transfer](how-to-set-up-sepa-credit-transfer.md)   
 [Collect Payments with SEPA Direct Debit](collect-payments-with-sepa-direct-debit.md)