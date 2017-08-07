---
    title: How to: Automatically Distribute the Annual Amount Difference on Contracts | Microsoft Docs
    description: If you are going to change the annual amount of the service contract or contract quote, you will need to distribute the difference between the new and calculated annual amount values on the contract lines.
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
# How to: Automatically Distribute the Annual Amount Difference on Contracts
If you are going to change the annual amount of the service contract or contract quote, you will need to distribute the difference between the new and calculated annual amount values on the contract lines.  
  
### To distribute the annual amount difference of a service contract change automatically  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contracts** or **Service Contract Quotes**, and then choose the related link.  
  
2.  Select the relevant contract or contract quote. Open the **Service Contract** or **Contract Quote** card window containing information for this service contract or contract quote.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Open Contract** to open the contract or contract quote for editing.  
  
4.  On the **Invoice Details** FastTab, clear the check box in the **Allow Unbalanced Amounts** field.  
  
    > [!NOTE]  
    >  If the contract or contract quote was already opened and the **Annual Amount** field value is not equal to the **Calcd. Annual Amount** field value, skip the next step. The contract or contract quote was already opened if its **Change Status** field value is set to **Open**.  
  
5.  Change the contents of the **Annual Amount** field according to your needs. It is not possible either to sign, that is, convert into a service contract if you are working on a contract quote, or lock the service contract or contract quote if it has a negative annual amount. If you set the annual amount to zero, the contents of the **Invoice Period** field should be **None** when either signing the service quote or locking the service contract.  
  
6.  A dialog box with three options will open. Choose one of the options corresponding to the automatic distribution methods you prefer:  even distribution,  distribution based on profit, or distribution based on line amount.  
  
7.  Choose the **OK** button.  
  
     The value in the **Calcd. Annual Amount** field and the line amounts on the contract lines are updated. This means that the annual amount difference has been successfully distributed.  
  
## See Also  
 [How to: Change the Annual Amount on Service Contracts or Contract Quotes](../how-to-change-the-annual-amount-on-service-contracts-or-contract-quotes.md)   
 [Distribution Based on Line Amount](../distribution-based-on-line-amount.md)   
 [Distribution Based on Profit](../distribution-based-on-profit.md)   
 [Even Distribution](../even-distribution.md)   
 [How to: Manually Distribute the Annual Amount Difference on Contracts](../how-to-manually-distribute-the-annual-amount-difference-on-contracts.md)