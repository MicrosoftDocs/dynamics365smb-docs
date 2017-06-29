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
# How to: Print the Ingoing Cash Order Report
The **Cash Ingoing Order CO\-1** report prints the Ingoing Cash Order form, which is a standard format required by Russian accounting legislation.  
  
### To print the ingoing cash order report  
  
1.  In the **Search** box, enter **Cash Ingoing Order**, and then choose the related link.  
  
2.  In the **\($ R\_12403 Cash Ingoing Order CO\-1 $\)** window, fill in the fields.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_12403\_N\_2\_1 Test Print $\)**|Select to print a draft of the report.<br /><br /> If this option is cleared and the value of **Bank Payment Type** on the **Ingoing Cash Order** window is set to **Computer Check**, then the following actions are performed:<br /><br /> -   If **Check Printed** is set to **No**, a record is created in **Check Ledger Entries** with the value of **Entry Status** set to **Printed**.<br />-   If **Document No.** is blank, then it is filled with the next number from the No. Series for this cash account.<br />-   The status of **Check Printed** is set to **Yes**.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  
  
## See Also  
 Cash Report CO\-4   
 Cash Order Journal CO\-3