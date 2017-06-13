---
title: "How to: Set Up VAT Reports-duplicate"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT reports, setting up"
ms.assetid: 16495586-13a0-4b11-a358-086ff90b3e74
caps.latest.revision: 13
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up VAT Reports-duplicate
You can create different types of VAT reports depending on the requirements of your country\/region. Before you can create and submit VAT reports, you must set up a number series.  
  
### To set up VAT reports  
  
1.  In the **Search** box, enter **VAT Report Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, select the **Modify Submitted Reports** field to let users modify VAT reports that have been submitted to the tax authorities.  
  
     If the field is left blank, users must create a corrective VAT report instead.  
  
3.  On the **Numbering** FastTab, specify the number series that will be used for standard VAT reports.  
  
     Depending on the requirements, you can use the same number series for all VAT reports, or separate number series for each type of VAT report. For more information, see [No. Series](assetId:///18dc626f-cdf2-4bd9-b1ab-d98927ce4c3b).  
  
     For example, if your company uses separate number series for standard and corrective VAT reports, this number series is the default number series. Users can select a different number series in the **No.** field when they create corrective reports.  
  
## Creating VAT Reports  
 You can configure different types of VAT reports based on requirements. Then, when you must submit a VAT report, you can create it in the **VAT Report** window and then print it or export it in electronic format.  
  
#### To create a VAT report  
  
1.  In the **Search** box, enter **VAT Report**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specify the report number.<br /><br /> Depending on the type of report, and the configuration in your company, you can use the automatically generated number, select a different number series, or enter a different number manually.|  
    |**VAT Report Config. Code**|Select the appropriate configuration code.<br /><br /> The configuration code specifies how the VAT report is generated. For more information, see [VAT and VIES Report Setup](../Finance/vat-and-vies-report-setup.md).|  
    |**VAT Report Type**|Specify if you want to create a standard, corrective, or supplementary VAT report.|  
    |**Reference VAT Report**|Specify the original VAT report if you selected a value that is not **Standard** in the **VAT Report Type** field.|  
    |**Start Date**|Specify the start date of the report period.|  
    |**End Date**|Specify the end date of the report period.|  
  
     Now, you must import the VAT ledger entries that must be included in this VAT report.  
  
3.  On the **Actions** tab, choose **Suggest Lines**.  
  
     This adds lines to the window. Optionally, for each line, in the **Amount** field, you can drill down to see the VAT ledger entries that resulted in this line.  
  
 Now that you have created the VAT report, you must submit it to the tax authorities.  
  
#### To submit a VAT report  
  
1.  In the **Search** box, enter **VAT Report List**, and then choose the related link.  
  
2.  Select the appropriate VAT report, and then choose **Edit**.  
  
3.  On the **Home** tab, choose **Release**.  
  
     [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] validates that the VAT report is set up correctly. If the validation fails, the errors are shown in the **VAT Report Error Log** window so that you can make the appropriate changes. For example, an error displays if you try to release a standard VAT report but you have not yet added any lines to the report.  
  
     When you mark a VAT report as released, it becomes non\-editable. If you must change the report after marking it as released, you must first reopen it.  
  
4.  On the **Home** tab, choose **Print** or choose **Export**.  
  
     You can now submit the report to the tax authorities.  
  
5.  On the **Home** tab, choose **Mark as Submitted**.  
  
 If you must submit a corrective VAT report or delete a submitted VAT report, you must create a new VAT report as described earlier.  
  
## See Also  
 [VAT and VIES Report Setup](../Finance/vat-and-vies-report-setup.md)   
 [No. Series](assetId:///18dc626f-cdf2-4bd9-b1ab-d98927ce4c3b)