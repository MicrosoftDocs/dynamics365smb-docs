---
title: "How to: Declare VAT-VIES Tax"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tax declarations, VAT-VIES"
  - "declaring VAT-VIES tax"
  - "VAT-VIES reports, declarations"
ms.assetid: 47e3a445-b284-4e07-b4a0-7e6d101f2031
caps.latest.revision: 22
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Declare VAT-VIES Tax
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes the VAT\-VIES declaration report, which you can use to submit information about sales transactions with other European Union \(EU\) countries\/regions to the customs and tax authorities' list system. The report displays information in the same format that is used in the customs and tax authorities' declaration list.  
  
 Depending on the volume of sales of goods or services to other EU countries\/regions, you must submit monthly, bi\-monthly, or quarterly declarations. If your company has sales of more than 100,000 euros per quarter, you must submit a monthly declaration. If your company has sales of less than 100,000 euros per quarter, you must submit a quarterly declaration. For more information, see the [BZSt website](http://go.microsoft.com/fwlink/?LinkId=204368).  
  
 The report is based on the [\($ T\_254 VAT Entry $\)](assetId:///e4113f5c-adc8-4bfd-8c4b-e7b5f11f4d32) table.  
  
### To declare VAT\-VIES tax  
  
1.  In the **Search** box, enter **\($ R\_11007 VAT\-Vies Declaration Tax – DE $\)**, and then choose the related link.  
  
2.  In the **\($ R\_11007 VAT\-Vies Declaration Tax – DE $\)** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_11007\_N\_2\_1140000 Reporting Period $\)**|Select the time period that the report applies to. This can be a month, a two\-month period, a quarter, or the calendar year.|  
    |**\($ R\_11007\_N\_2\_1140002 Date of Signature $\)**|Enter the date on which the VAT\-VIES declaration is sent.|  
    |**\($ R\_11007\_N\_2\_1140004 Corrected Notification $\)**|If selected, this field indicates that this is a corrected version of an already delivered VAT\-VIES declaration.|  
    |**\($ R\_11007\_N\_2\_1140006 Show Amounts in Add. Reporting Currency $\)**|If selected, the amounts of the report will be in the additional reporting currency. For more information, see [\($ T\_98\_68 Additional Reporting Currency $\)](assetId:///5264620d-b6cc-4d8a-b36a-b6e4a5714b36).|  
    |**\($ R\_11007\_N\_2\_1140009 Change to monthly reporting $\)**|If selected, your company has sales of more than 100,000 euros per quarter and you must migrate from a quarterly report to a monthly report. **Important:**  Only select this field the first time that you submit a monthly report.|  
    |**\($ R\_11007\_N\_2\_1140011 Revoke monthly reporting $\)**|If selected, you want to switch from monthly reporting to another reporting period.<br /><br /> For example, if you have previously submitted monthly declarations but the EU sales are less than 100,000 euros per quarter, select this field and then select one of the quarters in the **\($ R\_11007\_N\_2\_1140000 Reporting Period $\)** field.|  
  
3.  On the **VAT Entry** FastTab, select the appropriate filters.  
  
    > [!NOTE]  
    >  In order to run this report, you must select the **Posting Date** as a filter, and enter the posting date value.  
  
 You can print the declaration on paper or create an XML file that you can submit electronically to the tax authorities. For more information, see the [BZSt website](http://go.microsoft.com/fwlink/?LinkId=204368).  
  
## See Also  
 [VAT\-VIES Reporting\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/vat-vies-reporting-duplicate.md)   
 [VAT Reporting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/vat-reporting.md)   
 [\($ R\_11007 VAT\-Vies Declaration Tax \- DE $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-r_11007-vat-vies-declaration-tax-de-$-.md)   
 [\($ T\_254 VAT Entry $\)](assetId:///e4113f5c-adc8-4bfd-8c4b-e7b5f11f4d32)