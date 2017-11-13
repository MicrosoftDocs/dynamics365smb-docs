---
    title: How to Print the Outgoing Cash Order Report
    description: The **Cash Outgoing Order CO-2** report shows the outgoing cash order, which is a standard format required by Russian accounting legislation.

    documentationcenter: ''
    author: SorenGP

    ms.prod: "dynamics-nav-2017"
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Print the Outgoing Cash Order Report
The **Cash Outgoing Order CO-2** report shows the outgoing cash order, which is a standard format required by Russian accounting legislation.  

It shows the register of posted ingoing and outgoing cash orders during a specified reporting period.  

## To print the outgoing cash order report  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cash Outgoing Order**, and then choose the related link.  
2.  In the **Cash Outgoing Order** window, fill in the fields.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Test Print**|Select to print a draft of the report.<br /><br /> If this option is not selected and the value in the **Bank Payment Type** field in the **Outgoing Cash Order** window is **Computer Check**, then the following actions are performed:<br /><br /> -   If the **Check Printed** field is selected, a record is created in **Check Ledger Entries** with the value of **Entry Status** set to **Printed**.<br />-   If the **Document No.** field is blank, then it is filled with the next number from the No. Series for this cash account.<br />-   The status of the **Check Printed** is selected.|  

3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  

## See Also  
[Petty Cash Management](petty-cash-management.md)  
[Russia Local Functionality](russia-local-functionality.md)
