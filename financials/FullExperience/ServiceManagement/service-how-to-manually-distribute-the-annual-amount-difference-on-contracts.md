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
# How to: Manually Distribute the Annual Amount Difference on Contracts
If you are going to change the annual amount of the service contract or contract quote, you will need to distribute the difference between the new and calculated annual amount values on the contract lines. You can distribute the difference manually or automatically.  
  
### To distribute the annual amount difference manually  
  
1.  In the **Search** box, enter **Service Contracts** or **Service Contract Quotes**, and then choose the related link.  
  
2.  Open the relevant service contract or service contract quote card.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Open Contract** to open the contract or contract quote for editing.  
  
4.  On the **Invoice Details** FastTab, select the **Allow Unbalanced Amounts** field.  
  
5.  Change the contents of the **Annual Amount** field according to your needs. It is not possible either to sign or to lock the service contract if it has a negative annual amount. If the annual amount is equal to zero, the contents of the **Invoice Period** field must be **None** when either signing or locking the service contract.  
  
6.  On the **Lines** FastTab, modify the values in the **Line Amount** field on the contract lines. Note that the contents in the **Calcd. Annual Amount** field is updated as soon as you change any line amount on the contract lines. The distribution is completed when the value in the **Calcd. Annual Amount** field is equal to the new annual amount.  
  
## See Also  
 [How to: Automatically Distribute the Annual Amount Difference on Contracts](../how-to-automatically-distribute-the-annual-amount-difference-on-contracts.md)   
 [How to: Automatically Distribute the Annual Amount Difference on Contracts](../how-to-automatically-distribute-the-annual-amount-difference-on-contracts.md)   
 [How to: Change the Annual Amount on Service Contracts or Contract Quotes](../how-to-change-the-annual-amount-on-service-contracts-or-contract-quotes.md)   
 [Distribution Based on Line Amount](../distribution-based-on-line-amount.md)   
 [Distribution Based on Profit](../distribution-based-on-profit.md)   
 [Even Distribution](../even-distribution.md)