---
title: "How to: Create and Print a Swiss VAT Statement"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, setting up reporting"
  - "VAT, printing statements"
ms.assetid: b80c8ec0-7339-4cb1-a136-ad934f68ba71
caps.latest.revision: 4
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Create and Print a Swiss VAT Statement
Based on the information that you have specified in the **VAT Posting Setup** window, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] can automatically create a new VAT Statement Setup for realized VAT reporting. Before proceeding with the procedures in this topic, make sure that you have set up VAT posting setup with values specified for the sales and purchase cipher fields.  
  
### To set up a Swiss VAT statement template  
  
1.  In the **Search** box, enter **Update VAT Statement Template**, and then choose the related link.  
  
2.  Select a template in the **VAT Statement Template Name** field. For more information about how to creat a new template, see [VAT Statement Template](assetId:///678abbca-1d38-4cd2-a08c-0c1c69d6be6c).  
  
3.  Choose the **OK** button. Choose the **Yes** button to confirm that you want to create a new template.  
  
4.  Check the resulting VAT Statement and adjust as needed.  
  
     The VAT Statement page contains the **VAT Statement Cipher** field, which indicates in which cipher of the report the result will be printed. This field is automatically populated by the batch job based on the information in the **VAT Posting Setup** window. The field can be edited if needed.  
  
### To print the Swiss VAT statement  
  
1.  In the **Search** box, enter **Swiss VAT Statement**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Enter the date that you want the time interval for VAT statement lines that appear in the report to start.|  
    |**Ending Date**|Enter the date that you want the time interval for VAT statement lines that appear in the report to end.|  
    |**Closed with VAT Register No.**|Select the VAT Register that contains the posting source of the VAT adjusting entries. This option evaluates accounting periods that have already been settled. When you choose this option, you do not specify options in the following **Include VAT Entries** fields.|  
    |**Include VAT Entries**|Select one of the available options.|  
    |**Include VAT Entries**|Select one of the available options.|  
    |**Normal Rate %**|Enter the standard VAT rate that applies to the time period.|  
    |**Reduced Rate %**|Enter the reduced VAT tax for certain goods and services.|  
    |**Hotel Rate %**|Enter the VAT rate for accommodation that applies to the time period.|  
    |**Normal \(Other Rate\) %**|Enter an alternative VAT rate for standard transactions that applies to certain transactions during the time period.|  
    |**Reduced \(Other Rate\) %**|Enter an alternative VAT rate for other transactions that applies to certain transactions during the time period.|  
    |**Hotel \(Other Rate\) %**|Enter an alternative VAT rate for accommodation that applies to certain transactions during the time period.|  
    |**Show Amounts in Add. Reporting Currency**|Select to show amounts in an additional reporting currency. For more information, see [About Using Additional Reporting Currencies](../../Finance/about-using-additional-reporting-currencies.md).|  
  
## See Also  
 [Swiss Value Added Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-value-added-tax.md)   
 [Swiss VAT Statement](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-r_26100-swiss-vat-statement-$-.md)