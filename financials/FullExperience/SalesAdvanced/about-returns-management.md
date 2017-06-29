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
# About Returns Management
Superior customer service is a key strategic objective of companies that strive for a high level of customer loyalty. For many wholesalers and distributors, sales returns are a standard element of their customer service policy, which directly influences the customer's perception of the service level. Timely crediting for returned items, repairing\/replacing a damaged item, and replacing a wrong item are among those aspects of handling returns that a customer associates with good service. The more seamless and efficient these return procedures appear to the customer, the more likely it is that the customer will rate the company's customer service highly.  
  
 From the company's perspective, the internal handling of return\-related processes can appear rather extensive. In most cases, companies need to adjust customer \(and vendor\) balances, account for additional costs, and update inventory quantities and values. Additionally, they may also need to inspect the returned items, send the returned items to the vendor for repair and so on. The scope of these processes will depend on a wide range of factors, such as the customer's request, reason for return, item type and value, cause of damage, and practices common in a specific line of business.  
  
 The handling of these processes involves different tasks that are performed by various groups of employees: sales people, warehouse personnel, bookkeepers, purchasers and inspectors. Although logically related, those different tasks are not necessarily operationally dependent. For example, the replacement for a damaged item can be shipped to a customer before the damaged item has been returned. Similarly, a customer can be credited for a returned item before the company has inspected and approved the return. In such a multi\-process environment, the challenge is to ensure that all return\-associated processes are completed in a timely manner and possible errors can be easily recovered.  
  
## Managing Returns from Customers  
 Compensating a customer who is dissatisfied with an item that a company has sold them is a necessary and important transaction between a company and its customer. The faster and more accurately a company carries out the activities involved in a return process, the more likely the company is to foster the customer's perception of good customer service.  
  
 Typically, the salesperson responsible for the interface with certain customers would also be the contact person to receive complaints from those customers about the items sold. In other cases, a company may have a dedicated person\(s\) specifically dealing with returns; for example, employees in the customer service department.  
  
 Irrespective of the industry in which that company operates, the typical customer\-oriented return handling process includes the following tasks:  
  
-   Determine a compensation agreement with the customer.  
  
-   Shipping a replacement item\(s\) to the customer \(if replacement is part of the compensation agreement\).  
  
-   Crediting the customer \(either by means of a credit for physically returned items or a sales allowance where the customer is not required to physically return the items\).  
  
-   Shipping a repaired item\(s\) to the customer \(if repair is a part of a compensation agreement\).  
  
-   Follow\-up on the return status \(in case of customer inquiries\).  
  
 Related to the customer\-facing process, there are a number of internal handling tasks:  
  
-   Receiving returned items and inspecting them \(if relevant\).  
  
-   Applying restock charges.  
  
-   Shipping returned items to the vendor for repair.  
  
-   Ensuring the accurate inventory value of the returned items.  
  
 The Sales Return Order Management functionality allows companies to manage all these tasks in an efficient and accurate manner.  
  
## Managing Returns from Vendors  
 Receiving compensation from your vendor for a purchased item that you are dissatisfied with is important for reasons of recovering costs and maintaining satisfactory vendor relationships. Streamlining the return\-to\-vendor process by carrying out the activities involved in the return process faster and more accurately can help companies substantially reduce the costs usually associated with returns.  
  
 Typically, a purchaser responsible for the interface with certain vendors would also be the one to make contact with those vendors in case of dissatisfaction with the purchased items.  
  
 Managing returns to vendors includes carrying out a series of tasks. The number and scope of those tasks generally depend on who initiates the return: the company itself \(when, for example, dissatisfied with the quality of purchased items or in case of wrong delivery\) or a company's own customer. Irrespective of that, a typical vendor\-oriented return process may include the following tasks:  
  
-   Determine the compensation agreement with the vendor.  
  
-   Debiting the vendor, either by means of receiving a credit for physically returned items, or of a purchase allowance \(in a case where the company is not required to physically return the items\).  
  
-   Creating a replacement purchase order\(s\) \(if replacement is part of a compensation agreement\).  
  
 Related to the vendor\-oriented process, there are a number of internal handling tasks:  
  
-   Shipping items to the vendor \(if purchase return, including repair, is part of a compensation agreement\).  
  
-   Receiving replaced\/repaired items.  
  
-   Ensuring the accurate inventory value of the items to be returned to the vendor.  
  
-   Combining several return shipments to the same vendor into one credit memo document.  
  
 The Purchase Return Order Management functionality allows companies to manage all these tasks in an efficient and accurate manner.  
  
## Registering Compensation  
 The return order is the central document that allows the user to register a compensation agreement settled with a customer or vendor. From here, the user can access other sales or purchase related documents, and enter and maintain the return\-related information concerning the customer or vendor, the method of compensation, and the items in question.  
  
 To register different aspects of a compensation agreement in the same return order, the user can create return lines of different types. Principally, in return situations:  
  
-   An Item type line represents a transaction where the item is to be physically returned before a credit can be given.  
  
-   Charge \(Item\) and Account \(G\/L\) type lines represent a financial transaction where a credit is granted \(in the form of a sales\/purchase allowance\) for the unsatisfactory item\(s\), without physically returning the items. The same type lines can be used for registering any charges and fees that may be associated with a specific return.  
  
 Apart from the return order, to register details about a compensation agreement, the user can use other standard documents , \(sales credit memos, sales orders, and sales invoices; purchase credit memos, purchase orders, and purchase invoices\) or combinations of them.  
  
 In the return order\/credit memo, a return transaction is expressed as a line with a positive quantity, while in the sales or purchase order\/invoice, a return is represented by a line with negative quantity.  
  
 When deciding on which document to use as a preferred entry point for a compensation agreement, the user must be aware that, in contrast to a credit memo\/invoice \(where posting updates both quantity and value at the same time\), the return order offers the possibility of separating the quantity and value parts of the transaction. Therefore, companies where this flexibility is essential may prefer using a return order rather than a credit memo.  
  
## See Also  
 [How to: Process Purchase Returns](../Purchasing/how-to-process-purchase-returns.md)   
 [How to: Process Sales Returns](../Sales/how-to-process-sales-returns.md)