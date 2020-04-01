---
    title: Set Up Service Contracts | Microsoft Docs
    description: Learn how to set up service contracts.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: service, cost, service order
    ms.date: 04/01/2020
    ms.author: sgroespe

---

# Set Up Service Contracts
Before you can work with contracts, you must set up the following: 

* **Service contract groups**, which gather service contracts that are related in some way.
* **Service contract account groups**, which are used to group the service contract accounts together for service invoices created for service contracts. You assign these groups to service contracts.  
* **Contract templates** that define contract layouts of contracts that include the most commonly used service contract details. When you create service contract quotes, you can create them by using templates. When you create a contract quote, the fields automatically contain the contents of the template fields.
* **Customer templates** that let you create quotes for contacts or potential customers who are not registered as customers in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## To set up a service contract group  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contract Groups**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Choose the **Disc. on Contr. Orders Only** check box if you want contract or service discounts to be valid only for contract service orders, such as maintenance.  

## To set up a service contract account group  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Serv. Contract Account Groups**, and then choose the related link.  
2. Create a new service contract account group.   
3. Fill in the **Code** and **Description** fields. These fields describe the service account group.  
4. Fill in the **Non-Prepaid Contract Acc.** field, choose general ledger account number for the non-prepaid account.  
5. In the **Prepaid Contract Acc.** field, choose the general ledger account number for the prepaid account.  

## To set up a contract template  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contract Templates**, and then choose the related link.  
2. Create a new service contract template.  
3. In the **No.** field, enter a number for the contract template.  
  
     Alternatively, if you have set up number series for contract templates on the **Service Mgt. Setup** page, you can press the Enter key to enter the next available contract template number. Fill in the other fields if appropriate.  
  
4. On the **Invoice** FastTab, fill in the **Serv. Contract Acc. Group Code** field, the **Invoice Period**, and so on. Fill in the other fields if appropriate.  
5. Choose the **Service Discounts** action to add contract discounts.  

## To set up a customer template  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Templates**, and then choose the related link.  
2. Create a new customer template card.  
3. On the **General** FastTab, enter a code and a description for the customer template in the **Code** and **Description** fields respectively. 
4. To define search criteria, fill in the other fields, such as **Country/Region Code**, **Territory Code**, and **Language Code**.  
5. Fill in the **Gen. Bus. Posting Group** and **Customer Posting Group** fields.  

## See Also
[Setting Up Service Management](service-setup-service.md)