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
# How to: Change the Annual Amount on Service Contracts or Contract Quotes
You can change the annual amount of the service contract or contract quote to correct the amount that will be invoiced annually.  
  
### To change the annual amount of the service contract or contract quote  
  
1.  In the **Search** box, enter **Service Contracts** or **Service Contract Quotes**, and then choose the related link.  
  
2.  Select the contract or contract quote you want to change the annual amount for.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Open Contract** to open the contract or contract quote for editing.  
  
4.  On the **Invoice Details** FastTab, select the check box in the **Allow Unbalanced Amounts** field if you want to change the annual amount and distribute the annual amount difference manually on the contract lines. Otherwise, clear the check box in the **Allow Unbalanced Amounts** field to automatically distribute the annual amount difference on the contract lines after you change the annual amount.  
  
5.  Change the contents of the **Annual Amount** field as you need. It is not possible either to sign, that is, convert into a service contract if you are working on a contract quote, or to lock a service contract that has a negative annual amount. If you set the annual amount to zero, the contents of the **Invoice Period** field must be **None** when either signing or locking the service contract.  
  
6.  Depending on whether the check box in the **Allow Unbalanced Amounts** field is selected or not, run either the manual or automatic distribution of the annual amount difference. As a result, the contract lines will be updated in a way so that the **Calcd. Annual Amount** field value is equal to the new annual amount.  
  
## See Also  
 [How to: Automatically Distribute the Annual Amount Difference on Contracts](../Service/how-to-automatically-distribute-the-annual-amount-difference-on-contracts.md)   
 [Distribution Based on Line Amount](../Service/distribution-based-on-line-amount.md)   
 [Distribution Based on Profit](../Service/distribution-based-on-profit.md)   
 [Even Distribution](../Service/even-distribution.md)   
 [How to: Manually Distribute the Annual Amount Difference on Contracts](../Service/how-to-manually-distribute-the-annual-amount-difference-on-contracts.md)