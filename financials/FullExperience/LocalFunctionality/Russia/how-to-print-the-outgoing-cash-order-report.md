---
title: "How to: Print the Outgoing Cash Order Report"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cash order reports, printing"
ms.assetid: f3a8baca-9031-48a6-b499-2a49a8492bfc
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Print the Outgoing Cash Order Report
The **Cash Outgoing Order CO\-2** report shows the outgoing cash order, which is a standard format required by Russian accounting legislation.  
  
 It shows the register of posted ingoing and outgoing cash orders during a specified reporting period.  
  
### To print the outgoing cash order report  
  
1.  In the **Search** box, enter **Cash Outgoing Order**, and then choose the related link.  
  
2.  In the **Cash Outgoing Order** window, fill in the fields.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_12402\_N\_2\_2 Test Print $\)**|Select to print a draft of the report.<br /><br /> If this option is not selected and the value in the **Bank Payment Type** field in the **Outgoing Cash Order** window is **Computer Check**, then the following actions are performed:<br /><br /> -   If the **Check Printed** field is selected, a record is created in **Check Ledger Entries** with the value of **Entry Status** set to **Printed**.<br />-   If the **Document No.** field is blank, then it is filled with the next number from the No. Series for this cash account.<br />-   The status of the **Check Printed** is selected.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  
  
## See Also  
 Cash Report CO\-4   
 Cash Order Journal CO\-3   
 [Petty Cash Management](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/petty-cash-management.md)