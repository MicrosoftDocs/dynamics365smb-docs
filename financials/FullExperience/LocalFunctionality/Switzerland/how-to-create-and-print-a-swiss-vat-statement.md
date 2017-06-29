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
# How to: Create and Print a Swiss VAT Statement
Based on the information that you have specified in the **VAT Posting Setup** window, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> can automatically create a new VAT Statement Setup for realized VAT reporting. Before proceeding with the procedures in this topic, make sure that you have set up VAT posting setup with values specified for the sales and purchase cipher fields.  
  
### To set up a Swiss VAT statement template  
  
1.  In the **Search** box, enter **Update VAT Statement Template**, and then choose the related link.  
  
2.  Select a template in the **VAT Statement Template Name** field. For more information about how to creat a new template, see VAT Statement Template.  
  
3.  Choose the **OK** button. Choose the **Yes** button to confirm that you want to create a new template.  
  
4.  Check the resulting VAT Statement and adjust as needed.  
  
     The VAT Statement page contains the **VAT Statement Cipher** field, which indicates in which cipher of the report the result will be printed. This field is automatically populated by the batch job based on the information in the **VAT Posting Setup** window. The field can be edited if needed.  
  
### To print the Swiss VAT statement  
  
1.  In the **Search** box, enter **Swiss VAT Statement**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_26100\_F\_1\_1150062 Starting Date $\)**|Enter the date that you want the time interval for VAT statement lines that appear in the report to start.|  
    |**\($ R\_26100\_F\_1\_1150080 Ending Date $\)**|Enter the date that you want the time interval for VAT statement lines that appear in the report to end.|  
    |**\($ R\_26100\_F\_1\_1150001 Closed with VAT Register No. $\)**|Select the VAT Register that contains the posting source of the VAT adjusting entries. This option evaluates accounting periods that have already been settled. When you choose this option, you do not specify options in the following **Include VAT Entries** fields.|  
    |**\($ R\_26100\_F\_1\_1150072 Include VAT Entries $\)**|Select one of the available options.|  
    |**\($ R\_26100\_F\_1\_1150056 Include VAT Entries $\)**|Select one of the available options.|  
    |**\($ R\_26100\_F\_1\_1150002 Normal Rate % $\)**|Enter the standard VAT rate that applies to the time period.|  
    |**\($ R\_26100\_F\_1\_1150004 Reduced Rate % $\)**|Enter the reduced VAT tax for certain goods and services.|  
    |**\($ R\_26100\_F\_1\_1150006 Hotel Rate % $\)**|Enter the VAT rate for accommodation that applies to the time period.|  
    |**\($ R\_26100\_F\_1\_1150013 Normal \(Other Rate\) % $\)**|Enter an alternative VAT rate for standard transactions that applies to certain transactions during the time period.|  
    |**\($ R\_26100\_F\_1\_1150010 Reduced \(Other Rate\) % $\)**|Enter an alternative VAT rate for other transactions that applies to certain transactions during the time period.|  
    |**\($ R\_26100\_F\_1\_1150045 Hotel \(Other Rate\) % $\)**|Enter an alternative VAT rate for accommodation that applies to certain transactions during the time period.|  
    |**\($ R\_26100\_F\_1\_1150060 Show Amounts in Add. Reporting Currency $\)**|Select to show amounts in an additional reporting currency. For more information, see [About Using Additional Reporting Currencies](../about-using-additional-reporting-currencies.md).|  
  
## See Also  
 [Swiss Value Added Tax](../swiss-value-added-tax.md)   
 Swiss VAT Statement