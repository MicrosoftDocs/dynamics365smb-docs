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
# How to: Create an EU Sales List
Companies that run VAT\-registered businesses and sell or move goods to other VAT\-registered businesses in the European Union \(EU\) must record and report about data on their sales activities to the government.  
  
 All companies that sell more than a set value every year to EU states must submit an electronic version of their European Community \(EC\) sales list report in XML format through Her Majesty's Revenue and Customs \(HMRC\) web site.  
  
 This report displays one line of information for each customer who consolidates invoices. The report is based on the information in the **VAT Entry** table. The sales information in this report is in the same format as on the declaration form issued by the customs and tax authorities.  
  
### To create an EU community sales list  
  
1.  In the **Search** box, enter **EC Sales List**, and then choose the related link.  
  
2.  In the **EC Sales List** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_130\_N\_2\_1 Print Third Party Trade As $\)**|Specify how you want to print third\-party trade. Choose **Separate Lines** to create the report with third\-party trade as a separate line for each customer. Choose **Column with Amount** to create the report with third\-party trade as an additional column.|  
    |**\($ R\_130\_N\_2\_1000004 Create XML File $\)**|Select to create an electronic version of the **EC Sales List** report in XML file format.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 VAT Entry   
 [EC Sales List\-duplicate](../Topic/\($%20R_130%20EC%20Sales%20List%20$\)-duplicate.md)   
 [United Kingdom Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/united-kingdom-local-functionality.md)