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
# How to: Correct Prepayments
You can make a correction to an order after you have posted a prepayment invoice for the order. You can add new lines to an order after issuing a prepayment, and then you can post another prepayment invoice, but you cannot delete a line from an order after a prepayment has been invoiced for the line.  
  
### To correct a prepayment  
  
1.  Issue a prepayment credit memo to cancel all invoiced prepayments for an order.  
  
2.  In the **Search** box, enter **Sales Orders**, and then choose the related link.  
  
3.  Open the relevant sales order. On the **Actions** tab, in the **Posting** group, choose **Prepayment**, and then choose **Post Prepayment Credit Memo** or **Post and Print Prepmt. Cr. Memo**.  
  
4.  Recreate the correct entries.  
  
5.  Reduce the amount in the **Line Amount** field if you want to reduce the quantity on the line. However, you must first increase the prepayment percentage on the line so that the **Prepmt. Line Amount** is not decreased below the **Prepmt. Amt. Inv.**.  
  
6.  Add new lines to the order after issuing a prepayment.  
  
7.  To make a prepayment invoice for the new lines, on the  **Actions** tab, in the **Posting** group, choose **Prepayment**, and then choose **Post Prepayment Invoice** or **Post and Print Prepmt. Invoice**.  
  
8.  Issue an additional prepayment invoice. To do this, increase the prepayment amount on one or more lines and post the prepayment invoice. A new invoice will be created for the difference between the prepayment amounts invoiced and the new prepayment amounts.  
  
## See Also  
 [How to: Create Prepayment Invoices](../how-to-create-prepayment-invoices.md)   
 [How to: Define Prepayment Percentages](../how-to-define-prepayment-percentages.md)