---
title: "General Ledger Correspondence"
ms.custom: na
ms.date: "06-04-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "general ledger, correspondence"
ms.assetid: f0586fa5-4c29-4dd9-be3d-ee125dddb959
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# General Ledger Correspondence
The general ledger correspondence feature enables you to:  
  
-   Create a correspondence transaction periodically.  
  
-   Post correspondence operations when you post general ledger transactions.  
  
-   Analyze a number of reports for correspondence.  
  
## Creating a General Ledger Correspondence Entry  
 The following procedure shows how to periodically create general ledger correspondence entries.  
  
1.  In **Financial Management**, click **General Ledger**, click **Correspondence**, and then click **Create General Ledger Correspondence**.  
  
2.  Enter the **Transaction No.** field with the transaction number if general ledger correspondence is to be created only for the selected transaction. Otherwise, leave it blank.  
  
 To set up automatic general ledger correspondence  
  
-   In **Financial Management**, click **Setup**, click **General Ledger Setup**, and select the **Automatic G\/L Correspondence** field.  
  
## Reports  
 The following reports have been added for the analysis of data from correspondence transactions:  
  
-   General Ledger Correspondence General Ledger \(form ID 12403; report ID 12431\)  
  
-   General Ledger Correspondence Analysis \(form ID 12401\)  
  
-   General Ledger Correspondence Journal Order \(report ID 12432\)  
  
-   General Ledger Correspondence Cross\-Reference \(report ID 12433\)  
  
-   General Ledger Correspondence Cross\-Reference \(A\) \(report ID 12434\)  
  
-   General Ledger Correspondence Entries Analysis \(report ID 12435\)  
  
### General Ledger Correspondence General Ledger Form  
 The General Ledger Correspondence General Ledger form shows turnovers in the chosen period in correspondence.  
  
 To access the General Ledger Correspondence General Ledger form  
  
-   In **Financial Management**, click **General Ledger**, click **Correspondence**, and then click **General Ledger**.  
  
 The header contains the following filters:  
  
-   Date  
  
-   Business unit  
  
-   Global Dimension 1 Filter  
  
-   Global Dimension 2 Filter  
  
 If you select a turnover in the left subform, the report shows the turnover in correspondence with other accounts in the right subform.  
  
 To print the form  
  
-   Click **General Ledger** from **Print**. On the **G\/L Account** tab of the request form, the filter is set by default from the active line in the **G\/L Correspondence General Ledger** form.  
  
 On the **Options** tab, you can set parameters by filling in the fields with the information listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Period Beginning**|Enter the starting month and year of the period, for the entries that you want to include in the report.|  
|**Ending of period**|Enter the ending month and year of the period, for the entries that you want to include in the report.|  
|**Without Double Entries**|Select this check box to print the report without double entries.|  
|**Without Account Title Type**|Select this check box to print the report without account titles.|  
|**Without Levels of Enclosure**|Select this check box to print the report without levels of enclosure.|  
|**Interim Total**|Select this check box to print the report with interim totals.|  
  
### General Ledger Correspondence Analysis Report  
 The General Ledger Correspondence Analysis report shows turnover in the selected period in correspondence.  
  
 To access the report  
  
-   In **Financial Management**, click **General Ledger**, click **Correspondence**, and then click **General Ledger Correspondence**.  
  
 The header contains the following filters:  
  
-   Date  
  
-   Closing  
  
-   Department  
  
-   Project  
  
 The report shows turnover in correspondence for all accounts.  
  
### General Ledger Correspondence Journal Order Report  
 This report shows the debit and credit turnovers and balance on each general ledger account.  
  
 To access the report  
  
-   In **Financial Management**, click **General Ledger**, click **Reports**, click **Correspondence**, and then click **Journal Order**.  
  
 You can set a general ledger account filter on the **G\/L Account** tab of the request form. The **Options** tab contains the same fields as the General Ledger Correspondence General Ledger report.  
  
### General Ledger Correspondence Cross\-Reference Report  
 The General Ledger Correspondence Cross\-Reference report shows all correspondence amounts.  
  
 To access the report  
  
-   In **Financial Management**, click **General Ledger**, Click **Reports**, click **Correspondence**, and then click **Cross Reference**.  
  
 On the **Options** tab of the request form, you can set parameters by filling in the fields with the information listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Starting Date**|Enter the starting date of the period, for the entries that you want to include in the report.|  
|**Ending Date**|Enter the ending date of the period, for the entries that you want to include in the report.|  
  
### General Ledger Correspondence Reference \(A\) Report  
 The General Ledger Correspondence Reference report shows all correspondence amounts.  
  
 To access the report  
  
-   In **Financial Management**, click **General Ledger**, click **Reports**, click **Correspondence**, and then click **Cross Reference \(A\).** The **Options** tab of the request form contains the same fields as the General Ledger Cross\-Reference report.  
  
### General Ledger Correspondence Entries Analysis Report  
 The General Ledger Correspondence Entries Analysis report shows the correspondence entries for each account. The report can be used to get an overview of general ledger account entries with correspondence and totals.  
  
 To access the report  
  
-   In **Financial Management**, click **General Ledger**, click **Reports**, click **Correspondence**, and then click **Entries Analysis**.  
  
 On the **Options** tab of the request form, you can set parameters by filling in the fields with the information listed in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Starting Date**|Enter the starting date of the period, for the entries that you want to include in the report.|  
|**Ending Date**|Enter the ending date of the period, for the entries that you want to include in the report.|  
|**Other parameters**<br /><br /> **Without Zero Net Changes**<br /><br /> **Without Zero Lines**<br /><br /> **Debit Credit Separately**<br /><br /> **New Page for GL Acc**|Specify the view of the report, such as whether the information for each account should be written without zero lines or net changes.|