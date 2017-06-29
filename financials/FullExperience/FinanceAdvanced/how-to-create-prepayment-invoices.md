---
title: "How to: Create Prepayment Invoices"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "prepayments, creating invoices"
  - "installments, payments"
ms.assetid: f15bbc0d-0169-432f-a39f-2b141255dadb
caps.latest.revision: 8
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
---
# How to: Create Prepayment Invoices
If you require your customers to submit payment before you ship an order to them, or if your vendor requires you to submit payment before they ship an order to you, you can use the prepayment functionality.  
  
 After you create a sales or purchase order, you can create a prepayment invoice. You can use the default percentages for each sales or purchase line, or you can adjust the amount as necessary. For example, you can specify a total amount for the entire order.  
  
 The following procedure is for sales orders, but you can follow the same procedure for purchase orders.  
  
### To create a prepayment invoice  
  
1.  In the **Search** box, enter **Sales Orders**, and then choose the related link. Create a new sales order and fill in the header.  
  
2.  On the **Prepayment** FastTab, the **Prepayment %** field will be filled in automatically if there is a default prepayment percentage on the customer card. You can change the contents of the field. The prepayment percentage is only copied from the header to lines that do not copy the default prepayment percentage from the item.  
  
     If the **Compress Prepayment** field is selected, lines will be combined on the invoice if:  
  
    -   They have the same general ledger account for prepayments as determined by the general posting setup.  
  
    -   They have the same dimensions.  
  
         Leave the field blank if you want to specify a prepayment invoice with one line for each sales order line that has a prepayment percentage.  
  
3.  Fill in the sales lines.  
  
     If default prepayment percentages have been set up for your items, they are automatically copied to the **\($ T\_37\_109 Prepayment % $\)** field on the line. Otherwise, the prepayment percentage is copied from the header. You can change the contents of the **\($ T\_37\_109 Prepayment % $\)** field on the line.  
  
4.  If you want to apply one prepayment percentage to the entire order, change the **\($ T\_36\_130 Prepayment % $\)** field on the header after filling in the lines.  
  
5.  To view the total prepayment amount, on the **Navigate** tab, in the **Order** group, choose **Statistics**.  
  
    -   If you want to adjust the total prepayment amount for the order, you can change the contents of the **Prepayment Amount** field in the **Sales Order Statistics** window.  
  
    -   If the **Prices Including VAT** field is selected, the **Prepayment Amount Incl. VAT** field is editable.  
  
    -   If you change the contents of the **Prepayment Amount** field, the amount will be distributed proportionately between all lines, except those that have **0** in the **\($ T\_37\_109 Prepayment % $\)** field.  
  
6.  To print a test report before posting the prepayment invoice, on the **Actions** tab, in the **Posting** group, choose **Prepayment**, and then choose **Prepayment Test Report**.  
  
7.  To post the prepayment invoice, on the **Actions** tab, in the **Posting** group, choose **Prepayment**, and then choose **Post Prepayment Invoice**.  
  
     To post and print the prepayment invoice, choose **Post and Print Prepmt. Invoice**.  
  
 You can issue additional prepayment invoices for the order. To do this, increase the prepayment amount on one or more lines, adjust the document date if necessary, and post the prepayment invoice. A new invoice will be created for the difference between the prepayment amounts invoiced so far and the new prepayment amount.  
  
> [!NOTE]  
>  If you are located in North America, you cannot change the prepayment percentage after the prepayment invoice has been posted. This is prevented in the North American version of FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> because the calculation of sales tax will otherwise be incorrect.  
  
 When you are ready to post the rest of the invoice, post it as you would post any invoice, and the prepayment amount will automatically be deducted from the amount due.  
  
## See Also  
 [How to: Define Prepayment Percentages](../Purchasing/how-to-define-prepayment-percentages.md)   
 [How to: Correct Prepayments](../Finance/how-to-correct-prepayments.md)