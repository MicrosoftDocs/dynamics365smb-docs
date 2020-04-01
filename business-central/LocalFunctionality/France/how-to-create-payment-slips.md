---
    title: How to Create Payment Slips
    description: You can create payments slips to manage vendor and customer payments. Before you create payment slips, you must set up payment classes.

    services: project-madeira 
    documentationcenter: ''
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
# Create Payment Slips
You can create payments slips to manage vendor and customer payments. Before you create payment slips, you must set up payment classes. For more information, see [Set Up Payment Classes](how-to-set-up-payment-classes.md).  

The following procedure describes how to create payment slips for vendor payments, but the same steps also apply to creating payment slips for customer payments.  

## To create a payment slip for vendors  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Slips**, and then choose the relevant link.  
2.  Choose the **New** action.  
3.  On the **Payment Slip** page, choose a field to open the **Payment Class List** page.  
4.  Select a payment class, and then choose the **OK** button.  
5.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Currency Code**|Specify the currency code to be used for the payment lines.|  
    |**Posting Date**|Specify the posting date.|  
    |**Document Date**|Specify the document date.|  
    |**Amount (LCY)**|The total amount from the payment lines. This field is updated automatically when the net line amounts are changed.<br /><br />|  

6.  On the **Lines** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Account Type**|The account type to which the payment line is posted.|  
    |**Account No.**|The unique identification number for the account to which the entry will be posted.|  

7.  In the **Bank Account Code** field, select a bank name from the list, and then choose **Advanced**.  
8.  Optionally, for SEPA, on the **Select – Vendor Account List** page, and then choose the **Edit** action.  

    Fill in the following fields if needed:  

    - **Country/Region Code**. In the list, choose **Advanced**, and make sure that the **SEPA Allowed** check box is selected for the code that you select.  
    - **Swift Code**  
    - **IBAN**  

    Choose the **OK** button to close the page.  

9. Optionally, for SEPA, choose the **Header RIB** action. Select the **Bank Country/Region Code** field, and then choose **Advanced**. Make sure the **SEPA Allowed** check box is selected. Also make sure that the **IBAN** and **SWIFT Code** fields are filled in.  

10. Choose the **Suggest Vendor Payments** action.  

    > [!NOTE]  
    >  You can also manually fill in the payment lines.  

11. In the **Suggest Vendor Payments** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Last Payment Date**|The last payment date for the vendor ledger entries that are to be included in the batch job.|  
    |**Find Payment Discounts**|Select to include vendor ledger entries for which you can receive a payment discount.|  
    |**Summarize per**|The criteria for summarizing the payment line.|  
    |**Use Vendor Priority**|Select to sort the suggested payments based on the value in the **Priority** field on the vendor cards. For more information, see Priority.|  
    |**Available Amount (LCY)**|The maximum amount that is available for payments in local currency.|  
    |**Currency Filter**|The code for the currency to be included in the batch job.|  

12. On the **Vendor** FastTab, select the appropriate filters.  
13. Choose the **OK** button.  

    The payment lines are automatically created.  

14. On the **Payment Slip** page, on the **Posting** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Source Code**|The source code for the payment slip.|  
    |**Department Code**|The relevant dimension code.|  
    |**Project Code**|The relevant dimension code.|  
    |**Account Type**|The account type to which or from which the payments will be transferred.|  
    |**Account No.**|The account number to which or from which the payments will be transferred.|  

15. Optionally, for SEPA, in the **Account No.** field, choose the **Advanced** option.  

    1. On the **Bank Account List** page, choose the **Edit** action.  
    2. Fill in the following fields if needed:  

        - **General** FastTab  
        - **Country/Region Code**  
        - **Transfer**  FastTab  
        - **Swift Code**  
        - **IBAN**  
        - **RIB** FastTab  
        - **Payment Export Format**: SEPA  
        - **SEPA CT Msg. ID No. Series**: Bank  

16. Choose the **OK** button.  

After you create a payment slip, you can generate payment files and send them to the bank electronically.  

> [!NOTE]  
>  A payment file can be created if the payment slip displays **File** for the **Action Type** field.

## To create a payment file  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Slips**, and then choose the relevant link.  
2.  Select a payment slip, and then choose the **Edit** action.  
3.  On the **Payment Slip** page, choose the **Generate file** action.  
4.  Choose the **Yes** button, and then choose the **OK** button.  

    The payment file is generated and exported according to the export type that is specified on the **Payment Step** page.  

5.  In the case of error, review the errors listed in the **File Export Errors** FactBox, and take the appropriate action.  

## See Also  
 [Payment Management](payment-management.md)   
 [Set Up Payment Classes](how-to-set-up-payment-classes.md)   
 [Set Up Payment Statuses](how-to-set-up-payment-statuses.md)   
 [Set Up Payment Steps](how-to-set-up-payment-steps.md)   
 [Set Up Payment Addresses](how-to-set-up-payment-addresses.md)   
 [Post Payment Slips](how-to-post-payment-slips.md)   
 [Archive Payment Slips](how-to-archive-payment-slips.md)   
 [Export or Import Payment Management Setup Parameters](how-to-export-or-import-payment-management-setup-parameters.md)
