---
title: Create Payment Slips [FR]
description: Learn ho to create payments slips to manage vendor and customer payments in the French version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: create payment slips, vendor paymnt slip, French version
ms.search.form: 10868, 10870, 10860, 10861, 10864, 10865, 10866, 10871, 10872, 10873, 10874, 10877, 10878, 10879, 10869, 10867, 10882, 10880
ms.date: 04/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create payment slips

You can create payments slips to manage vendor and customer payments. Before you create payment slips, you must set up payment classes. Learn more in [Set Up Payment Classes](how-to-set-up-payment-classes.md).  

The following procedure describes how to create payment slips for vendor payments, but the same steps also apply to creating payment slips for customer payments.  

## Create a payment slip for vendors  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Slips**, and then choose the relevant link.  
1. Choose the **New** action.  
1. On the **Payment Slip** page, choose a field to open the **Payment Class List** page.  
1. Select a payment class, and then choose the **OK** button.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Currency Code**|Specify the currency code to be used for the payment lines.|  
    |**Posting Date**|Specify the posting date.|  
    |**Document Date**|Specify the document date.|  
    |**Amount (LCY)**|The total amount from the payment lines. This field is updated automatically when the net line amounts are changed.<br><br/>|  

1. On the **Lines** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Account Type**|The account type to which the payment line is posted.|  
    |**Account No.**|The unique identification number for the account to which the entry is posted.|  

1. In the **Bank Account Code** field, select a bank name from the list, and then choose **Advanced**.  
1. Optionally, for SEPA, on the **Select – Vendor Account List** page, and then choose the **Edit** action.  

   Fill in the following fields if needed:  

    - **Country/Region Code**. In the list, choose **Advanced**, and make sure that the **SEPA Allowed** check box is selected for the code that you select.  
    - **Swift Code**  
    - **IBAN**  

    Choose the **OK** button to close the page.  

1. Optionally, for SEPA, choose the **Header RIB** action. Select the **Bank Country/Region Code** field, and then choose **Advanced**. Make sure the **SEPA Allowed** checkbox is selected. Also make sure that the **IBAN** and **SWIFT Code** fields are filled in.  

1. Choose the **Suggest Vendor Payments** action.  

    > [!NOTE]  
    > You can also manually fill in the payment lines.  

1. In the **Suggest Vendor Payments** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Last Payment Date**|The last payment date for the vendor ledger entries that are to be included in the batch job.|  
    |**Find Payment Discounts**|Select to include vendor ledger entries for which you can receive a payment discount.|  
    |**Summarize per**|The criteria for summarizing the payment line.|  
    |**Use Vendor Priority**|Select to sort the suggested payments based on the value in the **Priority** field on the vendor cards. Learn more in [Priority](../../purchasing-how-prioritize-vendors.md).|  
    |**Available Amount (LCY)**|The maximum amount that is available for payments in local currency.|  
    |**Currency Filter**|The code for the currency to be included in the batch job.|  

1. On the **Vendor** FastTab, select the appropriate filters.  
1. Choose the **OK** button.  

   The payment lines are automatically created.  

1. On the **Payment Slip** page, on the **Posting** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Source Code**|The source code for the payment slip.|  
    |**Department Code**|The relevant dimension code.|  
    |**Project Code**|The relevant dimension code.|  
    |**Account Type**|The account type to which or from which the payments is transferred.|  
    |**Account No.**|The account number to which or from which the payments is transferred.|  

1. Optionally, for SEPA, in the **Account No.** field, choose the **Advanced** option.  

    1. On the **Bank Account List** page, choose the **Edit** action.  
    1. Fill in the following fields if needed:  

        - **General** FastTab  
        - **Country/Region Code**  
        - **Transfer**  FastTab  
        - **Swift Code**  
        - **IBAN**  
        - **RIB** FastTab  
        - **Payment Export Format**: SEPA  
        - **SEPA CT Msg. ID No. Series**: Bank  

1. Choose the **OK** button.  

After you create a payment slip, you can generate payment files and send them to the bank electronically.  

> [!NOTE]  
> A payment file can be created if the payment slip displays **File** for the **Action Type** field.

## Create a payment file  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Slips**, and then choose the relevant link.  
1. Select a payment slip, and then choose the **Edit** action.  
1. On the **Payment Slip** page, choose the **Generate file** action.  
1. Choose the **Yes** button, and then choose the **OK** button.  

   The payment file is generated and exported according to the export type that is specified on the **Payment Step** page.  

1. In the case of error, review the errors listed in the **File Export Errors** FactBox, and take the appropriate action.  

## Related information

- [Payment Management](payment-management.md)   
- [Set Up Payment Classes](how-to-set-up-payment-classes.md)   
- [Set Up Payment Statuses](/dynamics365/business-central/LocalFunctionality/France/how-to-set-up-payment-classes)   
- [Set Up Payment Steps](/dynamics365/business-central/LocalFunctionality/France/how-to-set-up-payment-classes)   
- [Set Up Payment Addresses](how-to-set-up-payment-addresses.md)   
- [Post Payment Slips](how-to-post-payment-slips.md)   
- [Archive Payment Slips](how-to-archive-payment-slips.md)   
- [Export or Import Payment Management Setup Parameters](how-to-export-or-import-payment-management-setup-parameters.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
