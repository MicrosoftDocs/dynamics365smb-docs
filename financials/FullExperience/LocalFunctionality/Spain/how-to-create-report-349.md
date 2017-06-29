---
title: "How to: Create Report 349"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "349 report, submitting"
  - "Report 349, submitting"
ms.assetid: e4117fb3-8830-4939-860c-23a5aa386c91
caps.latest.revision: 10
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# How to: Create Report 349
You must submit a periodic report of trade with other EU countries\/regions to the tax authorities. This declaration, Report 349, must be submitted to the tax authorities electronically on the tax agency website or on a CD\-ROM. For more information, see the [Spanish Tax Agency](http://go.microsoft.com/fwlink/?LinkId=238181) website.  
  
### To create Report 349  
  
1.  In the **Search** box, enter **\($ B\_10709 Make 349 Declaration $\)**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_10710\_N\_2\_1100011 Fiscal Year $\)**|Specify the year of the reporting period.|  
    |**\($ B\_10710\_N\_2\_1100013 Period $\)**|Select the period that the report covers. This can be a year, a month, or a quarter.|  
    |**\($ B\_10710\_N\_2\_1100000 Period Frequency Change $\)**|Select to change the period frequency of the report.|  
    |**\($ B\_10710\_N\_2\_1100015 Contact Name $\)**|Specify the contact name for your company.|  
    |**\($ B\_10710\_N\_2\_1100017 Telephone Number $\)**|Specify the telephone number for contact.|  
    |**\($ B\_10710\_N\_2\_1100019 Declaration Number $\)**|Specify the number of the declaration. For example, if this is your first 349 declaration, the number is **3490000000000**.|  
    |**\($ B\_10710\_N\_2\_1100021 Company Country\/Region $\)**|Enter the country\/region for your company.|  
    |**\($ B\_10710\_N\_2\_1100001 Declaration Media Type $\)**|Select the media type for the declaration.<br /><br /> To submit the declaration electronically, select **Telematic**.<br /><br /> To submit the declaration on CD\-ROM, select **Physical support**. If you want to submit the 349 declaration on a CD\-ROM, you must also print labels for the disk. For more information, see Declaration Labels.|  
    |**\($ B\_10710\_N\_2\_1100004 Excluded Gen. Product Posting Groups $\)**|Specify the general product posting group that you do not want to include in the declaration.|  
  
3.  Choose the **OK** button.  
  
 If the period includes a credit memo, a message appears, and if you choose the **OK** button, the **\($ N\_10736 Customer\/Vendor Warnings 349 $\)** window opens and shows all credit memos for that period.  
  
 Entries related to credit memos display in the **\($ N\_10736 Customer\/Vendor Warnings 349 $\)** window because you may want to include them as corrections to invoices. For example, if you posted a sales invoice in October, and you then post a credit memo in November that corrects the October invoice, a warning displays. Then, you can make the appropriate changes in the **\($ N\_10736 Customer\/Vendor Warnings 349 $\)** window. You must specify which section of the total amount for that customer must be included in the November 349 declaration.  
  
### To correct warnings for Report 349  
  
1.  In the **\($ N\_10736 Customer\/Vendor Warnings 349 $\)** window, select the line for the relevant customer.  
  
2.  Make the appropriate changes to the line.  
  
     The following table describes the key fields for correcting a 349 declaration that includes a credit memo.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Include Correction**|Select to accept the correction that the credit memo has resulted in.|  
    |**Delivery Operation Code**|Specifies the type of export delivery for the VAT transaction.<br /><br /> If you select a month in the **Original Declaration Period** field, the **Delivery Operation Code** field helps you identify the appropriate amount, which is shown in the **Previous Declared Amount** field.|  
    |**Previous Declared Amount**|Specifies the total amount that has been included in a 349 declaration.<br /><br /> This field is calculated only if you changed the **Original Declaration Period** field. It is calculated based on the specified delivery operation code.|  
    |**Original Declaration FY**|Specifies the fiscal year that the original 349 declaration was submitted to the tax authorities with the invoice that this credit memo corrects. **Warning:**  Do not change this field if the credit memo applies to an invoice that has not yet been declared to the tax authorities because it is part of the current 349 declaration.|  
    |**Original Declaration Period**|Specifies the month, such as **01** for the month of January, for the original 349 declaration that included the invoice that this credit memo corrects. **Warning:**  Do not change this field if the credit memo applies to an invoice that has not yet been declared to the tax authorities because it is part of the current 349 declaration.|  
    |**Original Declared Amount**|Specifies the correction for the original transaction.<br /><br /> For a credit memo for an invoice that was included in an earlier 349 declaration, enter the amount that should have been declared for this customer or vendor. This amount is the invoiced amount less the credit memo amount.<br /><br /> For a credit memo for an invoice that is part of the current 349 declaration, enter the credit memo amount.|  
  
3.  When you have made the appropriate changes, on the **Home** tab, choose **Process**.  
  
     A window appears where you must confirm that you want to update the 349 declaration for those entries where the **Include Correction** field is selected.  
  
 For corrections to amounts that were included in an earlier 349 declaration, the window can show more than one warning for a customer or vendor with the same values in the **Original Declaration FY** and **Original Declaration Period** fields. In that case, you should combine the corrections in a single line so that the appropriate amounts for the **Previous Declared Amount** field and the **Original Declared Amount** field are included in the 349 declaration.  
  
## See Also  
 [Report 349](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/report-349.md)   
 Make 349 Declaration   
 Declaration Labels