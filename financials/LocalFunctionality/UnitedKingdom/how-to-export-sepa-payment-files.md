---
    title: How to: Export SEPA Payment Files | Microsoft Docs
    description: The following procedure describes how to export a SEPA payment file, one of the payment options supported by [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The procedure describes how to create a payment for a vendor, but the same steps also apply to creating payments for a customer.
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
# How to: Export SEPA Payment Files
The following procedure describes how to export a SEPA payment file, one of the payment options supported by [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The procedure describes how to create a payment for a vendor, but the same steps also apply to creating payments for a customer.  
  
 Before starting this procedure, you need to specify the following information on the vendor card:  
  
-   **Payment Method Code**: Bank  
  
-   **Preferred Bank Account**  
  
 In addition, you must specify IBAN and SWIFT Code information for the recipient bank.  
  
### To export a SEPA payment file  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank through which you will make the SEPA payment, and on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Transfer** FastTab, fill in the following fields:  
  
    -   **SWIFT Code**  
  
    -   **IBAN**  
  
    -   **Payment Export Format**: SEPA  
  
    -   **SEPA CT Msg. ID No. Series**  
  
     Close the window.  
  
4.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
5.  Select a batch in the **Batch Name** field. In the **General Journal Batches** window, for the batch, select the **Allow Payment Export** check box.  
  
     Choose the **OK** button.  
  
6.  In the **Payment Journal** window, create a payment line.  
  
7.  Fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Document No.**|Specifies the document number for the journal line.|  
    |**Account Type**|Select the account type as **Vendor**.|  
    |**Account No.**|Specifies the code of the vendor that you selected in the **Vendor Card** window.|  
    |**Recipient Bank Account**|Specifies the bank account that you have set on the vendor card as the preferred bank.|  
    |**Currency Code**|Specifies the currency code.|  
    |**Amount**|Specifies the total amount including VAT.|  
  
8.  On the **Home** tab, in the **Process** group, choose **Export Payments to File**.  
  
9. In the case of error, review the errors listed in the **Payment File Errors** FactBox, and take the appropriate action.  
  
 You can export a line again if needed. On the **Home** tab, in the Bank group, choose **Export Payments to File**, and then choose **Yes**.  
  
## See Also  
 [How to: Export BACS Files](how-to-export-bacs-files.md)