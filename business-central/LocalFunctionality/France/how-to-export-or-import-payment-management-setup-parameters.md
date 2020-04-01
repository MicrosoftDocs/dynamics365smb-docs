---
    title: How to Export or Import Payment Management Setup Parameters
    description: You can export or import payment management setup parameters to an external disk so that you can use the same parameters for another company with similar requirements.

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
# Export or Import Payment Management Setup Parameters
You can export or import payment management setup parameters to an external disk so that you can use the same parameters for another company with similar requirements.  

You can use the following formats to export payment setup parameters:  

- ETEBAC (XMLport 10860) – To create a bill of exchange remittance.  
- Withdraw (XMLport 10861) – To create a customer payment withdrawal (direct debit).  
- Transfer (XMLport 10862) – To create a vendor payment transfer (credit transfer).  

You can select these formats when you set up the payment status for your payment class. For more information, see [Set Up Payment Classes](how-to-set-up-payment-classes.md).  

## To export or import payment management setup parameters  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Slip Setup**, and then choose the relevant link.  
2.  On the **Payment Class** page, choose the **Export Parameters** action.  

    To import a parameter, choose the **Import Parameter** action, select the file, and then choose the **Open** button.  

3.  Choose the **Save** button to open the **Save As** page and navigate to the location where the file should be saved.  
4.  Choose the **OK** button.  

## See Also  
 [Payment Management](payment-management.md)   
 [Set Up Payment Classes](how-to-set-up-payment-classes.md)   
 [Set Up Payment Statuses](how-to-set-up-payment-statuses.md)   
 [Set Up Payment Steps](how-to-set-up-payment-steps.md)   
 [Set Up Payment Addresses](how-to-set-up-payment-addresses.md)   
 [Create Payment Slips](how-to-create-payment-slips.md)   
 [Archive Payment Slips](how-to-archive-payment-slips.md)
