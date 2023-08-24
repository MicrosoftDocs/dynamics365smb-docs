---
    title: How to Set Up VAT Reports [DE]
    description: To file a VAT report under the ELMA5 system from Business Central, you need to set up report parameters.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/18/2021
    ms.author: bholtorf

---
# Set Up VAT Reports in the German Version
Information from various invoice types is used to feed data into the EU Sales List report. To file a VAT report under the ELMA5 system from [!INCLUDE[prod_short](../../includes/prod_short.md)], you need to set up report parameters.  

## To set up a VAT report  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Report Setup**, and then choose the related link.  
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]