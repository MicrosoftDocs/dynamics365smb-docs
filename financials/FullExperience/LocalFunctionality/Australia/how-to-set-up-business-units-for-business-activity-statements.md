---
title: "How to: Set Up Business Units for Business Activity Statements"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "BAS, setting up business units"
  - "business units, setting up"
  - "Business Activity Statement (BAS), setting up business units"
  - "business units, business activity statements"
ms.assetid: 0fa00c39-cfb1-4ace-a29f-2c0dd362abe0
caps.latest.revision: 24
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-au"
---
# How to: Set Up Business Units for Business Activity Statements
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can consolidate the financial statements of various companies into one financial statement.  
  
 You must set up a consolidation company to perform the consolidation. In this company, the total amounts for all accounts in the group, from both the parent company and subsidiaries are added together. You must also indicate the general ledger accounts in the consolidated company to which the total should be transferred.  
  
 You can use the **BAS Business Units** window to set up the following:  
  
-   Parent company  
  
-   Subsidiaries  
  
-   Affiliates  
  
 You must set up information in the **General Ledger Setup** window before you can set up business units.  
  
### To set up general ledger for a business activity statement  
  
1.  In the **Seach** box, enter **General Ledger Setup**, and then choose the appropriate link.  
  
2.  Fill in the required fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**BAS to be Lodged as a Group**|Select if you are logging a business activity statement for a group of companies.|  
    |**BAS Group Company**|Select if this company is the main company in the group of companies for which you are lodging a group business activity statement.|  
  
3.  Choose the **OK** button.  
  
### To set a business unit for a business activity statement  
  
1.  In the **Seach** box, enter **BAS Business Units**, and then choose the appropriate link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Company Name**|Specify the name of the company which will be added to the group company's business activity statement.|  
    |**Document No.**|Specify the BAS document number that has to be consolidated. This field is associated with the **BAS Version** field.|  
    |**BAS Version**|Specify the BAS version number in which the transaction was included. This field is associated with the **Document No.** field.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 General Ledger Setup   
 [Business Activity Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/business-activity-statements.md)   
 [How to: Set Up Business Activity Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/how-to-set-up-business-activity-statements.md)