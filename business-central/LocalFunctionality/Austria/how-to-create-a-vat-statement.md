---
title: How to Create a VAT Statement
description: You can submit a periodic report of VAT transactions. The VAT statement is submitted as an FDF file that corresponds with an editable PDF file from the tax authorities.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: periodic report, VAT transactions, FDF file, VAT statement
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Create a VAT statement

[!INCLUDE[prod_short](../../includes/prod_short.md)] lets you submit a periodic report of VAT transactions. The VAT statement is submitted as an FDF file that corresponds with an editable PDF file from the tax authorities.  

> [!NOTE]  
> As of July 1, 2026, Austria introduced a reduced VAT rate of 4.9%. If you have transactions that use this rate, create VAT posting groups that reflect it. When you create the VAT statement, the base amounts for domestic and intra-community 4.9% transactions are automatically included in positions KZ124 and KZ125 in both the XML file and the U30 PDF form.  
> [!IMPORTANT]  
> You must fill in detailed information about your company address on the **Company Information** page before you create the VAT statement. This includes the street, house number, floor number, and room number. This information is included in the FDF file.  

## Create a VAT statement

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement Austria**, and then select the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Specifies the start date of the VAT period.|  
    |**Ending Date**|Specifies the end date of the VAT period.|  
    |**Include VAT Entries**|Specifies if you want to include VAT entries that are either open or closed, or both open and closed entries.|  
    |**Include VAT Entries**|Specifies if you want to include VAT entries that are from the specified period or also include entries from before the period.|  
    |**Reporting Type**|Specifies if this VAT statement is the quarterly report, monthly report, or if it applies to another period.|  
    |**Check Positions**|Specifies that you want to verify the positions of the VAT statement during the export.|  
    |**Round to Whole Numbers**|Specifies if you want the amounts to be rounded to whole numbers.|  
    |**Surplus Used to Pay Dues**|Specifies if you want to use a potential surplus to cover other charges.|  
    |**Additional Invoices sent via Mail**|Specifies if you want to send additional information.|  
    |**Number Art. 6 Abs. 1**|Specifies the number according to article 6 section 1 if you want to claim tax-free revenues without input tax reduction.|  

1. Select **OK**.  
1. When prompted, choose to save or open the generated XML file and FDF file.  

If your VAT statement doesn't contain errors, you can now submit the FDF file to the tax authorities. Learn more at [FinanzOnline](https://go.microsoft.com/fwlink/?LinkId=239929).  

## Related information

[VAT Reporting](vat-reporting.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
