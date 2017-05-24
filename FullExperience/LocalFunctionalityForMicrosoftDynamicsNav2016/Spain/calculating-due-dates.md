---
title: "Calculating Due Dates"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "due dates, about"
  - "prompt payments"
ms.assetid: ab2b8136-f9f2-4325-b599-f75c2d33296a
caps.latest.revision: 9
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# Calculating Due Dates
In Spain, there is a legal limit for the number of days that a payment can be delayed. You must submit an annual report of purchases and sales for payments that were made before or after the due date. The legal requirements depend on whether the customer is a private company or a public administration. For more information, see the official declaration [BOE\-A\-2010\-10708](http://go.microsoft.com/fwlink/?LinkId=224630) on the Boletín Oficial del Estado website.  
  
## Payment Terms  
 To help you meet the legal requirements, you can set up payment terms so that the due dates are calculated correctly. This includes specifying the maximum number of calendar days that a payment can be delayed after delivery. For example, you can create separate payment terms for sales to the public sector and sales to private companies. The following table illustrates how you can set up payment terms.  
  
|[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|Public sector|Private company|  
|---------------------------------|-------------------|---------------------|  
|**\($ T\_3\_1 Code $\)**|**1M\(8D\) PUB**|**1M\(8D\) PRI**|  
|**\($ T\_3\_2 Due Date Calculation $\)**|**1M**|**1M**|  
|**\($ T\_3\_10710 Max. No. of Days till Due Date $\)**|**30**|**60**|  
  
 For each customer and vendor, you must select the appropriate payment term code. Then, when you create a document for that customer or vendor, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] will calculate a due date that does not exceed the limit for the relevant payment term.  
  
> [!IMPORTANT]  
>  You cannot post a document that creates a bill where one or more installments have a due date that is later than the limit that is specified in the **\($ T\_3\_10710 Max. No. of Days till Due Date $\)** field.  
  
 If a due date cannot be calculated based on the limit, the due date is set to blank. For example, if the calculated due date falls in a non\-payment period and there is no available date before that period, you must specify a due date manually. You cannot post a document that has an empty due date.  
  
 You can change the calculated due date manually, but you cannot make it later than the limit that you specify for the payment term. For example, the due date can be calculated to be very late because of conflicts with non\-payment periods. In that case, you can decide to make the due date earlier than the non\-payment period.  
  
## Overdue Payments  
 You must include information about overdue payments in the annual reports for the government. [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes two reports to help you identify overdue payments from customers and payments that you are late in making.  
  
 The **\($ R\_10747 Customer \- Overdue Payments $\)** and **\($ R\_10748 Vendor \- Overdue Payments $\)** reports include a section for each customer or vendor that lists the payments with the following information:  
  
-   Invoice number  
  
-   Invoice description  
  
-   Document number  
  
-   Posting date  
  
-   Due date  
  
-   Days overdue  
  
-   Currency code  
  
-   Amount  
  
-   Amount in the local reporting currency \(LCY\)  
  
 Each section has a summary section with the following information.  
  
|Information|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|-----------------|---------------------------------------|  
|Weighted average term exceeded|This formula is calculated based on the number of posted payments for the specified period, the number of days that payments were delayed, and the paid amount in \(LCY\). For more information, see the official declaration [BOE\-A\-2010\-10708](http://go.microsoft.com/fwlink/?LinkId=224630) on the Boletín Oficial del Estado website.|  
|Payments within the legal limit|The amounts in LCY and the percentage of the total payments that were made before the maximum allowed due date for each transaction.|  
|Payments outside the legal limit|The amounts in LCY and the percentage of the total payments that were made after the maximum allowed due date for each transaction.|  
  
 At the end of these reports, there is a section that summarizes this information for all payments. These reports will show information based on applied detailed customer ledger entries or applied detailed vendor ledger entries. The information is based on the date filters that you specify. For more information, see [\($ R\_10747 Customer \- Overdue Payments $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-r_10747-customer-overdue-payments-$-.md) and [\($ R\_10748 Vendor \- Overdue Payments $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-r_10748-vendor-overdue-payments-$-.md).  
  
## See Also  
 [How to: Set Limits for Due Dates](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-set-limits-for-due-dates.md)   
 [How to: Set Up Payment Terms](../../Finance/how-to-set-up-payment-terms.md)   
 [Apply Purchase Transactions](../../Finance/apply-purchase-transactions.md)   
 [Apply Sales Transactions](../../Finance/apply-sales-transactions.md)   
 [\($ R\_10747 Customer \- Overdue Payments $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-r_10747-customer-overdue-payments-$-.md)   
 [\($ R\_10748 Vendor \- Overdue Payments $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-r_10748-vendor-overdue-payments-$-.md)