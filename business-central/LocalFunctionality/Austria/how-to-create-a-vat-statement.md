---
    title: How to Create a VAT Statement
    description: You can submit a periodic report of VAT transactions. The VAT statement is submitted as an FDF file that corresponds with an editable PDF file from the tax authorities.
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
# Create a VAT Statement
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] allows you to submit a periodic report of VAT transactions. The VAT statement is submitted as an FDF file that corresponds with an editable PDF file from the tax authorities.  

> [!IMPORTANT]  
>  You must fill in detailed information about your company address in the Company Information page before you create the VAT statement. This includes information about street, building, floor, and room number. This information is included in the FDF file.  

## To create a VAT statement  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Statement AT**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Specifies the start date of the VAT period.|  
    |**Ending Date**|Specifies the end date of the VAT period.|  
    |**Include VAT Entries**|Specifies if you want to include VAT entries that are either open or closed, or both open and closed entries.|  
    |**Include VAT Entries**|Specifies if you want to include VAT entries that are from the specified period or also include entries from before the period.|  
    |**Reporting Type**|Select if this VAT statement is the quarterly report, monthly report, or if it applies to another period.|  
    |**Check Positions**|Select to verify the positions of the VAT statement during the export.|  
    |**Round to Whole Numbers**|Select to round amounts to whole numbers.|  
    |**Surplus Used to Pay Dues**|Select to use a potential surplus to cover other charges.|  
    |**Additional Invoices sent via Mail**|Select if you will send additional information.|  
    |**Number §6 Abs. 1**|Specify the number according to §6 section 1 if you want to claim tax-free revenues without input tax reduction.|  

3.  Choose the **OK** button.  
4.  When prompted, choose to save or open the generated XML file and FDF file.  

If your VAT statement does not contain errors, you can now submit the FDF file to the tax authorities. For more information, see the [Finanz-Online portal](https://go.microsoft.com/fwlink/?LinkId=239929).  

## See Also  
[VAT Reporting](vat-reporting.md)
