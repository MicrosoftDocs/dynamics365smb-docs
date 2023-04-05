---
    title: Audit files export
    description: This article explains how to set up different export formats and then use them based on auditors or authorities requirments.
    author: altotovi
    ms.service: dynamics365-business-central
    ms.topic: how-to
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: audit, export, SIE, SAF-T, FAC, GDPdU, file export
    ms.search.form: 5260, 5261, 5264, 5266, 5267, 5270
    ms.date: 04/04/2023
    ms.author: altotovi
    ms.reviewer:

---

# Audit files export

Exporting bookkeeping information from the system is a common request by some local authorities or auditors. Exporting formats and required information can be different. Entries for exporting are usually **General Ledger Entries** or **VAT Entries**, however other information is sometimes required.  

**Audit Files Export** is a preinstalled extension that enables you to export different entries based on auditor or authority requirements. Regardless of the format type or entries, you can use this functionality to control the data export process. This functionality doesn’t have a preinstalled file format for exporting so you must install an app with a specific format, such as SIE, SAF-T, or FAC, or develop your own.  

> [!NOTE]
> Currently, you can choose SIE or SAF-T formats as an additional app. Partners can also develop a custom format. The number of formats available will increase over time. 

## Set up the Audit file export

1. Select the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Setup**, and then select the related link. 
    1. On the **Audit File Export Setup** page, on the **General** FastTab, in the **Audit File Export Format Code**, specify the default audit file export format code. Only formats that were previously enabled while installing a specific file format from Feature management or those that were added as a custom format are available. 
    2. On the **Data Quality** FastTab, select the **Check Company Information** check box to be notified about company information fields that haven't been set up correctly. 
    3. Select the **Check Customer** check box to be notified about fields that haven't been set up correctly for specific customers. 
    4. Select the **Check Vendor** check box to be notified about fields that haven't been set up correctly for specific vendors. 
    5. Select the **Check Bank Account** check box to be notified about fields that haven't been set up correctly for specific bank accounts. 
    6. Select the **Check ZIP Code** check box to be notified about a ZIP Code that hasn't been set up correctly. 
    7. Select the **Check Address** check box to be notified when an address hasn't been set up correctly. 
    8. In the **Default ZIP Code** field, enter a ZIP Code to use when no ZIP Code is specified in the customer or vendor card. 
2.	Select the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Format Setup**, and then select the related link. 
    1. On the **Audit File Export Format Setup** page, select the Audit file export format you want to configure. Only formats that were previously enabled by installing a specific file format from Feature management or those added as a custom format are available to use.  
    2. In the **Audit File Name** field, specify the default file name or the file name template for the audit file you want to export.  
    3. Select the **Archive to Zip** check box to automatically zip exported files. 

## General ledger account mapping for Audit file export

Because most formats required by authorities for General ledger accounts require a specific standard chart of accounts, after you configure your General ledger accounts, your exported file will be based on the mappings. You can use more mappings in your system.  

Complete the following steps to provide General ledger account mapping for Audit file export. 

1. Select the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Account mapping**, and then select the related link. 
2.	On the **G/L Mapping** page select **New** to create a new mapping.  
3.	In the **Code** field, specify the mapping code that represents the reporting period. 
4.	In the **Standard Account Type** field, select the type of standard general ledger accounts. 
5.	In the **Audit File Export Format** field, specify the audit file export format to which the standard general ledger accounts are linked.  
6.	In the **Period Type** field, the system specifies accounting period or custom period type with a flexible start date and time, based on your choice. If you select a specific accounting period, it will be populated as **Accounting Period**, otherwise it will be shown as **Data Range**. 
7.	In the **Accounting Period** field, specify the start date of the accounting period that will be used as the reporting period, if you want them to be the same.  
8.	If you use the **Accounting Period** field, the **Starting Date** and **Ending Date** are automtically populated based on your choice. If you don’t use the **Accounting Period**, you can manually set up the starting and ending dates for your reporting. 
9. If you already have added a standard chart of account, set up the following fields:   
    1. In the **Standard Account Category No.** field, specify the category of the standard account or grouping code used for mapping. 
    2. In the **Standard Account No.** field, specify the standard account code or grouping code used for mapping.  
10.	Select the **Include Incoming Balance** check box to consider the incoming balance of the **G/L Account** of type **Balance Account** for mapping instead of the reporting period's net change. 
11.	To start the mapping, the General ledger account must have .   
    1. To create lines, select **Initialize Source for Mapping** to generate lines on the **G/L Account Mapping** page based on an existing chart of accounts or the **Copy from Another Mapping** action to copy the G/L account mapping from some another mapping code.  
    2.	After creating lines, you can see all **G/L Accounts** with posted entries marked in green.  
    3.	If you want to mark only **G/L Accounts** with entries, you can do it executing the **Update G/L Entry Availability** action. If option **Include Incoming Balance** is enabled, then all posted **G/L Entries** are considered for calculation. Otherwise only **G/L Entries** of the reporting period are considered.  

## To export the audit file

1.	Select the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Documents**, and the select the related link.  
2.	On the **Audit File Export Documents** page, select **New**.  
3.	On the **General** FastTab, enter the following field information.   
    1. In the **Audit File Export Format** field, select the format used to export the audit file. 
    2. In the **G/L Account Mapping Code** field, select the G/L account mapping code for the reporting period. 
    3. Select the **Split By Month** check box if multiple audit files must be generated per month.  
    4. Select the **Split By Date** check box if multiple audit files will be generated for each day. 
    5. In the **Header Comment** field, enter the comment to be included on the audit file header.  
    6. In the **Contact** field, specify the contact that's exported to the header of the audit file. 
    7. Select the **Create Multiple Zip Files** check box to generate multiple Zip files.  

  > [!NOTE] 
  > Use this option only if you previously installed some of the format apps or created a custom one. Installing one or more of the specific formats will likely add additional fields and functions to the Audit File Export functionality, based on the format requirements.   

4.	On the **Processing** FastTab, select the method you want to use for exporting data.
    1.	Select the **Parllel Processing** check box if you want teh audit file generation to be processed by parallel backgroung jobs. If you want to export data in your current session, clear the check box. 
    2.	If you select the **Parallel Processing** field, enter a value in the **Max No. Of Jobs** field to specify the maximum number of background jobs that can be run at the same time. 
    3.	Enter a value in the **Earliest Start Date/Time** field to specify the earliest date and time when the background job must be run. When you run the process using the **Start** action, you can track the status in the **Processing** and **Lines** FastTabs.   
5.	After you have finished job, select **Download as File** to download audit file for the selected line.  

> [!IMPORTANT]  
> If you have multiple entries for exporting, we don't recommend exporting in the current session, because of the potential performance issues. In this situation, we recommend using **Parallel Processing** during non-working days/hours.  

## See Also

[Financial Management](finance.md)  
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)
[Work with Dimensions](finance-dimensions.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
