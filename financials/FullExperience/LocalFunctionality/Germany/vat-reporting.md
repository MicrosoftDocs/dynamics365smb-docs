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
# VAT Reporting
You can report VAT electronically to the tax authorities. You can generate, electronically sign, encrypt, and send an XML file directly to the German ELSTER portal. Response messages are received and processed in the same transaction.  
  
 You can print the following local VAT reports.  
  
|Report|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
|------------|---------------------------------------|  
|**VAT Statement Germany**|A simple VAT report. The main VAT reporting is handled by the ELSTER functionality. The amounts are differentiated by taxable base and taxable amount.<br /><br /> Serves as the basis for VAT registration for a selected period, and is printed according to the VAT statement in the VAT Statement Line table.<br /><br /> Use this report in conjunction with VAT correction. For more information, see [How to: Correct VAT](../../Finance/how-to-correct-vat.md).|  
|**VAT Statement AT**|The Austrian VAT statement serves as the basis for VAT registration for a selected period, and is printed according to the VAT statement in the VAT Statement Line table. You can generate the report in three different formats. For more information, see VAT Statement AT.|  
|**Sales VAT Adv. Not. Acc. Proof**|Confirms that entries in the VAT statement form are also posted in general ledger accounts.<br /><br /> To verify VAT in sales VAT advance notifications, select the same settings for the VAT statement form and the sales VAT advance notification.|  
|**VAT Statement Schedule**|This report can be retrieved from the **VAT Statement** form.<br /><br /> Prints the settings in the VAT statement. Using this report, you can print the characteristics of the **Sales VAT Adv. Not. Acc. Proof**.|  
  
## See Also  
 [How to: Print VAT Reports-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-print-vat-reports-duplicate.md)   
 VAT Statement Line   
 [How to: Correct VAT](../../Finance/how-to-correct-vat.md)   
 VAT Statement AT   
 VAT Statement Germany   
 Sales VAT Adv. Not. Acc. Proof   
 VAT Statement Schedule   
 VAT Statement Schedule   
 [How to: Set Up Reports for VAT and Intrastat](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-set-up-reports-for-vat-and-intrastat.md)