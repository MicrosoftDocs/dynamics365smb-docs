---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Make Manual Corrections to VAT
You can make corrections to posted VAT entries without posting the correction into the VAT or general ledger entries. This is useful if you need to make a change to the total sales or purchases VAT amounts without changing the VAT base. For example, you can manually correct VAT if you receive an invoice from a vendor who has calculated VAT incorrectly.  
  
### To make manual corrections to VAT  
  
1.  In the **Search** box, enter **VAT Statement Preview**, and then choose the related link.  
  
2.  Select the line that needs to be corrected. You can make the VAT correction on both the **Row Totaling** and **VAT Entry Totaling** row **Type**.  
  
3.  To make the correction, choose the **Correction Amount** field. The **Manual VAT Correction List** window opens.  
  
4.  On the **Home** tab, in the **Manage** group, choose **Edit List**. In the **Manual VAT Correction List** window, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Posting Date**|Enter the posting date of the VAT correction.|  
    |**Amount**|Enter the amount of the VAT correction. You must enter the correction amount, not the new amount. For example, if the amount is 1000.00 and should be 1200.00, enter 200.00.|  
    |**Additional-Currency Amount**|This field displays the amount of the VAT correction in the additional reporting currency.<br /><br /> The field is automatically calculated, based on the contents of the **Amount** field and the current exchange rate.|  
  
5.  Choose the **OK** button.  
  
6.  Refresh the **VAT Statement Preview** window to see your corrections.  
  
7.  To view a report related to the preview of the VAT information, on the **Home** tab, in the **Report** group, choose one of the following actions:  
  
    |Action|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |------------|---------------------------------------|  
    |**Detailed Report**|Opens the **VAT Statement** report. For more information, see VAT Statement.|  
    |**Form\/Intervat Declaration**|Opens the **VAT –Form** report. For more information, see VAT - Form.<br /><br /> The **Form\/Intervat Declaration** report is based on the VAT Statement template that is defined in the general ledger setup. Therefore, it may export data that is not the same as what is shown in the **VAT Statement Preview** window.|  
    |**Declaration Summary Report**|Opens the **VAT Statement Summary** report. For more information, see VAT Statement Summary.|  
  
## See Also  
 [Belgian VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-vat.md)   
 [How to: Print Periodic VAT Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-print-periodic-vat-reports.md)   
 [How to: Set Up Non-Deductible VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-non-deductible-vat.md)