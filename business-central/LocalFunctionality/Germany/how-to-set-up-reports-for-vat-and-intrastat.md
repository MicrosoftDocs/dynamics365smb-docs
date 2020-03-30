---
    title: How to Set Up Reports for VAT and Intrastat
    description: You can specify which reports to use to create the documents that you must submit to the authorities, such as the VAT statement and the Intrastat form.

    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Set Up Reports for VAT and Intrastat
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can specify which reports to use to create the documents that you must submit to the authorities, such as the VAT statement and the Intrastat form.  

### To set up reports for VAT  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Selections VAT**, and then choose the related link.  

2.  On the **Report Selection – VAT** page, in the **Usage** field, select the type of document that you want to specify reports for. This includes the VAT statement and the VAT statement schedule.  

3.  Specify the report or batch job that must run when a user starts the activity for the document type that you specified in the **Usage** field. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sequence**|Specifies where a report is in the printing order.|  
    |**Report ID**|Specifies the ID of the report that prints for this document type.|  
    |**Report Name**|Specifies the name of the report that prints for this document type. The **Report Name** field updates based on the selection in the **Report ID** field.|  

4.  Choose the **OK** button.  

### To set up reports for Intrastat  
> [!NOTE]
> Intrastat reports can use either the XML or ASCII formats. Depending on the format you use, enter the material number in one of the following fields on the **Company  Information** page.  
> 
> |Format|Fields|
> |---------|---------|
> |XML|Company No.|
> |ASCII|Sales Material No., Purchase Material No.|

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Selection**, and then choose the related link.  

2.  On the **Report Selection – Intrastat** page, in the **Usage** field, select the type of document that you want to specify reports for. This includes the Intrastat checklist and Intrastat form.  

3.  Specify the report or batch job that must run when a user starts the activity for the document type that you specified in the **Usage** field. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sequence**|Specifies where a report is in the printing order.|  
    |**Report ID**|Specifies the ID of the report that prints for this document type.|  
    |**Report Name**|Specifies the name of the report that prints for this document type. The **Report Name** field updates based on the selection in the **Report ID** field.|  

4.  Choose the **OK** button.  

## See Also  
[Export and Print Intrastat Reports](how-to-export-and-print-intrastat-reports.md)  
[VAT Reporting](vat-reporting.md)
