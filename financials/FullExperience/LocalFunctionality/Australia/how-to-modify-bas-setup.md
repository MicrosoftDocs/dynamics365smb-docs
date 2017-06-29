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
# How to: Modify BAS Setup
To complete the Business Activity Statement \(BAS\) setup, you must map fuel tax credits to general ledger accounts. Do not map an account for field 7C if you only have a fuel tax credit that the ATO owes you and you do not owe anything to ATO. In this case, you can consider mapping only field 7D.  
  
### To modify and map BAS Setup for the fuel tax credit fields  
  
1.  In the **Search** box, enter **BAS Setup Names**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **BAS Setup**.  
  
3.  In the **BAS Setup**  window, on a new line 16000, in the **Field No.** field, enter 72.  
  
4.  In the **Account Totaling** field, select the appropriate general ledger account. The account should have a credit balance.  
  
5.  In the **BAS Setup**  window, on a new line 17000, in the **Field No.** field, enter 73.  
  
6.  In the **Account Totaling** field, select the appropriate general ledger account. The account should have a debit balance.  
  
7.  Choose the **OK** button.  
  
## See Also  
 [BAS Fuel Tax Credits](../FullExperience/bas-fuel-tax-credits.md)   
 [How to: Set Up BAS XML Fields](../FullExperience/how-to-set-up-bas-xml-fields.md)   
 [Business Activity Statements](../FullExperience/business-activity-statements.md)