---
    title: Setting Up Payment Terms
    description: For each payment term, you can specify if the payment can be made in installments. For example, you can define that a payment can be made in three installments with a third of the payment due after 30, 60, and 90 days.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 02/27/2018
    ms.author: sgroespe

---
# Set Up Payment Terms
For each payment term, you can specify if the payment can be made in installments. For example, you can define that a payment can be made in three installments with a third of the payment due after 30, 60, and 90 days.  

If a payment term must be paid in one installment, you must still specify how the due date will be calculated.  

## To set up payment terms  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Terms**, and then choose the related link.    
2.  Fill in the fields in the **Payment Terms** window. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]  
3.  Choose the **Calculation** action.  
4.  In the **Payment Terms Lines** window, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payment %**|Specify the percentage of the total payment that this installment is for.<br /><br /> For example, if the payment must be made in one installment, enter **100**.|  
    |**Due Date Calculation**|Specify the formula that is used to calculate the date that a payment must be made.<br /><br /> For example, if the payment must be made in one installment after two weeks, enter **14D**. For more information, see the "Using Date Formulas" section in [Entering Data](../../ui-enter-data.md)|  
    |**Discount Date Calculation**|Specify the formula that is used to calculate the date that a payment must be made in order to obtain a discount.|  
    |**Discount %**|Specify the discount percentage that is applied for early payment of an invoice amount.|  

5.  Choose the **OK** button.  

The **Payment Nos.** field in the **Payment Terms** window is updated. The payment terms that you set here will be a reference for automatic due date calculation for documents that you post for relevant customers and vendors.  

## See Also  
 [How to: Set Up Automatic Payments and Automatic Bills](how-to-set-up-automatic-payments-and-automatic-bills.md)   
 [Italy Local Functionality](italy-local-functionality.md)   
