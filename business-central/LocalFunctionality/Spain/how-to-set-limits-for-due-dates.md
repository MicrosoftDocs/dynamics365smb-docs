---
    title: How to Set Limits for Due Dates
    description: You can modify payment terms to have limits for the maximum number of days that can be between a delivery and the corresponding payment.

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
# Set Limits for Due Dates
You can modify payment terms to have limits for the maximum number of days that can be between a delivery and the corresponding payment.  

Legal limits for the gap between delivery and payment determine how due dates are calculated. For example, if you create a payment term that will be used for sales to the public sector, the **Max. No. of Days till Due Date** field for that payment term must be set to 30 days.  

## To set limits for due dates on payment terms  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Terms**, and then choose the related link.  
2.  Select the payment term that you want to modify, and then, in the **Max. No. of Days till Due Date** field, specify the number of calendar days to allow between delivery and payment.  

Next, you must make sure that you specify the appropriate payment terms for your public and private customers and vendors. When you create a document for that customer or vendor, the due date for the payment is calculated from the day that the customer received the items or services. Then, you must update the **Document Date** field for the document with the date of the receipt. For example, if you update a sales invoice when you are informed of delivery, the due date is calculated based on the new document date that you specified. The calculated due date cannot be further away than the limit that you specified for the payment term.  

> [!IMPORTANT]  
>  You cannot post a document that creates a bill where one or more installments have a due date that is later than the limit that is specified in the **Max. No. of Days till Due Date** field.  

## See Also  
 [Calculating Due Dates](calculating-due-dates.md)
