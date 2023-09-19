---
title: Set Up Payment Terms (IT)
description: In the Italian version of Business Central, for each payment term, you can specify if the payment can be made in installments. 
author: brentholtorf
ms.topic: conceptual
ms.search.keywords:
ms.search.form: 12170, 12171, 12172, 12173, 12174
ms.date: 04/01/2021
ms.author: bholtorf
---
# Set Up Payment Terms in the Italian Version

Payment terms determine how you manage due dates and payment discounts. For each payment term, you can specify if the payment can be made in installments. For example, you can define that a payment can be made in three installments with a third of the payment due after 30, 60, and 90 days.  

If a payment term must be paid in one installment, you must still specify how the due date will be calculated.  

When you first sign up for [[!INCLUDE [prod_short](../../includes/prod_short.md)], the demonstration company provides a few payment methods that businesses often use. You can, however, add as many as you need.

## To set up payment terms

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Terms**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]  
3. Choose the **Calculation** action.  
4. On the **Payment Terms Lines** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payment %**|Specify the percentage of the total payment that this installment is for.<br /><br /> For example, if the payment must be made in one installment, enter **100**.|  
    |**Due Date Calculation**|Specify the formula that is used to calculate the date that a payment must be made.<br /><br /> For example, if the payment must be made in one installment after two weeks, enter **14D**. For more information, see [Use Date Formulas](../../ui-enter-date-ranges.md#use-date-formulas)|  
    |**Discount Date Calculation**|Specify the formula that is used to calculate the date that a payment must be made in order to obtain a discount.|  
    |**Discount %**|Specify the discount percentage that is applied for early payment of an invoice amount.|  

5. Choose the **OK** button.  

The **Payment Nos.** field on the **Payment Terms** page is updated. The payment terms that you set here will be a reference for automatic due date calculation for documents that you post for relevant customers and vendors.  

After you set up the payment terms, you assign them to customers and vendors. Optionally, assign payment terms to your payment methods.  

## See Also

[Set Up Payment Terms in the Italian Version](../../finance-payment-terms.md)  
[Defining Payment Methods](../../finance-payment-methods.md)  
[Setting Up Finance](../../finance-setup-finance.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]