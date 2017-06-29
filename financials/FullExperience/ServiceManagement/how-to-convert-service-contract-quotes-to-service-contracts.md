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
# How to: Convert Service Contract Quotes to Service Contracts
When a customer has accepted a service contract quote, you convert it to a service contract. At the same time, you can create a service invoice for the starting period of the contract if the starting date of the contract is before the beginning of the next invoice period.  
  
 You must have created the service contract quote already.  
  
### To convert a service contract quote to service contract  
  
1.  In the **Search** box, enter **Service Contract Quotes**, and then choose the related link.  
  
2.  Open the relevant service contract quote you want to convert to a service contract.  
  
3.  On the **Home** tab, in the **Process** group, choose **Make Contract**.  
  
4.  If the starting date of the contract is before the beginning of the next invoice period, you are asked if you want to create an invoice for the starting period of the contract. Choose the **Yes** button to confirm.  
  
     A service contract is created with the status **Signed**. If a service invoice is created for the starting period of the contract, the invoiced amount is calculated in the following way, depending on whether the contract is detailed or not.  
  
    -   For detailed contracts, the invoiced amount is calculated as follows:  
  
        -   Invoiced amount \= sum of the invoiced amount for each contract line.  
  
        -   Invoiced amount for each contract line \= \(\(quote value ÷ 12\) × number of months in the starting period\) \+ \(\(quote value ÷ number of days in the year\) × number of days left in the starting period\).  
  
         If the contract line expires before the starting period ends, the expiration date becomes the ending date of the starting period for the line.  
  
    -   For contracts that are not detailed, the invoiced amount is calculated as follows:  
  
        -   Invoiced amount \= \(annual amount ÷ number of days in the year\) × number of days in the starting period.  
  
         If the contract expires before the starting period ends, the expiration date becomes the ending date of the starting period.  
  
 The service invoice is posted to the service account of the contract, even if the contract is prepaid.  
  
## See Also  
 [How to: Create Service Contracts and Service Contract Quotes](../how-to-create-service-contracts-and-service-contract-quotes.md)   
 [How to: Invoice Service Contracts](../how-to-invoice-service-contracts.md)   
 [How to: Add Contract Lines to Service Contracts or Service Contract Quotes](../how-to-add-contract-lines-to-service-contracts-or-service-contract-quotes.md)   
 [How to: Remove Contract Lines](../how-to-remove-contract-lines.md)   
 [How to: Update Service Contract Prices](../how-to-update-service-contract-prices.md)   
 [How to: Cancel Contracts](../how-to-cancel-contracts.md)