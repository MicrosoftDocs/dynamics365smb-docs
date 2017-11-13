---
    title: How to Create Statutory Report Data
    description: After you have defined the statutory reports that are required by the tax authorities, you can create the report data and generate files that you can submit to the authorities.

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
# How to: Create Statutory Report Data
After you have defined the statutory reports that are required by the tax authorities, you can create the report data and generate files that you can submit to the authorities.  

## To create report data  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Statutory Reports**, and then choose the related link.  
2.  Select the statutory report that you want to create data for, and then choose the **Create Report Data** action.  
3.  In the **Create Report Data** window, fill in the fields.  

    The **Creation Date** field is automatically set to the work date, but you can change this.  

    The **Periodicity** field is set depending on the value of the **Report Type** field for the report.  

4.  Choose the **OK** button.  

This generates data for the report. Now, you can verify the data before you submit the statutory report.  

## To verify report data  

1.  In the **Statutory Reports** window, select the statutory report that you want to create data for, and then choose the **Report Data** action.  

    The **Report Data List** window contains a line for each set of report data that you have created for this statutory report.  

2.  In the **Report Data List** window, select the set of report data that you want to verify, and then choose the **Overview** action.  
3.  In the **Statutory Report Data Overview** window, set the appropriate filters, and then choose the **Show Data** action.  

    This opens a window that displays the data based on your filters. You can verify the report data before you generate the files for the statutory report. If you want to make changes, you must create the report data again.  

4.  After you have verified that the report data is correct, choose the **OK** button.  

    You can repeat these steps for all combinations of filters.  

Now, you can submit the report by generating a file that is based on the setup for the statutory report.  

## Generating Statutory Reports  
Before you generate a statutory report, you should verify that the data is correct in the **Report Data List** window. Also, you should make sure that the statutory report is set up correctly in the **Statutory Reports** window. Before you do this, you must release the report data.  

### To release the report data for a statutory report  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Statutory Reports**, and then choose the related link.  
2.  Select the statutory report that you want to generate, and then choose the **Report Data** action.  
3.  Select the report data, and then choose the **Release** action.  

Now, you can generate the statutory report.  

### To generate a statutory report  

1.  In the **Statutory Reports** window, select the statutory report that you want to generate, and then choose the **Report Data** action.  

    Depending on the statutory report, you must export to Microsoft Excel or generate an XML file.  

2.  To export to Microsoft Excel, select the report data, and then choose the **Export to Excel** action.  

    This creates a Microsoft Excel workbook that has the data that you created for this statutory report.  

3.  To export to an XML file, select the report data, and then choose the **Export Electronic File** action.  

    This creates an XML file that has the data that you created for this statutory report.  

Now, you can submit the report. For more information, see [Statutory Reporting Directives](http://go.microsoft.com/fwlink/?LinkId=216142) on the Federal Tax Services website.  
  
## See Also  
 [Statutory Reports](statutory-reports.md)   
 [How to: Set Up Statutory Reports](how-to-set-up-statutory-reports.md)
