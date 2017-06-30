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
# How to: Print VAT Reports-duplicate
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes VAT reports that you can use to submit information about VAT to the authorities. The following VAT reports are available for Germany:  
  
-   **Sales VAT Adv. Not. Acc. Proof**  
  
-   **VAT Statement Schedule**  
  
-   **VAT Statement Germany**  
  
 For more information, see [VAT Reporting](../vat-reporting.md).  
  
### To print the Sales VAT Adv. Not. Acc. Proof report  
  
1.  In the **Search** box, enter **Sales VAT Advance Notification**, and then choose the related link.  
  
2.  In the **Sales Advance VAT Notification** window, on the **Actions** tab, in the **Functions** group, choose **Sales VAT Adv. Not. Acc. Proof**.  
  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_11009\_N\_2\_1140011 Starting Date $\)**|Sets the start date.|  
    |**\($ R\_11009\_N\_2\_1140009 Ending Date $\)**|Sets the end date.|  
    |**\($ R\_11009\_N\_2\_1140007 Include VAT Entries $\)**|**Open** to include only open VAT entries in the report.<br /><br /> –or–<br /><br /> **Closed** to include only closed VAT entries in the report.<br /><br /> –or–<br /><br /> **Open and Closed** to include both open and closed VAT entries in the report.|  
    |**\($ R\_11009\_N\_2\_1140003 Include VAT Entries $\)**|**Before and Within Period** to display entries from both the period within the date filter and the period before the date filter in the report.<br /><br /> –or–<br /><br /> **Within Period** to display entries from the period within the date filter in the report.|  
    |**\($ R\_11009\_N\_2\_1140000 Show Amounts in Add. Reporting Currency $\)**|Select to display amounts in additional reporting currency.|  
  
4.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
### To print the VAT Statement Schedule report  
  
1.  In the **Search** box, enter **VAT Statements**, and then choose the related link.  
  
2.  In the **Name** field, select the relevant VAT statement name.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **VAT Statement Schedule**.  
  
4.  In the **VAT Statement Schedule** batch job, on the **VAT Statement Name** FastTab, select the appropriate filters.  
  
5.  On the **VAT Statement Line** FastTab, select the appropriate filters.  
  
6.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
### To print the VAT Statement Germany report  
  
1.  In the **Search** box, enter **VAT Statement Germany**, and then choose the related link.  
  
2.  In the **VAT Statement Germany** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_11005\_N\_2\_1140013 Starting Date $\)**|Sets the start date.|  
    |**\($ R\_11005\_N\_2\_1140011 Ending Date $\)**|Sets the end date.|  
    |**\($ R\_11005\_N\_2\_1140000 Include VAT Entries $\)**|**Open** to include only open VAT entries in the report.<br /><br /> –or–<br /><br /> **Closed** to include only closed VAT entries in the report.<br /><br /> –or–<br /><br /> **Open and Closed** to include both open and closed VAT entries in the report.|  
    |**\($ R\_11005\_N\_2\_1140004 Include VAT Entries $\)**|**Before and Within Period** to display entries from both the period within the date filter and the period before the date filter in the report.<br /><br /> –or–<br /><br /> **Within Period** to display entries from the period within the date filter in the report.|  
    |**\($ R\_11005\_N\_2\_1140009 Show Amounts in Add. Reporting Currency $\)**|Select to display amounts in additional reporting currency.|  
    |**\($ R\_11005\_N\_2\_1140007 Round to Whole Numbers $\)**|Select to round amounts to whole numbers.|  
  
3.  On the **VAT Statement Name** FastTab, select the appropriate filters.  
  
4.  On the **VAT Statement Line** FastTab, select the appropriate filters.  
  
5.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [VAT Reporting](../vat-reporting.md)   
 [How to: Preview VAT Statements](../how-to-preview-vat-statements.md)   
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](../electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 Sales VAT Adv. Not. Acc. Proof   
 VAT Statement Schedule   
 VAT Statement Germany