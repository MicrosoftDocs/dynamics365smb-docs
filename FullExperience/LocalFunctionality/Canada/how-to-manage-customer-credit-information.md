---
title: "How to: Manage Customer Credit Information"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "credit management"
  - "customer credit information"
  - "CMR notes, customer credit management"
ms.assetid: 9434d98d-5e31-4fa3-a446-d550d3dec603
caps.latest.revision: 32
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-ca"
  - "es-mx"
  - "fr-ca"
---
# How to: Manage Customer Credit Information
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can add comments to customer credit information. You can also hold and block customers with bad credit before shipping or invoicing occurs.  
  
### To add comments to customer credit information  
  
1.  In the **Search** box, enter **Credit Management**, and then choose the related link.  
  
2.  In the **Customer List \- Credit Mgmt.** window, select a customer. On the **Navigate** tab, in the **Customer** group, choose **Comments**.  
  
3.  In the **Comment Sheet** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Date**|The date of the comment.|  
    |**Comment**|The comment about the customer. You can enter a maximum of 80 alphanumeric characters.|  
  
4.  Choose the **OK** button.  
  
### To prevent an order from shipping or invoicing  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link in **Receivables**.  
  
2.  Select the customer. On the **Navigate** tab, in the **History** group, choose **Ledger Entries**.  
  
3.  In the **On Hold** field, enter the initials of the customer.  
  
4.  Choose the **OK** button.  
  
    > [!NOTE]  
    >  You must have the proper security clearance to add or remove holds on individual sales orders using the **On Hold** field.  
  
### To block a sales order for a customer  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link in **Receivables**.  
  
2.  Select a customer. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **General** FastTab, in the **Blocked** field, select one of the following options:  
  
    -   **\<Blank\>** – Transaction is allowed for this customer.  
  
    -   **Ship** – New orders and new shipments cannot be created for this customer. Existing shipments not yet invoiced can be invoiced.  
  
    -   **Invoice** – New orders, new shipments, and new invoices cannot be created for this customer. Existing shipments not yet invoiced cannot be invoiced.  
  
    -   **All** – No transaction is allowed for this customer, including payments.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Customer \- Order Summary](../Topic/\($%20R_107%20Customer%20-%20Order%20Summary%20$\).md)   
 [United States Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedStates/united-states-local-functionality.md)   
 [Canada Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/canada-local-functionality.md)   
 [Mexico Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/mexico-local-functionality.md)