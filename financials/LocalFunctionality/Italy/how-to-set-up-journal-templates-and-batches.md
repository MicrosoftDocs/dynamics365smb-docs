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
# How to: Set Up Journal Templates and Batches
All European Union \(EU\) companies must submit Intrastat reports to the customs office, detailing their trade with other EU countries\/regions for the current year. An Intrastat summary report is presented to the tax authorities monthly, quarterly, or yearly depending upon the company's business.  
  
 You can print Intrastat reports in the **Intrastat Jnl. Batches** window based on Intrastat journal entries. You can manually place entries into the journal, or use a batch job to place the entries there. Before you can do this, you must set up Intrastat journal templates and batches.  
  
### To set up Intrastat journal templates  
  
1.  In the **Search** box, enter **Intrastat Journal Templates**, and then choose the related link.  
  
2.  To create a new Intrastat journal template, on the **Home** tab, choose **New**.  
  
3.  In the **Intrastat Journal Templates** window, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The name of the Intrastat journal template. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the Intrastat journal template. You can enter a maximum of 80 alphanumeric characters.|  
  
4.  Choose the **OK** button.  
  
### To set up Intrastat journal batches  
  
1.  In the **Search** box, enter **Intrastat Journal Templates**, and then choose the related link.  
  
2.  To open the **Intrastat Jnl. Batches** window, select the required template, and then, on the **Navigate** tab, in the **Templates** group, choose **Batches**.  
  
3.  Fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The name of the Intrastat journal. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the Intrastat journal. You can enter a maximum of 50 alphanumeric characters.|  
    |**Periodicity**|Select one of the following options:<br /><br /> -   **Month**<br />-   **Quarter**<br />-   **Year**|  
    |**Type**|Select one of the following options:<br /><br /> -   **Purchases**<br />-   **Sales**|  
    |**Statistics Period**|The statistics period that the report will cover. Enter the value in YYMM format.|  
    |**Corrective Entry**|Select the **Corrective Entry** check box to correct an entry.|  
    |**File Disk No.**|The number of the file disk.<br /><br /> This is used when you run the Intrastat - Make Disk Tax Auth batch job.|  
    |**Currency Identifier**|The code to identify the currency for the Intrastat report.|  
    |**Reported**|If the entry has already been reported to the tax authorities, select the **Reported** check box. This check box is selected automatically when you run the **Intrastat - Make Disk Tax Auth** batch job for this entry.|  
  
4.  To close the window, choose the **OK** button.  
  
 For more information, see [How to: Print Intrastat Reports for Italy](how-to-print-intrastat-reports-for-italy.md).  
  
## See Also  
 [How to: Set Up Intrastat Journal Templates and Batches](how-to-set-up-intrastat-journal-templates-and-batches.md)   
 [Italy Local Functionality](italy-local-functionality.md)   
 [How to: Print Intrastat Reports for Italy](how-to-print-intrastat-reports-for-italy.md)