---
    title: How to Set Up VAT Reports
    description: Information from various invoice types is used to feed data into the EU Sales List report. To file a VAT report under the ELMA5 system from Business Central, you need to set up report parameters.

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
# Set Up VAT Reports
Information from various invoice types is used to feed data into the EU Sales List report. To file a VAT report under the ELMA5 system from [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you need to set up report parameters.  

## To set up a VAT report  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Report Setup**, and then choose the related link.  
2.  On the **General** FastTab, select the **Modify Submitted Reports** check box to let users modify VAT reports that have been submitted to the tax authorities.  

    If the field is left blank, users must create a corrective VAT report instead.  

3.  Select the **Export Cancellation Lines** check box if you want to include information about cancellation lines when you export data for the VAT report of EU sales. For more information, see [Correct VAT Reports](how-to-correct-vat-reports.md).  
4.  On the **Numbering** FastTab, specify the number series that will be used for standard VAT reports. This will be the default numbering series that is used on any VAT Report that you then create.  

    Depending on the requirements, you can use the same number series for all VAT reports, or separate number series for each type of VAT report.

    For example, if your company uses separate number series for standard and corrective VAT reports, this number series is the default number series. Users can select a different number series in the **No.** field when they create corrective reports.  

5.  On the **ZIVIT** FastTab, specify information for the fields.  
6.  Choose the **OK** button.  

## See Also  
 [VAT Reporting](vat-reporting.md)   
 [Create VAT Reports](how-to-create-vat-reports.md)
