---
    title: How to Manage Customer Credit Information | Microsoft Docs
    description: In Business Central, you can add comments to customer credit information. You can also hold and block customers with bad credit before shipping or invoicing occurs.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/11/2017
    ms.author: sgroespe

---
# Manage Customer Credit Information
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can add comments to customer credit information. You can also hold and block customers with bad credit before shipping or invoicing occurs.  

## To add comments to customer credit information  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Credit Management**, and then choose the related link.  
2.  In the **Customer List - Credit Mgmt.** window, select a customer, and then choose the **Comments** action.  
3.  In the **Comment Sheet** window, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Date**|The date of the comment.|  
    |**Comment**|The comment about the customer. You can enter a maximum of 80 alphanumeric characters.|  

4.  Choose the **OK** button.  

## To prevent an order from shipping or invoicing  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
2.  Select the customer, and the choose the **Ledger Entries** action.  
3.  In the **On Hold** field, enter the initials of the customer.  
4.  Choose the **OK** button.  

    > [!NOTE]  
    >  You must have the proper security clearance to add or remove holds on individual sales orders using the **On Hold** field.  

## To block a sales order for a customer  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
2.  Select a customer, and then choose the **Edit** action.  
3.  On the **General** FastTab, in the **Blocked** field, select one of the following options:  

    -   **<Blank>** – Transaction is allowed for this customer.  
    -   **Ship** – New orders and new shipments cannot be created for this customer. Existing shipments not yet invoiced can be invoiced.  
    -   **Invoice** – New orders, new shipments, and new invoices cannot be created for this customer. Existing shipments not yet invoiced cannot be invoiced.  
    -   **All** – No transaction is allowed for this customer, including payments.  
4.  Choose the **OK** button.  

## See Also  
[United States Local Functionality](united-states-local-functionality.md)  
[Finance](../../finance.md)  
[Setting Up Finance](../../finance.md)
