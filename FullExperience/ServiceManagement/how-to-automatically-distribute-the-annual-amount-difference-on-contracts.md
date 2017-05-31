---
title: "How to: Automatically Distribute the Annual Amount Difference on Contracts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "distribution, annual amount"
  - "service contracts, changing distribution"
ms.assetid: cb84d16d-8e43-4852-9de7-a776ae6682ee
caps.latest.revision: 6
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Automatically Distribute the Annual Amount Difference on Contracts
If you are going to change the annual amount of the service contract or contract quote, you will need to distribute the difference between the new and calculated annual amount values on the contract lines.  
  
### To distribute the annual amount difference of a service contract change automatically  
  
1.  In the **Search** box, enter **Service Contracts** or **Service Contract Quotes**, and then choose the related link.  
  
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
 [How to: Change the Annual Amount on Service Contracts or Contract Quotes](../Service/how-to-change-the-annual-amount-on-service-contracts-or-contract-quotes.md)   
 [Distribution Based on Line Amount](../Service/distribution-based-on-line-amount.md)   
 [Distribution Based on Profit](../Service/distribution-based-on-profit.md)   
 [Even Distribution](../Service/even-distribution.md)   
 [How to: Manually Distribute the Annual Amount Difference on Contracts](../Service/how-to-manually-distribute-the-annual-amount-difference-on-contracts.md)