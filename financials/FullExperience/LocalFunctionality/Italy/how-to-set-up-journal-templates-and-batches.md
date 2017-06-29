---
title: "How to: Set Up Journal Templates and Batches"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "journal batches, setting up for Intrastat"
  - "journal templates, setting up for Intrastat"
  - "Intrastat, setting up journals"
ms.assetid: de2a9634-3fd7-4c78-9327-a84a001d34dc
caps.latest.revision: 18
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Set Up Journal Templates and Batches
All European Union \(EU\) companies must submit Intrastat reports to the customs office, detailing their trade with other EU countries\/regions for the current year. An Intrastat summary report is presented to the tax authorities monthly, quarterly, or yearly depending upon the company's business.  
  
 You can print Intrastat reports in the **Intrastat Jnl. Batches** window based on Intrastat journal entries. You can manually place entries into the journal, or use a batch job to place the entries there. Before you can do this, you must set up Intrastat journal templates and batches.  
  
### To set up Intrastat journal templates  
  
1.  In the **Search** box, enter **Intrastat Journal Templates**, and then choose the related link.  
  
2.  To create a new Intrastat journal template, on the **Home** tab, choose **New**.  
  
3.  In the **Intrastat Journal Templates** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The name of the Intrastat journal template. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the Intrastat journal template. You can enter a maximum of 80 alphanumeric characters.|  
  
4.  Choose the **OK** button.  
  
### To set up Intrastat journal batches  
  
1.  In the **Search** box, enter **Intrastat Journal Templates**, and then choose the related link.  
  
2.  To open the **Intrastat Jnl. Batches** window, select the required template, and then, on the **Navigate** tab, in the **Templates** group, choose **Batches**.  
  
3.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The name of the Intrastat journal. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the Intrastat journal. You can enter a maximum of 50 alphanumeric characters.|  
    |**Periodicity**|Select one of the following options:<br /><br /> -   **Month**<br />-   **Quarter**<br />-   **Year**|  
    |**Type**|Select one of the following options:<br /><br /> -   **Purchases**<br />-   **Sales**|  
    |**Statistics Period**|The statistics period that the report will cover. Enter the value in YYMM format.|  
    |**Corrective Entry**|Select the **Corrective Entry** check box to correct an entry.|  
    |**File Disk No.**|The number of the file disk.<br /><br /> This is used when you run the Intrastat \- Make Disk Tax Auth batch job.|  
    |**Currency Identifier**|The code to identify the currency for the Intrastat report.|  
    |**Reported**|If the entry has already been reported to the tax authorities, select the **Reported** check box. This check box is selected automatically when you run the **Intrastat \- Make Disk Tax Auth** batch job for this entry.|  
  
4.  To close the window, choose the **OK** button.  
  
 For more information, see [How to: Print Intrastat Reports for Italy](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-print-intrastat-reports-for-italy.md).  
  
## See Also  
 [How to: Set Up Intrastat Journal Templates and Batches](../../Finance/how-to-set-up-intrastat-journal-templates-and-batches.md)   
 [Italy Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/italy-local-functionality.md)   
 [How to: Print Intrastat Reports for Italy](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-print-intrastat-reports-for-italy.md)