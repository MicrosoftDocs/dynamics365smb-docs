---
    title: How to Generate Domiciliation Suggestions
    description: After you have set up domiciliations, you can start generating domiciliation suggestions. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can only create domiciliation suggestions for domestic customers.

    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Generate Domiciliation Suggestions
After you have set up domiciliations, you can start generating domiciliation suggestions. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can only create domiciliation suggestions for domestic customers.  

## To generate domiciliation suggestions  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Domiciliation Journal**, and then choose the related link.  
2.  In the **Batch Name** field, select the required journal batch, and then choose the **Suggest Domiciliations** action.  
3.  On the **Options** FastTab, fill in the fields as displayed in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Due Date**|Enter the due date to be included in the batch job. Only entries that have a due date before or on this date will be included.|  
    |**Take Payment Discounts**|Select if you want the batch job to include customer ledger entries for which you can receive a payment discount.|  
    |**Payment Discount Date**|Enter the date that will be used to calculate the payment discount.|  
    |**Select Possible Refunds**|Select if you want the batch job to include refunds.|  
    |**Posting Date**|Enter the date that will appear as the posting date on the lines that the batch job inserts in the domiciliation journal.|  

4.  On the **Customer** FastTab, enter any additional filter criteria.  
5.  Choose the **OK** button.  

When the batch job is finished, the domiciliation journal contains all open customer ledger entries that match the filters.  

> [!NOTE]  
>  The domiciliation suggestions will only include customers who have a Domiciliation number set up. For more information, see [Set Up Domiciliations](how-to-set-up-domiciliations.md).  

## See Also  
 [Belgian Electronic Banking](belgian-electronic-banking.md)   
 [Direct Debit Using Domiciliation](direct-debit-using-domiciliation.md)   
 [Set Up Domiciliations](how-to-set-up-domiciliations.md)   
 [Test Domiciliations](how-to-test-domiciliations.md)   
 [Edit and Delete Domiciliation Lines](how-to-edit-and-delete-domiciliation-lines.md)   
 [Export and Post Domiciliations](how-to-export-and-post-domiciliations.md)
