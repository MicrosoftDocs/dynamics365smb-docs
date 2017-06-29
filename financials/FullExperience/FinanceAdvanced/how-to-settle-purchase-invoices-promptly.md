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
# How to: Settle Purchase Invoices Promptly
If you need to pay the vendor by cash or check, you can have the necessary posting done at the same time that you post the invoice itself.  
  
### To settle purchase invoices promptly  
  
1.  In the **Search** box, enter **Purchase Invoices**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  To pay either in cash or by bank transfer, enter the number of the general ledger cash account or the bank account in the **Bal. Account No.** field.  
  
    > [!IMPORTANT]  
    >  The **Bal. Account Type** and **Bal. Account No.** fields are not included in the standard layout of the invoice header. In order to post the payment of an invoice, you must first insert them with the design facilities.  
  
> [!NOTE]  
>  If you frequently pay purchase invoices in cash, it is a good idea to set up a specific payment method with a balancing account and enter this method in the **Payment Method** field on the vendor card. The balancing account number is inserted automatically on the invoice header every time you create a new invoice.  
  
## See Also  
 [How to: Post Purchase Invoices](../FullExperience/how-to-post-purchase-invoices.md)   
 [Process Purchases](../FullExperience/process-purchases.md)