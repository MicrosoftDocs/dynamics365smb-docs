---
title: How to Create a VAT Statement
description: You can submit a periodic report of VAT transactions. The VAT statement is submitted as an FDF file that corresponds with an editable PDF file from the tax authorities.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: periodic report, VAT transactions, FDF file, VAT statement
ms.date: 03/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create a VAT statement

[!INCLUDE[prod_short](../../includes/prod_short.md)] allows you to submit a periodic report of VAT transactions. The VAT statement is submitted as an FDF file that corresponds with an editable PDF file from the tax authorities.  

> [!NOTE]  
> As of July 1st 2020, the Austrian authorities changed VAT on certain hospitality services to 5% as a temporary measure part of a plan to stimulate the economy in areas that are hit hard by COVID-19. If you have customers or vendors in the impacted areas, you must create VAT posting groups that reflect the correct VAT rate and use these for transactions created on or after July 1st 2020. To make sure that the new 5% VAT transactions get included correctly in the VAT statements, run the **Update VAT Statement** action from the **Search** field. This rebuilds the VAT statement and includes the 5% transactions, ready for reporting in the corresponding box in the official VAT statement PDF template. Additionally, make sure that you acquire the official PDF template to use for VAT reporting.  
> [!IMPORTANT]  
> You must fill in detailed information about your company address in the **Company Information** page before you create the VAT statement. This includes information about street, building, floor, and room number. This information is included in the FDF file.  

## Create a VAT statement

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement AT**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Period Date Type**|Specifies the type of date used for the period from which VAT entries are processed in the batch job.|
    |**Starting Date**|Specifies the start date of the VAT period.|  
    |**Ending Date**|Specifies the end date of the VAT period.|  
    |**Include VAT Entries**|Specifies if you want to include VAT entries that are either open or closed, or both open and closed entries.|  
    |**Include VAT Entries**|Specifies if you want to include VAT entries that are from the specified period or also include entries from before the period.|  
    |**Reporting Type**|Select if this VAT statement is the quarterly report, monthly report, or if it applies to another period.|  
    |**Check Positions**|Select to verify the positions of the VAT statement during the export.|  
    |**Round to Whole Numbers**|Select to round amounts to whole numbers.|  
    |**Surplus Used to Pay Dues**|Select to use a potential surplus to cover other charges.|  
    |**Additional Invoices sent via Mail**|Select if you send additional information.|  
    |**Number §6 Abs. 1**|Specify the number according to §6 section 1 if you want to claim tax-free revenues without input tax reduction.|  

1. Choose the **OK** button.  
1. When prompted, choose to save or open the generated XML file and FDF file.  

If your VAT statement doesn't contain errors, you can now submit the FDF file to the tax authorities. Learn more in [Finanz-Online portal](https://go.microsoft.com/fwlink/?LinkId=239929).  

## Related information

[VAT Reporting](vat-reporting.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
