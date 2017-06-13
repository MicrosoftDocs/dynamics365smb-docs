---
title: "How to: Set Up Analysis Column Templates"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "templates, analysis reports"
  - "analysis, column templates"
ms.assetid: e0ec4570-9e0a-47fc-89ea-ab3aafdde707
caps.latest.revision: 7
ms.author: "sgroespe"
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
# How to: Set Up Analysis Column Templates
In an analysis report your analysis parameters are shown as columns. You can define the columns that you want to include in your analysis report by setting up analysis column templates.  
  
 A template contains a set of lines each representing the analysis columns that you see in the analysis report. To define a column you must assign an analysis type code to a line. This analysis type code determines the type of source data in the item ledger entries that the analysis will be based on. Source data includes cost, sales amount, or quantity, and their associated value entries. You can set up as many column templates as you like, and then use them to create new analysis reports.  
  
### To set up analysis column templates  
  
1.  In the **Search** box, enter **Analysis Column Templates**, and then choose the related link.  
  
2.  Select the first empty line, and in the **Name** field, enter the name you want to give your new analysis column template. In the **Description** field, enter a description.  
  
3.  On the **Home** tab, in the **Process** group, choose **Columns**.  
  
4.  In the **Analysis Columns** window, fill in the fields to specify the columns that you want to include in your analysis report.  
  
    > [!NOTE]  
    >  To define a column, you must fill in the **Analysis Type Codes** field for all column types except **Formula**. Set up the analysis type codes in the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[Analysis Types](DynamicsNAV:////runpage?Page=7110)** window.  
  
    > [!NOTE]  
    >  In the **Ledger Entry Type** field, if you select **Item Entries**, the actual figures from the item ledger entry are copied. If you select **Item Budget Entries**, the budgeted figures from the budget are copied.  
  
5.  Choose the **OK** button to save your changed, or press the Esc key to close the windows.  
  
## See Also  
 [How to: Set Up Analysis Line Templates](../BusinessIntelligence/how-to-set-up-analysis-line-templates.md)   
 [How to: Create New Inventory Analysis Reports](../BusinessIntelligence/how-to-create-new-inventory-analysis-reports.md)   
 [How to: Set Up Analysis Types](../BusinessIntelligence/how-to-set-up-analysis-types.md)