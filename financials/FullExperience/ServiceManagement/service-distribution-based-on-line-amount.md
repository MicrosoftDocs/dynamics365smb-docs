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
# Distribution Based on Line Amount
If you change the annual amount of the service contract or contract quote, you may want to distribute the difference between its new and calculated annual amounts on the contract lines. Distribution Based on Line Amount is an automatic method that can help you spread the new and calculated annual amounts difference between the line amounts on the contract lines. This distribution will be performed proportionally to their line amount shares in the calculated annual amount. The following list of distribution procedure steps for each contract line describe the main idea of this method:  
  
1.  The line amount percentage contribution is calculated as follows: the contents of the **Line Amount** field is divided by the **Calcd. Annual Amount** field values on all contract lines.  
  
2.  The **Line Amount** field value is updated by adding to it the difference between the new and calculated annual amounts, which is multiplied by the line amount percentage contribution.  
  
3.  The contents in the **Line Discount Amount**, **Line Discount %**, and **Profit** fields are updated with regard to the new value in the **Line Discount Amount** field in the following way:  
  
    -   Line Discount Amount \= Line Value - Line Amount  
  
    -   Line Discount % \= Line Discount Amount \/ Line Value \* 100  
  
    -   Profit \= Line Amount - Line Cost  
  
 The steps are repeated for each contract line.  
  
## Example  
 The **Allow Unbalanced Amounts** check box is not selected in the service contract that contains three contract lines with such information.  
  
|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|15.00|17.00|3.00|0.51|25.00|1.49|  
|Item 2|20.00|23.00|None|0.00|55.10|3.00|  
|Item 3|24.00|27.00|3.00|0.81|112.70|2.19|  
  
 The **Annual Amount** field value is equal to the contents of the **Calcd. Annual Amount** field which is always set to the sum of the line amounts. In this case, it is equal to the following: 16.49 \+ 23.00 \+ 26.19 \= 65.68.  
  
 If you change the **Annual Amount** to 60, the profit percentage contributions for each contract line is calculated:  
  
-   Item 1 – 5 \/ \(5 \+ 5.1 \+12.7\) \= 0.2193 %  
  
-   Item 2 – 5.1 \/ \(5 \+ 5.1 \+ 12.7\) \= 0.2237  
  
-   Item 3 – 12.7 \/ \(5 \+ 5.1 \+ 12.7\) \= 0.557  
  
 The **Line Amount** field value is updated on each contract line using the following formula: Line Amount \= Line Amount \+ difference between the new and calculated annual amounts \* Percentage Contribution. After that, the **Line Discount Amount**, **Line Discount %**, and **Profit** field values are updated using the formulas described in the procedure above.  
  
 Finally, the contract lines will contain this data.  
  
|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|15.00|17.00|11.41|1.94|15.06|0.06|  
|Item 2|20.00|23.00|8.65|1.99|21.01|1.01|  
|Item 3|24.00|27.00|11.37|3.07|23.93|-0.07|  
  
## See Also  
 [How to: Automatically Distribute the Annual Amount Difference on Contracts](../how-to-automatically-distribute-the-annual-amount-difference-on-contracts.md)   
 [How to: Change the Annual Amount on Service Contracts or Contract Quotes](../how-to-change-the-annual-amount-on-service-contracts-or-contract-quotes.md)   
 [Distribution Based on Profit](../distribution-based-on-profit.md)   
 [Even Distribution](../even-distribution.md)   
 [How to: Manually Distribute the Annual Amount Difference on Contracts](../how-to-manually-distribute-the-annual-amount-difference-on-contracts.md)   
 Line Amount