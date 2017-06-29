---
title: "How to: Create a VAT Statement"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, statements"
ms.assetid: 7906e872-a814-4d53-91d3-ad1936deaacd
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "de-at"
---
# How to: Create a VAT Statement
FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> allows you to submit a periodic report of VAT transactions. The VAT statement is submitted as a FDF file that corresponds with an editable PDF file from the tax authorities.  
  
> [!IMPORTANT]  
>  You must fill in detailed information about your company address in the Company Information window before you create the VAT statement. This includes information about street, building, floor, and room number. This information is included in the FDF file.  
  
### To create a VAT statement  
  
1.  In the **Search** box, enter **VAT Statement AT**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_11110\_N\_2\_1160010 Starting Date $\)**|Specifies the start date of the VAT period.|  
    |**\($ B\_11110\_N\_2\_1160012 Ending Date $\)**|Specifies the end date of the VAT period.|  
    |**\($ B\_11110\_N\_2\_8 Include VAT Entries $\)**|Specifies if you want to include VAT entries that are either open or closed, or both open and closed entries.|  
    |**\($ B\_11110\_N\_2\_4 Include VAT Entries $\)**|Specifies if you want to include VAT entries that are from the specified period or also include entries from before the period.|  
    |**\($ B\_11110\_N\_2\_11 Reporting Type $\)**|Select if this VAT statement is the quarterly report, monthly report, or if it applies to another period.|  
    |**\($ B\_11110\_N\_2\_1160007 Check Positions $\)**|Select to verify the positions of the VAT statement during the export.|  
    |**\($ B\_11110\_N\_2\_1 Round to Whole Numbers $\)**|Select to round amounts to whole numbers.|  
    |**\($ B\_11110\_N\_2\_1160003 Surplus Used to Pay Dues $\)**|Select to use a potential surplus to cover other charges.|  
    |**\($ B\_11110\_N\_2\_1160005 Additional Invoices sent via Mail $\)**|Select if you will send additional information.|  
    |**\($ B\_11110\_N\_2\_1160000 Number §6 Abs. 1 $\)**|Specify the number according to §6 section 1 if you want to claim tax\-free revenues without input tax reduction.|  
  
3.  Choose the **OK** button.  
  
4.  When prompted, choose to save or open the generated XML file and FDF file.  
  
 If your VAT statement does not contain errors, you can now submit the FDF file to the tax authorities. For more information, see the [Finanz\-Online portal](http://go.microsoft.com/fwlink/?LinkId=239929).  
  
## See Also  
 [VAT Reporting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/vat-reporting.md)   
 VAT Statement AT   
 Company Information