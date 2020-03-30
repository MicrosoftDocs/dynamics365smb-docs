---
    title: How to Create VAT Reports
    description: You can configure different types of VAT reports based on requirements. Then, when you have to submit a VAT report, you can create it on the VAT Report page and then export it in electronic format that conforms to the ELMA5 format requirements.
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
# Create VAT Reports
You can configure different types of VAT reports based on requirements. Then, when you have to submit a VAT report, you can create it on the **VAT Report** page and then export it in electronic format that conforms to the ELMA5 format requirements.  

## To create a VAT report  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Report**, and then choose the related link.  
2.  Fill in the fields in the **General** FastTab, including the fields that are described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specify the report number.<br /><br /> Depending on the type of report, and the configuration in your company, you can use the automatically generated number, select a different number series, or enter a different number manually.|  
    |**VAT Report Type**|Select the appropriate VAT Report type. The default setting is  **Standard**. If the report is an update to an existing report, choose **Corrective**.|  
    |**Trade Type**|Specify the type of trade that the report is to describe. The default is **Sales**. Other options are **Purchases** or **Both**.|  
    |**Start Date**|Specify the start date of the report period.|  
    |**End Date**|Specify the end date of the report period.|  
    |**EU Goods/Services**|Specify whether the report applies to **Goods**, **Services**, or both. The default is **Both**.|  
    |**Report Period Type**|Specify the time period that the report applies to:<br /><br /> -   Month<br />-   Quarter<br />-   Year<br />-   Bi-Monthly|  
    |**Report Period No.**|Specify the number of the VAT period.|  
    |**Report Year**|Specify the year that the VAT report covers.|  
    |**Processing Date**|Specify the date that the VAT report is created.|  

3.  Fill in the fields in the **Sign-off** FastTab, including the key fields that are described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sign-off Place**|Specify the location where the VAT report was signed off.|  
    |**Sign-off Date**|Specify the date that the VAT report has been signed off.|  
    |**Signed by Employee No.**|Specify the number of the employee who signed the VAT report from the lookup list.|  
    |**Created by Employee No.**|Specify the number of the employee who created the VAT report from the lookup list.|  

4.  Import the VAT ledger entries that must be included in the VAT report.  
5. Choose the **Suggest Lines** action.  

This adds VAT entries to the page. For each line, in the **Amount** field, you can drill down to see the VAT ledger entries that are the source of the line.  

After you create the VAT report, you have to submit it to the tax authorities.  

## To submit a VAT report  

1.  On the **VAT Report** page, choose the **Release** action.  
2.  Confirm that you want to release the report.  

    [!INCLUDE[d365fin](../../includes/d365fin_md.md)] validates that the VAT report is set up correctly. If the validation fails, the errors are shown on the **VAT Report Error Log** page so that you can make the appropriate changes. For example, an error displays if you try to release a standard VAT report but you have not yet added any lines to the report.  

    When you mark a VAT report as released, it becomes non-editable. If you must change the report after marking it as released, you must first reopen it.  

3.  Choose the **Export** action to create a VAT report of EU Sales List data in ELMA5 format. Save a copy of the report, which has the required name specified by ELMA5.  

    You can now submit the report to the tax authorities.  

4.  Choose the **Mark as Submitted** action.  

## See Also  
 [Correct VAT Reports](how-to-correct-vat-reports.md)   
 [Set Up VAT Reports](how-to-set-up-vat-reports.md)
