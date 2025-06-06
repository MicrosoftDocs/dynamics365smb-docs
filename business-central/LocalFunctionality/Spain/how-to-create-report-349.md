---
title: Create Report 349 [ES]
description: Learn how to use the Spanish version of Business Central to electronically submit the report 349 declaration to the tax authorities.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: report 349 declaration, create report 349, report 349 creation, report 349, Spanish version
ms.search.form: 10736
ms.date: 05/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create report 349 in the Spanish version

You must submit a periodic report of trade with other EU countries/regions to the tax authorities. This declaration, report 349, must be submitted to the tax authorities electronically on the tax agency website or on a CD-ROM. Learn more in [Spanish Tax Agency](https://go.microsoft.com/fwlink/?LinkId=238181) website.  

## Create report 349  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Make 349 Declaration**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Fiscal Year**|Specify the year of the reporting period.|  
    |**Period**|Select the period that the report covers. This can be a year, a month, or a quarter.|  
    |**Period Frequency Change**|Select to change the period frequency of the report.|  
    |**Contact Name**|Specify the contact name for your company.|  
    |**Telephone Number**|Specify the telephone number for contact.|  
    |**Declaration Number**|Specify the number of the declaration. For example, if this is your first 349 declaration, the number is **3490000000000**.|  
    |**Company Country/Region**|Enter the country/region for your company.|  
    |**Declaration Media Type**|Select the media type for the declaration.<br><br/> To submit the declaration electronically, select **Telematic**.<br><br/> To submit the declaration on CD-ROM, select **Physical support**. If you want to submit the 349 declaration on a CD-ROM, you must also print labels for the disk. For more information, see Declaration Labels.|  
    |**Excluded Gen. Product Posting Groups**|Specify the general product posting group that you don't want to include in the declaration.|  

1. Choose the **OK** button.  

If the period includes a credit memo, a message appears, and if you choose the **OK** button, the **Customer/Vendor Warnings 349** page opens and shows all credit memos for that period.  

Entries related to credit memos display on the **Customer/Vendor Warnings 349** page because you may want to include them as corrections to invoices. For example, if you posted a sales invoice in October, and you then post a credit memo in November that corrects the October invoice, a warning displays. Then, you can make the appropriate changes on the **Customer/Vendor Warnings 349** page. You must specify which section of the total amount for that customer must be included in the November 349 declaration.  

## Correct warnings for report 349  

1. On the **Customer/Vendor Warnings 349** page, select the line for the relevant customer.  
1. Make the appropriate changes to the line.  

    The following table describes the key fields for correcting a 349 declaration that includes a credit memo.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Include Correction**|Select to accept the correction that the credit memo has resulted in.|  
    |**Delivery Operation Code**|Specifies the type of export delivery for the VAT transaction.<br><br/> If you select a month in the **Original Declaration Period** field, the **Delivery Operation Code** field helps you identify the appropriate amount, which is shown in the **Previous Declared Amount** field.|  
    |**Previous Declared Amount**|Specifies the total amount that is included in a 349 declaration.<br><br/> This field is calculated only if you changed the **Original Declaration Period** field. It's calculated based on the specified delivery operation code.|  
    |**Original Declaration FY**|Specifies the fiscal year that the original 349 declaration was submitted to the tax authorities with the invoice that this credit memo corrects. **Warning:**  Don't change this field if the credit memo applies to an invoice that hasn't yet been declared to the tax authorities because it's part of the current 349 declaration.|  
    |**Original Declaration Period**|Specifies the month, such as **01** for the month of January, for the original 349 declaration that included the invoice that this credit memo corrects. **Warning:**  Don't change this field if the credit memo applies to an invoice that hasn't yet been declared to the tax authorities because it's part of the current 349 declaration.|  
    |**Original Declared Amount**|Specifies the correction for the original transaction.<br><br/> For a credit memo for an invoice that was included in an earlier 349 declaration, enter the amount that should have been declared for this customer or vendor. This amount is the invoiced amount less the credit memo amount.<br><br/> For a credit memo for an invoice that is part of the current 349 declaration, enter the credit memo amount.|  

1. After making the appropriate changes, choose the **Process** action.  

   A page appears where you must confirm that you want to update the 349 declaration for those entries where the **Include Correction** checkbox is selected.  

For corrections to amounts that were included in an earlier 349 declaration, the page can show more than one warning for a customer or vendor with the same values in the **Original Declaration FY** and **Original Declaration Period** fields. In that case, you should combine the corrections in a single line so that the appropriate amounts for the **Previous Declared Amount** field and the **Original Declared Amount** field are included in the 349 declaration.  

## Related information

[Report 349](report-349.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
