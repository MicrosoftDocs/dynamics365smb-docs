---
    title: How to Change the Annual Amount on Service Contracts or Contract Quotes | Microsoft Docs
    description: You can change the amount that will be invoiced annually on service contracts or service contract quotes.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Change the Annual Amount on Service Contracts or Contract Quotes
You can change the annual amount of the service contract or contract quote to correct the amount that will be invoiced annually.  

## To change the annual amount of the service contract or contract quote  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts** or **Service Contract Quotes**,and then choose the related link.  
2. Choose the contract or contract quote.  
3. Choose the **Open Contract** action to open the contract or contract quote for editing.  
4. Choose the **Allow Unbalanced Amounts** check box if you want to change the annual amount and distribute the annual amount difference manually on the contract lines. Otherwise, clear the check box to automatically distribute the annual amount difference on the contract lines after you change the annual amount.  
5. Change the contents of the **Annual Amount** field. You cannot sign, that is, convert into a service contract if you are working on a contract quote, or lock a service contract that has a negative annual amount. If you set the annual amount to zero, the contents of the **Invoice Period** field must be **None** when either signing or locking the service contract.  
6. Depending on whether the **Allow Unbalanced Amounts** check box is selected, run either the manual or automatic distribution of the annual amount difference. The contract lines will be updated so that the **Calcd. Annual Amount** field value is equal to the new annual amount.  

## Distributing Differences Between New and Calculated Annual Amounts
If you change the annual amount of a service contract or contract quote, you may want to distribute the difference between its new and calculated ammual amounts on the contract lines. There are three ways to distribute amounts:

* Even distribution  
* Distribution based on line amounts  
* Distribution based on Profit

### Even Distribution
If you change the annual amount of the service contract or contract quote, you may want to distribute the difference between its new and calculated annual amounts on the contract lines. Even distribution is one of the automatic distribution methods that can help you spread equally the new and calculated annual amounts difference between line amounts on the contract lines. The following list of distribution procedure steps describe the main idea of this method:  

1. The difference between the new **Annual Amount** and **Calcd. Annual Amount** field values is divided by the number of the contract lines in the service contract or contract quote.  
2. The **Line Amount** field value is updated by adding the result of the previous operation.  
3. The contents in the **Line Discount Amount**, **Line Discount %**, and **Profit** fields are updated with regard to the new value in the **Line Amount** field in the following way:   
    * Line Discount Amount = Line Value - Line Amount.  
    * Line Discount % = Line Discount Amount / Line Value * 100.  
    * Profit = Line Amount - Line Cost.  

 The steps are repeated for each contract line.  

#### Example  
The **Allow Unbalanced Amounts** check box is not selected in the service contract that contains three contract lines with such information.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|30.00|40.00|0.00|0.00|40.00|10.00|  
|Item 2|40.00|50.00|10.00|5.00|45.00|5.00|  
|Item 3|50.00|70.00|10.00|7.00|63.00|13.00|  

The **Annual Amount** field value is equal to the contents of the **Calcd. Annual Amount** field, which is always set to the sum of the line amounts. In this case, it is equal to the following:  40 + 45 + 63 = 148.  

If you change the **Annual Amount** to 139, the amount is calculated that should be added to each **Line Amount** field value. This amount is calculated by subtracting the **Calcd. Annual Amount** from the new **Annual Amount** field value and dividing the result by the number of the contract lines in the service contract. In this case, it will be equal to the following: (139 - 148) / 3 = -3. Then, the last calculated figure is added to each **Line Amount** field value and the **Line Discount %**, **Line Discount Amount**, and **Profit** field values are updated using the formulas in the procedure described above.  

Finally, the contract lines will contain this data.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|30.00|40.00|7.50|3.00|37.00|7.00|  
|Item 2|40.00|50.00|16.00|8.00|42.00|2.00|  
|Item 3|50.00|70.00|14.29|10.00|60.00|10.00|  

