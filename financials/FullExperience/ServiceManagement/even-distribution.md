---
title: "Even Distribution"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "distribution, even"
  - "service contracts, changing distribution"
ms.assetid: 1cc06620-d1c4-4e2d-bfff-5aafa18c8e10
caps.latest.revision: 8
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
# Even Distribution
If you change the annual amount of the service contract or contract quote, you may want to distribute the difference between its new and calculated annual amounts on the contract lines. Even distribution is one of the automatic distribution methods that can help you spread equally the new and calculated annual amounts difference between line amounts on the contract lines. The following list of distribution procedure steps describe the main idea of this method:  
  
1.  The difference between the new **Annual Amount** and **Calcd. Annual Amount** field values is divided by the number of the contract lines in the service contract or contract quote.  
  
2.  The **Line Amount** field value is updated by adding the result of the previous operation.  
  
3.  The contents in the **Line Discount Amount**, **Line Discount %**, and **Profit** fields are updated with regard to the new value in the **Line Amount** field in the following way:   
    Line Discount Amount \= Line Value \- Line Amount.  
    Line Discount % \= Line Discount Amount \/ Line Value \* 100.  
    Profit \= Line Amount \- Line Cost.  
  
 The steps are repeated for each contract line.  
  
## Example  
 The **Allow Unbalanced Amounts** check box is not selected in the service contract that contains three contract lines with such information.  
  
|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|30.00|40.00|0.00|0.00|40.00|10.00|  
|Item 2|40.00|50.00|10.00|5.00|45.00|5.00|  
|Item 3|50.00|70.00|10.00|7.00|63.00|13.00|  
  
 The **Annual Amount** field value is equal to the contents of the **Calcd. Annual Amount** field, which is always set to the sum of the line amounts. In this case, it is equal to the following:  40 \+ 45 \+ 63 \= 148.  
  
 If you change the **Annual Amount** to 139, the amount is calculated that should be added to each **Line Amount** field value. This amount is calculated by subtracting the **Calcd. Annual Amount** from the new **Annual Amount** field value and dividing the result by the number of the contract lines in the service contract. In this case, it will be equal to the following: \(139 \- 148\) \/ 3 \= \-3. Then, the last calculated figure is added to each **Line Amount** field value and the **Line Discount %**, **Line Discount Amount**, and **Profit** field values are updated using the formulas in the procedure described above.  
  
 Finally, the contract lines will contain this data.  
  
|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|30.00|40.00|7.50|3.00|37.00|7.00|  
|Item 2|40.00|50.00|16.00|8.00|42.00|2.00|  
|Item 3|50.00|70.00|14.29|10.00|60.00|10.00|  
  
## See Also  
 [How to: Automatically Distribute the Annual Amount Difference on Contracts](../Service/how-to-automatically-distribute-the-annual-amount-difference-on-contracts.md)   
 [How to: Change the Annual Amount on Service Contracts or Contract Quotes](../Service/how-to-change-the-annual-amount-on-service-contracts-or-contract-quotes.md)   
 [Distribution Based on Line Amount](../Service/distribution-based-on-line-amount.md)   
 [Distribution Based on Profit](../Service/distribution-based-on-profit.md)   
 [How to: Manually Distribute the Annual Amount Difference on Contracts](../Service/how-to-manually-distribute-the-annual-amount-difference-on-contracts.md)   
 Line Amount   
 Calcd. Annual Amount   
 Annual Amount