---
    title: How to Create Service Contracts and Service Contract Quotes | Microsoft Docs
    description: You can create a service contract either manually or from a service contract quote. You can create a contract based on a service contract quote. 
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
# How to: Create Service Contracts and Service Contract Quotes
You can create a service contract either manually or from a service contract quote. You can use a service contract quote as a forerunner of a service contract, in which your company makes an offer to the customer and obtains customer approval before you can convert it to a service contract. The procedures for creating either a service contract or service contract quote are similar.  
  
### To create a service contract or service contract quote  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contracts** or **Service Contract Quotes**,and then choose the related link.  
2. Create a new service contract or service contract quote.  
3. Fill in the **No.** field. A dialog box opens, asking whether you want to fill it with the common data from a contract template. If you want to create such a service contract or service contract quote, choose the **Yes** button. The **Service Contract Template List** window opens.  
4. Select the appropriate template, and then choose **OK** to use it to create the service contract or service contract quote.  
5. In the **Customer No.** field, choose the customer.  
6. If you do not want an annual amount difference to be distributed automatically, choose the **Allow Unbalanced Amounts** check box. The values in the **Annual Amount** and **Calcd. Annual Amount** fields are not automatically equalized. If you want the program to do automatically distribute any annual amount difference that might occur from a change in the service contract, leave the **Allow Unbalanced Amounts** check box clear.  
7. Add contract lines to the service contract or service contract quote.  
8. Fill in the rest of the fields in the **Service Contract Quote** window as needed.  

### To convert a service contract quote to service contract  
When a customer has accepted a service contract quote, you convert it to a service contract. At the same time, you can create a service invoice for the starting period of the contract if the starting date of the contract is before the beginning of the next invoice period.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contract Quotes**, and then choose the related link.  
2. Open the service contract quote you want to convert to a service contract.  
3. Choose the **Make Contract** action.  
4. If the starting date of the contract is before the beginning of the next invoice period, you are asked if you want to create an invoice for the starting period of the contract. Choose **Yes**.  
  
     A service contract is created with the status **Signed**. If a service invoice is created for the starting period of the contract, the invoiced amount is calculated in the following way, depending on whether the contract is detailed or not.  
  
    -   For detailed contracts, the invoiced amount is calculated as follows:  
  
        -   Invoiced amount = sum of the invoiced amount for each contract line.  
  
        -   Invoiced amount for each contract line = ((quote value ÷ 12) × number of months in the starting period) + ((quote value ÷ number of days in the year) × number of days left in the starting period).  
  
         If the contract line expires before the starting period ends, the expiration date becomes the ending date of the starting period for the line.  
  
    -   For contracts that are not detailed, the invoiced amount is calculated as follows:  
  
        -   Invoiced amount = (annual amount ÷ number of days in the year) × number of days in the starting period.  
  
         If the contract expires before the starting period ends, the expiration date becomes the ending date of the starting period.  
  
 The service invoice is posted to the service account of the contract, even if the contract is prepaid. 

## Update and Evaluate Contracts
Sometimes you have to change the terms of a contract after it has been created. In most cases, you open the relevant contract in the **Service Contract** window, and change it as necessary.  
  
You can change the status of the contract, initially set to **Locked**, add and remove contract lines, and cancel a contract. If you want to see how your business is doing as measured by gain and loss, you can do quick business analysis using the contract trendscape feature.

### To add a contract line to a service contract or contract quote  
When a customer purchases a new item and wants to include it in the existing service contract or contract quote, you can register the item as a service item and then add it as a new contract line to the contract or contract quote.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contracts**, and then choose the related link.  
2. Open the relevant service contract or service contract quote that you want to add a new contract line for.  
3. Choose the **Open Contract** action to open the service contract or service contract quote for editing.  
4. On the **Invoice Details** FastTab, select the **Allow Unbalanced Amounts** field if you want to change the annual amount and distribute the annual amount difference manually on the contract lines. Otherwise, clear the check box in the **Allow Unbalanced Amounts** field. This will distribute the annual amount difference automatically on the contract lines after you change the annual amount.  
5. On the **Lines** FastTab, add a service item or item, or text description, on each contract line. Alternatively, you can add contract quote lines. Note that you can create multiple contracts per service item to have it included in different service contracts or contract quotes at the same time.  
6. Verify and correct the numbers in the **Line Discount %**, **Line Discount Amount**, **Response Time**, **Service Period**, and other fields as needed. 

## About Service Line Cost and Value
On a service contract lines, the amounts in the **Line Cost** and **Line Value** are calculated as described in the following tables.

| Line Cost Options | Description|
|----------------------------------|---------------------------------------|  
|**Service item** | The cost is automatically retrieved from the **Default Contract Cost** field in the **Service Item** table and copied into the **Line Cost** field. The following formula is used to calculate the line cost:<br /><br /> Sales Unit Cost × Contract Value % ÷ 100|  
|**Item** | The cost is automatically retrieved from the **Unit Cost** field in the **Item** table and the **Contract Value %** field value in the **Service Mgt. Setup** table. The following formula is used to calculate the line cost:<br /><br /> Unit Cost × Contract Value % ÷ 100|  
|**Text description** | The value in the **Line Cost** field is set to zero.|  

| Line Value Options | Description|
|----------------------------------|---------------------------------------|  
|**Service item** | The price is automatically retrieved from the **Default Contract Value** field in the **Service Item** table and copied into the **Line Value** field.|  
|**Item** | Depending on the value in the **Contract Value Calc. Method** field in the **Service Mgt. Setup** table, the amount is retrieved from either the **Unit Price** or the **Unit Cost** field in the **Item** table. After that, this value is multiplied by the contents of the **Contract Value %** field in the **Service Mgt. Setup** table and divided by 100. This amount is copied into the **Line Value** field.<br /><br /> **NOTE:** If the **Contract Value Calc. Method** field is set to **None**, the contents of the **Line Value** field are not calculated.|  
|**Text description** | The contents of the **Line Value** field are set to zero.|  

## See Also  
[How to: Set Up Service Contracts](service-how-setup-service-contracts.md)  
[Service Management](service-service.md)  
[How to: Convert Service Contracts that Include VAT Amounts](service-how-to-convert-service-contracts.md)  