### Distribution Based on Line Amount
If you change the annual amount of the service contract or contract quote, you may want to distribute the difference between its new and calculated annual amounts on the contract lines. Distribution Based on Line Amount is an automatic method that can help you spread the new and calculated annual amounts difference between the line amounts on the contract lines. This distribution will be performed proportionally to their line amount shares in the calculated annual amount. The following list of distribution procedure steps for each contract line describe the main idea of this method:  

1. The line amount percentage contribution is calculated as follows: the contents of the **Line Amount** field is divided by the **Calcd. Annual Amount** field values on all contract lines.  
2. The **Line Amount** field value is updated by adding to it the difference between the new and calculated annual amounts, which is multiplied by the line amount percentage contribution.  
3. The contents in the **Line Discount Amount**, **Line Discount %**, and **Profit** fields are updated with regard to the new value in the **Line Discount Amount** field in the following way:  

    * Line Discount Amount = Line Value - Line Amount  
    * Line Discount % = Line Discount Amount / Line Value * 100  
    * Profit = Line Amount - Line Cost  

### Distribution Based on Line Amount
If you change the annual amount of the service contract or contract quote, you may want to distribute the difference between its new and calculated annual amounts on the contract lines. Distribution Based on Line Amount is an automatic method that can help you spread the new and calculated annual amounts difference between the line amounts on the contract lines. This distribution will be performed proportionally to their line amount shares in the calculated annual amount. The following list of distribution procedure steps for each contract line describe the main idea of this method:  

1. The line amount percentage contribution is calculated as follows: the contents of the **Line Amount** field is divided by the **Calcd. Annual Amount** field values on all contract lines.  
2. The **Line Amount** field value is updated by adding to it the difference between the new and calculated annual amounts, which is multiplied by the line amount percentage contribution.  
3. The contents in the **Line Discount Amount**, **Line Discount %**, and **Profit** fields are updated with regard to the new value in the **Line Discount Amount** field in the following way:  

    * Line Discount Amount = Line Value - Line Amount  
    * Line Discount % = Line Discount Amount / Line Value * 100  
    * Profit = Line Amount - Line Cost  

The steps are repeated for each contract line.  

#### Example  
The **Allow Unbalanced Amounts** check box is not selected in the service contract that contains three contract lines with such information.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|15.00|17.00|3.00|0.51|25.00|1.49|  
|Item 2|20.00|23.00|None|0.00|55.10|3.00|  
|Item 3|24.00|27.00|3.00|0.81|112.70|2.19|  

The **Annual Amount** field value is equal to the contents of the **Calcd. Annual Amount** field which is always set to the sum of the line amounts. In this case, it is equal to the following: 16.49 + 23.00 + 26.19 = 65.68.  

If you change the **Annual Amount** to 60, the profit percentage contributions for each contract line is calculated:  

* Item 1 – 5 / (5 + 5.1 +12.7) = 0.2193 %  
* Item 2 – 5.1 / (5 + 5.1 + 12.7) = 0.2237  
* Item 3 – 12.7 / (5 + 5.1 + 12.7) = 0.557  

The **Line Amount** field value is updated on each contract line using the following formula: Line Amount = Line Amount + difference between the new and calculated annual amounts * Percentage Contribution. After that, the **Line Discount Amount**, **Line Discount %**, and **Profit** field values are updated using the formulas described in the procedure above.  

Finally, the contract lines will contain this data.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|15.00|17.00|11.41|1.94|15.06|0.06|  
|Item 2|20.00|23.00|8.65|1.99|21.01|1.01|  
|Item 3|24.00|27.00|11.37|3.07|23.93|-0.07|  -   Line Discount % = Line Discount Amount / Line Value * 100  

#### Example  
The **Allow Unbalanced Amounts** check box is not selected in the service contract that contains three contract lines with such information.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|15.00|17.00|3.00|0.51|25.00|1.49|  
|Item 2|20.00|23.00|None|0.00|55.10|3.00|  
|Item 3|24.00|27.00|3.00|0.81|112.70|2.19|  

