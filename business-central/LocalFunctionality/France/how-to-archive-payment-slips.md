---
    title: How to Archive Payment Slips
    description: When a payment slip has been processed, you can separate it from the active payment slips by archiving it.

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
# Archive Payment Slips
When a payment slip has been processed, you can separate it from the active payment slips by archiving it.  

You can archive the payment slip by using the following methods:  

- Manually – for individual payment slips.  
- Automatically – for a batch of payment slips.  

## To archive a payment slip  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Slips**, and then choose the relevant link.  
2.  Select the relevant payment slip, and then choose the **Edit** action.  
3.  On the **Payment Slip** page, choose the **Archive** action.  
4.  Choose the **Yes** button to archive the payment slip.  

    > [!NOTE]  
    >  If the current status of the payment slip does not allow archiving, a message is displayed.  

## To archive a batch of payment slips  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Archive Payment Slips**, and then choose the relevant link.  
2.  On the **Archive Payment Slips** page, on the **Payment Header** FastTab, select the appropriate filters.  
3.  Choose the **OK** button.  

The payment slips are archived.  

> [!NOTE]  
>  This batch job will only archive payment slips that have the **Archiving Authorized** check box selected on the **Payment Status** page. For more information, see [Set Up Payment Statuses](how-to-set-up-payment-statuses.md).  

## See Also  
 [Payment Management](payment-management.md)   
 [Set Up Payment Classes](how-to-set-up-payment-classes.md)   
 [Set Up Payment Statuses](how-to-set-up-payment-statuses.md)   
 [Set Up Payment Steps](how-to-set-up-payment-steps.md)   
 [Set Up Payment Addresses](how-to-set-up-payment-addresses.md)   
 [Create Payment Slips](how-to-create-payment-slips.md)   
 [Post Payment Slips](how-to-post-payment-slips.md)
