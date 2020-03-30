---
    title: How to Settle Purchase Invoices Promptly | Microsoft Docs
    description: If you need to pay the vendor by cash or check, you can have the necessary posting done when you post the invoice.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Settle Purchase Invoices Promptly
If you need to pay the vendor by cash or check, you can post the payment when you post the invoice.  

### To settle purchase invoices promptly  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2. Choose the **New** action.  
3.  To pay either in cash or by bank transfer, enter the number of the general ledger cash account or the bank account in the **Bal. Account No.** field.  

> [!IMPORTANT]  
>  The **Bal. Account Type** and **Bal. Account No.** fields are not included in the standard layout of the invoice header. In order to post the payment of an invoice, you must first insert them with the design facilities. For more information, see [Personalize Your Workspace](ui-personalization-user.md). 

> [!NOTE]  
>  If you frequently pay purchase invoices in cash, it is a good idea to set up a specific payment method with a balancing account and enter this method in the **Payment Method** field on the vendor card. The balancing account number is inserted automatically on the invoice header every time you create a new invoice.  

## See Also  
[Managing Payables](payables-manage-payables.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
