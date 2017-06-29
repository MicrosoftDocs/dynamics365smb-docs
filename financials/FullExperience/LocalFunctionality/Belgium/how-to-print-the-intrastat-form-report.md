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
# How to: Print the Intrastat Form Report
The **Intrastat - Form** report must be used for reporting to Intrastat. In Belgium, you must report the movement of goods to the statistics authorities every month, and the report must be sent to the tax authorities.  
  
 Before you print the **Intrastat - Form** report, you can also print the **Intrastat Checklist** report to verify the contents of the report.  
  
### To print the Intrastat form report  
  
1.  In the **Search** box, enter **Intrastat – Form**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_501\_F\_1\_1010002 Name $\)**|Enter the company name.|  
    |**\($ R\_501\_F\_1\_1010004 Address $\)**|Enter the address.|  
    |**\($ R\_501\_F\_1\_1010006 Post Code \+ City $\)**|Enter the postal code and the city.|  
    |**\($ R\_501\_F\_1\_1010008 Contact $\)**|Enter the name of the contact person.|  
    |**\($ R\_501\_F\_1\_1010010 Telephone $\)**|Enter the telephone number of the contact person.|  
    |**\($ R\_501\_F\_1\_1010012 Telefax $\)**|Enter the telefax number.|  
    |**\($ R\_501\_F\_1\_1010014 International VAT number $\)**|Enter the international VAT registration number.|  
    |**\($ R\_501\_F\_1\_1010019 Nihil declaration $\)**|Select if you do not have any trade transactions with EU countries and want to send an empty declaration. When selected, the message "NIHIL" displays in the **Message** field.|  
    |**\($ R\_501\_F\_1\_1010017 Message $\)**|Enter a message to be printed on the Intrastat declaration, such as "regular declaration" or "replacement declaration".|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Belgian Intrastat Reporting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-intrastat-reporting.md)   
 [How to: Set Up Declaration Types](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-declaration-types.md)   
 [How to: Set Up Belgian Tariff Numbers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-belgian-tariff-numbers.md)   
 [How to: Set Up Intrastat Establishment Numbers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-intrastat-establishment-numbers.md)   
 [How to: Export Intrastat Third-Party Declararations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-export-intrastat-third-party-declararations.md)