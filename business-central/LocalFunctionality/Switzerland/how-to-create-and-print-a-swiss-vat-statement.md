---
    title: How to Create and Print a Swiss VAT Statement
    description: Based on the information that you have specified on the VAT Posting Setup page, Business Central can automatically create a new VAT Statement Setup for realized VAT reporting. Before proceeding with the procedures in this topic, make sure that you have set up VAT posting setup with values specified for the sales and purchase cipher fields.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Create and Print a Swiss VAT Statement
Based on the information that you have specified on the **VAT Posting Setup** page, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] can automatically create a new VAT Statement Setup for realized VAT reporting. Before proceeding with the procedures in this topic, make sure that you have set up VAT posting setup with values specified for the sales and purchase cipher fields.  

## To set up a Swiss VAT statement template  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Update VAT Statement Template**, and then choose the related link.  
2.  Select a template in the **VAT Statement Template Name** field.
3.  Choose the **OK** button. Choose the **Yes** button to confirm that you want to create a new template.  
4.  Check the resulting VAT Statement and adjust as needed.  

     he VAT Statement page contains the **VAT Statement Cipher** field, which indicates in which cipher of the report the result will be printed. This field is automatically populated by the batch job based on the information on the **VAT Posting Setup** page. The field can be edited if needed.  

## To print the Swiss VAT statement  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Swiss VAT Statement**, and then choose the related link.  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Enter the date that you want the time interval for VAT statement lines that appear in the report to start.|  
    |**Ending Date**|Enter the date that you want the time interval for VAT statement lines that appear in the report to end.|  
    |**Closed with VAT Register No.**|Select the VAT Register that contains the posting source of the VAT adjusting entries. This option evaluates accounting periods that have already been settled. When you choose this option, you do not specify options in the following **Include VAT Entries** fields.|  
    |**Include VAT Entries**|Select one of the available options.|  
    |**Include VAT Entries**|Select one of the available options.|  
    |**Normal Rate %**|Enter the standard VAT rate that applies to the time period.|  
    |**Reduced Rate %**|Enter the reduced VAT tax for certain goods and services.|  
    |**Hotel Rate %**|Enter the VAT rate for accommodation that applies to the time period.|  
    |**Normal (Other Rate) %**|Enter an alternative VAT rate for standard transactions that applies to certain transactions during the time period.|  
    |**Reduced (Other Rate) %**|Enter an alternative VAT rate for other transactions that applies to certain transactions during the time period.|  
    |**Hotel (Other Rate) %**|Enter an alternative VAT rate for accommodation that applies to certain transactions during the time period.|  
    |**Show Amounts in Add. Reporting Currency**|Select to show amounts in an additional reporting currency.|  

## See Also  
 [Swiss Value Added Tax](swiss-value-added-tax.md)
