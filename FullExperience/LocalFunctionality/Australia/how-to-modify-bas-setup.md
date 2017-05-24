---
title: "How to: Modify BAS Setup"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 47132461-712b-4154-b644-5ec0de5898a8
caps.latest.revision: 7
ms.author: "edupont"
manager: "tsiggaar"
translation.priority.ht: 
  - "en-au"
---
# How to: Modify BAS Setup
To complete the Business Activity Statement \(BAS\) setup, you must map fuel tax credits to general ledger accounts. Do not map an account for field 7C if you only have a fuel tax credit that the ATO owes you and you do not owe anything to ATO. In this case, you can consider mapping only field 7D.  
  
### To modify and map BAS Setup for the fuel tax credit fields  
  
1.  In the **Search** box, enter **BAS Setup Names**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **BAS Setup**.  
  
3.  In the **BAS Setup**  window, on a new line 16000, in the **\($ T\_11600\_1 Field No. $\)** field, enter 72.  
  
4.  In the **\($ T\_11600\_7 Account Totaling $\)** field, select the appropriate general ledger account. The account should have a credit balance.  
  
5.  In the **BAS Setup**  window, on a new line 17000, in the **\($ T\_11600\_1 Field No. $\)** field, enter 73.  
  
6.  In the **\($ T\_11600\_7 Account Totaling $\)** field, select the appropriate general ledger account. The account should have a debit balance.  
  
7.  Choose the **OK** button.  
  
## See Also  
 [BAS Fuel Tax Credits](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/bas-fuel-tax-credits.md)   
 [How to: Set Up BAS XML Fields](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/how-to-set-up-bas-xml-fields.md)   
 [Business Activity Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/business-activity-statements.md)