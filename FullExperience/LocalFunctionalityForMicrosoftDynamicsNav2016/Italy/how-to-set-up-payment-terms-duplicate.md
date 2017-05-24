---
title: "How to: Set Up Payment Terms-duplicate"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment methods, setting up"
  - "payment terms, setting up"
ms.assetid: 501f9d41-7fb3-4ebc-94c0-41bf62ca5a72
caps.latest.revision: 41
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Set Up Payment Terms-duplicate
For each payment term, you can specify if the payment can be made in installments. For example, you can define that a payment can be made in three installments with a third of the payment due after 30, 60, and 90 days.  
  
 If a payment term must be paid in one installment, you must still specify how the due date will be calculated.  
  
### To set up payment terms  
  
1.  In the **Search** box, enter **\($ N\_4 Payment Terms $\)**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_3\_1 Code $\)**|Specify the unique identification code for the set of payment terms. You can enter a maximum of 10 alphanumeric characters.|  
    |**\($ T\_3\_12170 Payment Nos. $\)**|Specify the number of installments allowed for this payment term.|  
    |**\($ T\_3\_5 Description $\)**|Specify the payment term code description. This description is printed where the payment terms are used.|  
  
3.  On the **Home** tab, in the **Process**, choose **Calculation**.  
  
4.  In the **\($ N\_12170 Payment Terms Lines $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12170\_4 Payment % $\)**|Specify the percentage of the total payment that this installment is for.<br /><br /> For example, if the payment must be made in one installment, specify **100**.|  
    |**\($ T\_12170\_5 Due Date Calculation $\)**|Specify the formula that is used to calculate the date that a payment must be made.<br /><br /> For example, if the payment must be made in one installment after two weeks, specify **14D**. For more information, see [How to: Enter Dates and Times](../../WorkingWithDynamics/how-to-enter-dates-and-times.md).|  
    |**\($ T\_12170\_6 Discount Date Calculation $\)**|Specify the formula that is used to calculate the date that a payment must be made in order to obtain a discount.|  
    |**\($ T\_12170\_7 Discount % $\)**|Specify the discount percentage that is applied for early payment of an invoice amount.|  
  
5.  Choose the **OK** button.  
  
     The **\($ T\_3\_12170 Payment Nos. $\)** field in the **\($ N\_4 Payment Terms $\)** window is updated. The payment terms that you set here will be a reference for automatic due date calculation for documents that you post for relevant customers and vendors.  
  
## See Also  
 [How to: Set Up Automatic Payments and Automatic Bills](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-set-up-automatic-payments-and-automatic-bills.md)   
 [\($ N\_4 Payment Terms $\)](../Topic/\($%20N_4%20Payment%20Terms%20$\).md)   
 [Italy Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/italy-local-functionality.md)