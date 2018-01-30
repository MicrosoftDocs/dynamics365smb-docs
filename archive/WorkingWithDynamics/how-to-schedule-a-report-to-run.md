---
    title: How to Schedule a Report to Run | Microsoft Docs
    description: You can schedule a report to run at a specific date and time. Scheduled reports are entered in the job queue and processed at the scheduled time, similar to other jobs. You can choose to save the processed report to a file, such as an Excel, Word, or PDF, print it to a selected printer, or process the report only. If you choose to save the report to a file, then the processed report is sent to the **Report Inbox**, where you can view it.
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
# Schedule a Report to Run
You can schedule a report to run at a specific date and time. Scheduled reports are entered in the job queue and processed at the scheduled time, similar to other jobs. You can choose to save the processed report to a file, such as an Excel, Word, or PDF, print it to a selected printer, or process the report only. If you choose to save the report to a file, then the processed report is sent to the **Report Inbox**, where you can view it.  
  
 You can schedule a report from the job queue on your Role Center or on the request page when you open a report.  
  
### To schedule a report to run  
  
1.  Do one of the following:  
  
    -   To schedule a report from the report request page, open the report, and then in the **Print** menu of the report's request page, choose **Schedule**.  
  
    -   To schedule a report from the job queue, in the **My Job Queue** part on the Role Center page, choose **Schedule a Report**.  
  
2.  In the **Schedule a Report** window, set the **Report ID** field to ID of the report that you want to schedule to run. Use the drop-down list to find the report.  
  
     This field is automatically filled in when you schedule a report from the report request page.  
  
     After you set the **Report ID** field, the **Report Name** field is automatically filled in with the name of the report. You cannot manually change this field.  
  
3.  Fill in the remaining fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Report Request Page Options**|Specifies the options, such as filters, which narrow the data that is included in the processed report.<br /><br /> To set the options, select the check box, and then fill in the options on the request page that opens for the report.<br /><br /> After you set the options, the checkbox is selected.|  
    |**Report Output Type**|Specifies the output of the processed report. You can select from the following options.<br /><br /> -   **PDF** saves the report as a PDF file.<br />-   **Word** saves the report as a Word (.docx) file.<br />-   **Excel** saves the report as an Excel (.xlsx) file.<br />-   **Print** sends the report to a specified printer for printing.<br />-   **None** does not generate an output and is used for process-only reports.|  
    |**Printer Name**|Specifies the printer to use to print the processed report when you set the **Report Output Type** field to **Print**.<br /><br /> You can select from the printers that are set up on your computer.|  
    |**Earliest Date/Time**|Specifies the date and time on which you want to run the report.<br /><br /> If there are no other jobs in the job queue at the scheduled time, then the report will be processed. Otherwise, it will be processed when the job queue is available.|  
    |**Expiration Date/Time**|Specifies the last date and time on which the report runs. The report will not run after this time.|  
  
 The report is added to the job queue and will be run at the specified time. When the report is processed, the item will be removed from the job queue. If you saved the processed report to a file, it will be available in the **Report Inbox** on your Role Center.  
  
## See Also  
 [View and Print Reports](../FullExperience/how-to-view-and-print-reports.md)   
 Report Inbox Part