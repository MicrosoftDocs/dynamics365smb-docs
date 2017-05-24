---
title: "How to: Print General Ledger Setup Information"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "general ledger, printing setup information"
ms.assetid: dd8bcfb8-a980-4cc2-baa8-32aac571db3b
caps.latest.revision: 20
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-at"
  - "de-ch"
  - "de-de"
  - "fr-ch"
---
# How to: Print General Ledger Setup Information
Before you use [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] in the daily business, you can run the **\($ R\_11514 G\/L Setup Information $\)** report to display the master data that you have set up. You can look over this master data so that you have a baseline to compare to, and then verify that you have set up posting groups correctly, for example.  
  
### To print general ledger setup information  
  
1.  In the **Search** box, enter **\($ R\_11514 G\/L Setup Information $\)**, and then choose the related link.  
  
2.  On the **Options** FastTab, in the **Setup Information** field, select the master data area as described in the following table.  
  
    |[!INCLUDE[bp_optionsheading](../../DesignAndEngineering/includes/bp_optionsheading_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |-------------------------------------|---------------------------------------|  
    |**G\/L Setup \- Company Data \- Consolidation**|Displays tables for general ledger setup, company information, and business units.|  
    |**Posting Groups**|Displays customer posting group tables, vendor posting group tables, inventory posting group tables, and bank account posting group tables.|  
    |**Posting Matrix**|Displays general business posting group tables, general product posting group tables, and general posting group tables.|  
    |**VAT Setup**|Displays VAT business posting group tables, VAT product posting group tables, and VAT posting setup tables.|  
    |**Source Code \- Reason Code**|Displays source tables, source code setup tables, and reason codes tables.|  
    |**Check Number Series**|Select to provide an overview of the use of number series so that you can identify number series that are problematic for the data export for the Grundsätze zum Datenzugriff und zur Prüfbarkeit digitaler Unterlagen \(GDPdU\). The report will show number series with one of the following issues:<br /><br /> -   The number series allows manual document numbers.<br />-   The number series is not chronological.<br />-   The number series is used in more than one table or field.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [\($ R\_11514 G\-L Setup Information $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-r_11514-g-l-setup-information-$-.md)   
 [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6)   
 [\($ T\_79 Company Information $\)](assetId:///2a44e662-0d42-429e-8131-e0012a89996a)   
 [\($ T\_220 Business Unit $\)](assetId:///bee5745b-543d-4588-90d6-4a6c79e2ce2b)   
 [\($ T\_92 Customer Posting Group $\)](../Topic/\($%20T_92%20Customer%20Posting%20Group%20$\).md)   
 [\($ T\_93 Vendor Posting Group $\)](../Topic/\($%20T_93%20Vendor%20Posting%20Group%20$\).md)   
 [\($ T\_94 Inventory Posting Group $\)](../Topic/\($%20T_94%20Inventory%20Posting%20Group%20$\).md)   
 [\($ T\_277 Bank Account Posting Group $\)](assetId:///b4a12ab6-0240-49f6-9d98-c561515d25fd)   
 [\($ T\_250 Gen. Business Posting Group $\)](assetId:///b4468ee4-0324-4b46-80b5-efa5b5c1ad28)   
 [\($ T\_251 Gen. Product Posting Group $\)](assetId:///850fd887-5799-4852-b2d5-5ec44f485dd8)   
 [\($ T\_252 General Posting Setup $\)](assetId:///8d1129f7-d16d-40a2-a351-8a1aed5953b3)   
 [\($ T\_323 VAT Business Posting Group $\)](assetId:///2062a4d9-5817-4137-ae5c-d51c7d397f08)   
 [\($ T\_324 VAT Product Posting Group $\)](assetId:///03dbc973-a1b4-4805-b4aa-ee13ba8dca13)   
 [\($ T\_325 VAT Posting Setup $\)](assetId:///5510a4f9-3ad3-461f-a53a-f3578c78a87f)   
 [\($ T\_308 No. Series $\)](assetId:///18dc626f-cdf2-4bd9-b1ab-d98927ce4c3b)