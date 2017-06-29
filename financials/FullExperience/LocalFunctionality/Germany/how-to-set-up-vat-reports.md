---
title: "How to: Set Up VAT Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 05638471-2c68-48a4-9d5a-19a6679674fd
caps.latest.revision: 5
ms.author: "edupont"
translation.priority.ht: 
  - "de-de"
---
# How to: Set Up VAT Reports
Information from various invoice types is used to feed data into the EU Sales List report. To file a VAT report under the ELMA5 system from [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you need to set up report parameters.  
  
### To set up a VAT report  
  
1.  In the **Search** box, enter **VAT Report Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, select the **Modify Submitted Reports** check box to let users modify VAT reports that have been submitted to the tax authorities.  
  
     If the field is left blank, users must create a corrective VAT report instead.  
  
3.  Select the **Export Cancellation Lines** check box if you want to include information about cancellation lines when you export data for the VAT report of EU sales. For more information, see [How to: Correct VAT Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-correct-vat-reports.md).  
  
4.  On the **Numbering** FastTab, specify the number series that will be used for standard VAT reports. This will be the default numbering series that is used on any VAT Report that you then create.  
  
     Depending on the requirements, you can use the same number series for all VAT reports, or separate number series for each type of VAT report. For more information, see No. Series.  
  
     For example, if your company uses separate number series for standard and corrective VAT reports, this number series is the default number series. Users can select a different number series in the **No.** field when they create corrective reports.  
  
5.  On the **ZIVIT** FastTab, specify information for the fields.  
  
6.  Choose the **OK** button.  
  
## See Also  
 [VAT Reporting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/vat-reporting.md)   
 [How to: Create VAT Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-create-vat-reports.md)