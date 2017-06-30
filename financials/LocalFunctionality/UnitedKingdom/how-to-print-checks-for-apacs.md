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
# How to: Print Checks for APACS
The Association for Payment Clearing Services \(APACS\) specification defines a standard layout for fields on checks. The **Check** report uses this specification.  
  
### To print checks for APACS  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  To preview the check, on the **Navigate** tab, in the **Payments** group, choose **Preview Check**.  
  
3.  To print the check, on the **Navigate** tab, in the **Payments** group, choose **Print Check**.  
  
4.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_1401\_N\_2\_1 Bank Account $\)**|Specifies bank account code.|  
    |**\($ R\_1401\_N\_2\_3 Last Check No. $\)**|Specifies the last check number that was specified in the **Bank Account Card** window.|  
    |**\($ R\_1401\_N\_2\_11 One Check per Vendor per Document No. $\)**|Select to print only one check per vendor for each document number.|  
    |**\($ R\_1401\_N\_2\_5 Reprint Checks $\)**|Select to reprint canceled checks.|  
    |**\($ R\_1401\_N\_2\_9 Test Print $\)**|Select to print checks on blank paper before printing them on check forms.|  
    |**\($ R\_1401\_N\_2\_13 Preprinted Stub $\)**|Select to use check forms with preprinted stubs.|  
  
5.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Check](../\($%20R_1401%20Check%20$\).md)   
 Payment Journal   
 [United Kingdom Local Functionality](../united-kingdom-local-functionality.md)