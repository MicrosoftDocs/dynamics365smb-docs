---
title: "Distribution Based on Profit"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "distribution, based on profit"
  - "service contracts, changing distribution"
ms.assetid: 6751903b-6214-4e53-b358-ecdb83d47023
caps.latest.revision: 9
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
# Distribution Based on Profit
If you change the annual amount of the service contract or contract quote, you may want to distribute the difference between its new and calculated annual amounts on the contract lines. Distribution Based on Profit is one of the automatic methods that can help you spread the new and calculated annual amounts difference between the line amounts on the contract lines. This distribution will be performed proportionally to their profit shares in the total contract or contract quote profit. The following list of distribution procedure steps for each contract line describe the main idea of this method:  
  
1.  The profit percentage contribution is calculated as follows: the contents of the **Profit** field is divided by the sum of **Profit** field values on all contract lines.  
  
2.  The **Line Amount** field value is updated by adding to it the difference between the new and calculated annual amounts, which is multiplied by the profit percentage contribution.  
  
3.  The contents in the Line Discount Amount, Line Discount %, and Profit fields are updated with regard to the new value in the **Line Amount** field in the following way:  
  
    -   Line Discount Amount \= Line Value \- Line Amount  
  
    -   Line Discount % \= Line Discount Amount \/ Line Value \* 100  
  
    -   Profit \= Line Amount \- Line Cost  
  
 The steps are repeated for each contract line.  
  
## Example  
 The **Allow Unbalanced Amounts** check box is not selected in the service contract that contains three contract lines with such information.  
  
|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|20.00|25.00|0.00|0.00|25.00|5.00|  
|Item 2|50.00|58.00|5.00|2.90|55.10|5.10|  
|Item 3|100.00|115.00|2.00|2.30|112.70|12.70|  
  
 The **Annual Amount** field value is equal to the contents of the **Calcd. Annual Amount** field, which is always set to the sum of the line amounts. In this case, it is equal to the following:  25.00 \+ 55.10 \+ 112.70 \= 192.80.  
  
 If you change the **Annual Amount** to 180, the profit percentage contributions for each contract line are calculated:  
  
-   Item 1 – 5 \/ \(5 \+ 5.1 \+1 2.7\) \= 0.2193 %  
  
-   Item 2 – 5.1 \/ \(5 \+ 5.1 \+ 12.7\) \= 0.2237  
  
-   Item 3 – 12.7 \/ \(5 \+ 5.1 \+ 12.7\) \= 0.557  
  
 The **Line Amount** field value is updated on each contract line using the following formula: Line Amount \= Line Amount \+ difference between the new and calculated annual amounts \* Percentage Contribution. After that, the **Line Discount Amount**, **Line Discount %**, and **Profit** field values are updated using the formulas in the step 3 of the procedure described above.  
  
 Finally, the contract lines will contain this data.  
  
|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|20.00|25.00|11.24|2.81|22.19|2.19|  
|Item 2|50.00|58.00|9.93|5.76|52.24|2.24|  
|Item 3|100.00|115.00|8.20|9.43|105.57|5.57|  
  
## See Also  
 [How to: Automatically Distribute the Annual Amount Difference on Contracts](../Service/how-to-automatically-distribute-the-annual-amount-difference-on-contracts.md)   
 [How to: Change the Annual Amount on Service Contracts or Contract Quotes](../Service/how-to-change-the-annual-amount-on-service-contracts-or-contract-quotes.md)   
 [Distribution Based on Line Amount](../Service/distribution-based-on-line-amount.md)   
 [Even Distribution](../Service/even-distribution.md)   
 [How to: Manually Distribute the Annual Amount Difference on Contracts](../Service/how-to-manually-distribute-the-annual-amount-difference-on-contracts.md)   
 [Profit](../Topic/\($%20T_5964_34%20Profit%20$\).md)   
 [Line Amount](../Topic/\($%20T_5964_24%20Line%20Amount%20$\).md)