The **Annual Amount** field value is equal to the contents of the **Calcd. Annual Amount** field which is always set to the sum of the line amounts. In this case, it is equal to the following: 16.49 + 23.00 + 26.19 = 65.68.  

If you change the **Annual Amount** to 60, the profit percentage contributions for each contract line is calculated:  

* Item 1 – 5 / (5 + 5.1 +12.7) = 0.2193 %  
* Item 2 – 5.1 / (5 + 5.1 + 12.7) = 0.2237  
* Item 3 – 12.7 / (5 + 5.1 + 12.7) = 0.557  

The **Line Amount** field value is updated on each contract line using the following formula: Line Amount = Line Amount + difference between the new and calculated annual amounts * Percentage Contribution. After that, the **Line Discount Amount**, **Line Discount %**, and **Profit** field values are updated using the formulas described in the procedure above.  

Finally, the contract lines will contain this data.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|15.00|17.00|11.41|1.94|15.06|0.06|  
|Item 2|20.00|23.00|8.65|1.99|21.01|1.01|  
|Item 3|24.00|27.00|11.37|3.07|23.93|-0.07|  

### Distribution Based on Profit
If you change the annual amount of the service contract or contract quote, you may want to distribute the difference between its new and calculated annual amounts on the contract lines. Distribution Based on Profit is one of the automatic methods that can help you spread the new and calculated annual amounts difference between the line amounts on the contract lines. This distribution will be performed proportionally to their profit shares in the total contract or contract quote profit. The following list of distribution procedure steps for each contract line describe the main idea of this method:  

1. The profit percentage contribution is calculated as follows: the contents of the **Profit** field is divided by the sum of **Profit** field values on all contract lines.  
2. The **Line Amount** field value is updated by adding to it the difference between the new and calculated annual amounts, which is multiplied by the profit percentage contribution.  
3. The contents in the Line Discount Amount, Line Discount %, and Profit fields are updated with regard to the new value in the **Line Amount** field in the following way:  

    * Line Discount Amount = Line Value - Line Amount  
    * Line Discount % = Line Discount Amount / Line Value * 100  
    * Profit = Line Amount - Line Cost  

#### Example  
The **Allow Unbalanced Amounts** check box is not selected in the service contract that contains three contract lines with such information.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|20.00|25.00|0.00|0.00|25.00|5.00|  
|Item 2|50.00|58.00|5.00|2.90|55.10|5.10|  
|Item 3|100.00|115.00|2.00|2.30|112.70|12.70|  

The **Annual Amount** field value is equal to the contents of the **Calcd. Annual Amount** field, which is always set to the sum of the line amounts. In this case, it is equal to the following:  25.00 + 55.10 + 112.70 = 192.80.  

 If you change the **Annual Amount** to 180, the profit percentage contributions for each contract line are calculated:  

* Item 1 – 5 / (5 + 5.1 +1 2.7) = 0.2193 %  
* Item 2 – 5.1 / (5 + 5.1 + 12.7) = 0.2237  
* Item 3 – 12.7 / (5 + 5.1 + 12.7) = 0.557  

The **Line Amount** field value is updated on each contract line using the following formula: Line Amount = Line Amount + difference between the new and calculated annual amounts * Percentage Contribution. After that, the **Line Discount Amount**, **Line Discount %**, and **Profit** field values are updated using the formulas in the step 3 of the procedure described above.  

Finally, the contract lines will contain this data.  

|Item|Line Cost|Line Value|Line Discount %|Line Discount Amount|Line Amount|Profit|  
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
|Item 1|20.00|25.00|11.24|2.81|22.19|2.19|  
|Item 2|50.00|58.00|9.93|5.76|52.24|2.24|  
|Item 3|100.00|115.00|8.20|9.43|105.57|5.57|  

## See Also  
[Create Service Contracts and Service Contract Quotes](service-how-to-create-service-contracts-and-service-contract-quotes.md)  
[Setting Up Service Management](service-setup-service.md)  
