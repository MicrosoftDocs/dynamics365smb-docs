---
title: Set Up Journal Templates and Batches (IT)
description: Learn how the Italian version of Business Central helps EU companies meet the requirement to submit Intrastat reports to the customs office.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: intrastat reports, submit intrastat reports, set up journal templates, journal templates, set up journal batches, journal batches, Italian version
ms.search.form: 12119, 12132, 12140
ms.date: 05/22/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up journal templates and batches

All European Union (EU) companies must submit Intrastat reports to the customs office, detailing their trade with other EU countries/regions for the current year. An Intrastat summary report is presented to the tax authorities monthly, quarterly, or yearly depending upon the company's business.  

You can print Intrastat reports on the **Intrastat Jnl. Batches** page based on Intrastat journal entries. You can manually place entries into the journal, or use a batch job to place the entries there. Before you can do this, you must set up Intrastat journal templates and batches.  

## Steps to set up Intrastat journal templates  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal Templates**, and then choose the related link.  
1. To create a new Intrastat journal template, choose the **New** action.  
1. On the **Intrastat Journal Templates** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The name of the Intrastat journal template. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the Intrastat journal template. You can enter a maximum of 80 alphanumeric characters.|  

1. Choose the **OK** button.  

## Steps to set up Intrastat journal batches  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal Templates**, and then choose the related link.  
1. To open the **Intrastat Jnl. Batches** page, select the required template, and then choose the **Batches** action.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The name of the Intrastat journal. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the Intrastat journal. You can enter a maximum of 50 alphanumeric characters.|  
    |**Periodicity**|Select one of the following options:<br><br/>- **Month**<br/>- **Quarter**<br/>- **Year**|  
    |**Type**|Select one of the following options:<br><br/>- **Purchases**<br/>- **Sales**|  
    |**Statistics Period**|The statistics period that the report covers. Enter the value in YYMM format.|  
    |**Corrective Entry**|Select the **Corrective Entry** checkbox to correct an entry.|  
    |**File Disk No.**|The number of the file disk.<br><br/> This is used when you run the Intrastat - Make Disk Tax Auth batch job.|  
    |**Currency Identifier**|The code to identify the currency for the Intrastat report.|  
    |**Reported**|If the entry has already been reported to the tax authorities, select the **Reported** checkbox. This checkbox is selected automatically when you run the **Intrastat - Make Disk Tax Auth** batch job for this entry.|  

1. To close the page, choose the **OK** button.  

## Related information

- [Italy Local Functionality](italy-local-functionality.md)   
- [Print Intrastat Reports for Italy](how-to-print-intrastat-reports-for-italy.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
