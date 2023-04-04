---
    title: Audit Files Export
    description: Using this functionallity you can set up and different export formats and export the based on auditors or authorities requirments.
    author: altotovi
    ms.service: dynamics365-business-central
    ms.topic: how-to
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: audit, export, SIE, SAF-T, FAC, GDPdU, file export
    ms.search.form: 5260, 5261, 5264, 5266, 5267, 5270
    ms.date: 04/04/2023
    ms.author: altotovi
    ms.reviewer:

---
# Audit Files Export

Exporting some bookkeeping information from the system is a common request by some local authorities or auditors. Exporting formats and required information can be different. Entries for exporting are mostly **General Ledger Entries** or **VAT Entries**, but also some other information in the system if this is required.  

**Audit Files Export** is preinstalled extension, and it enables users to export different entries from Business Central based on auditor or authority requirements. Regardless of the format type or entries, you can use this functionality to control data export process. But this functionality doesn’t have preinstalled file format for exporting and you need to install app with specific format (SIE, SAF-T, FAC…) or to develop your own custom format.  

> [!NOTE]
> Currently users can choose SIE or SAF-T formats as an additional app, but partners also can develop custom format. The number of formats will increase in the next period. 

## To set up the Audit File Export

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Setup**, and the choose the related link. 
    1.  On the **Audit File Export Setup** page choose **Audit File Export Format Code** on the **General** FastTab to specify the default audit file export format code. Keep in mind you can see only formats previously enabled installing specific file format from the Feature management or adding them as a custom format. 
    2.	Select the **Check Company Information** field on the **Data Quality** FastTab to specify if you want to be notified about fields that have not been set up correctly in the **Company Information**. 
    3.	Select the **Check Customer** field on the **Data Quality** FastTab to specify if you want to be notified about fields that have not been set up correctly for specific customers. 
    4.	Select the **Check Vendor** field on the **Data Quality** FastTab to specify if you want to be notified about fields that have not been set up correctly for specific vendors. 
    5.	Select the **Check Bank Account** field on the **Data Quality** FastTab to specify if you want to be notified about fields that have not been set up correctly for specific bank accounts. 
    6.	Select the **Check ZIP Code** field on the **Data Quality** FastTab to specify if you want to be notified about the **ZIP Code** that has not been set up correctly. 
    7.	Select the **Check Address** field on the **Data Quality** FastTab to specify if you want to be notified about the address that has not been set up correctly. 
    8.	Populate the **Default ZIP Code** field on the **Data Quality** FastTab to specify the **ZIP Code** to use when no values specified in the customer or vendor card. 
2.	Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Format Setup**, and the choose the related link. 
    1.	On the **Audit File Export Format Setup** page choose **Audit File Export Format** you want to configure for usage. Keep in mind you can see and use only formats previously enabled installing specific file format from the Feature management or adding them as a custom format.  
    2.	In the **Audit File Name** field specify the default file name or the file name template for the audit file you want to export.  
    3.	Select the **Archive to Zip** field if you want to have exported file zipped by default. 

## GL Account mapping for Audit File Export

As most of formats required by authorities for **G/L Accounts** require specific standard chart of accounts you can configure it and your exported file will be based on these mapped accounts. You can use more different mappings in your system.  

To provide **G/L Account** mapping for **Audit File Export**: 

1.	Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Account mapping**, and the choose the related link. 
2.	On the **G/L Mapping** page select **New** action to create new mapping.  
3.	In the **Code** field specify the mapping code that represents the reporting period. 
4.	In the **Standard Account Type** field select the type of standard general ledger accounts. 
5.	In the **Audit File Export Format** field specify the audit file export format to which the standard general ledger accounts are linked.  
6.	In the **Period Type** field system will specify the type for an accounting period or custom period with a flexible start date/time, based on your choice. If you choose a specific accounting period, it will be populated as **Accounting Period**, otherwise it will be showed as **Data Range**. 
7.	In the **Accounting Period** field, you can specify the starting date of the accounting period that will be used as reporting period, if you want to use accounting period as reporting period.  
8.	If you use the **Accounting Period**, field **Starting Date** and **Ending Date** will be auto populated based on your choice, but if you don’t use the **Accounting Period** you can manually set up starting and ending dates for your reporting. 
9.	If you already have added a standard chart of account, you can set up the following fields:   
    1.	In the **Standard Account Category No.** field specify the category of the standard account or grouping code that is used for mapping. 
    2.	In the **Standard Account No.** field specify the code of the standard account or grouping code that is used for mapping.  
10.	Select the **Include Incoming Balance** field to specify if the incoming balance of **G/L Account** of type **Balance Account** needs to be considered for mapping instead of the reporting period's net change. 
11.	To start with mapping, you first need to have G/L Account in lines.   
    1.	To create lines, you can run the **Initialize Source for Mapping** action to generate lines on the **G/L Account Mapping** page based on an existing chart of accounts or the **Copy from Another Mapping** action to copy the G/L account mapping from some another mapping code.  
    2.	After creating lines, you can see all **G/L Accounts** with posted entries marked in green.  
    3.	If you want to mark only **G/L Accounts** with entries, you can do it executing the **Update G/L Entry Availability** action. If option **Include Incoming Balance** is enabled, then all posted **G/L Entries** are considered for calculation. Otherwise only **G/L Entries** of the reporting period are considered.  

## To export the audit file

1.	Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Documents**, and the choose the related link.  
2.	On the **Audit File Export Documents** page select New action to prepare new export.  
3.	Populate the following fields on the **General** FastTab:   
    1.	In the **Audit File Export Format** field select the format which is used for exporting the audit file. 
    2.	In the **G/L Account Mapping Code** field select the G/L account mapping code that represents the reporting period. 
    3.	Select the **Split By Month** field if multiple audit files need to be generated per month.  
    4.	Select the **Split By Date** field whether multiple audit files will be generated for each day. 
    5.	Specifies the comment in the **Header Comment** field that is exported to the header of the audit file.  
    6.	In the **Contact** field specify the contact that is exported to the header of the audit file. 
    7.	Select the **Create Multiple Zip Files** field if you need multiple Zip files to be generated.  

  > [!NOTE] 
  > You can use this option only if you previously installed some of the format apps or created custom one. Installing some of the specific formats will probably add additional fields and functions to the Audit File Export functionality, based on this format requirements.   

4.	On the **Processing** FastTab you can choose the method you want to use for exporting data:  
    1.	If you want to export data in your current session do not select the **Parallel Processing** field, but if you want audit file generation to be processed by parallel background jobs, select it. 
    2.	If you select the **Parallel Processing** field, you can configure the **Max No. Of Jobs** field to specify the maximum number of background jobs that can be run at the same time and the **Earliest Start Date/Time** field to specify the earliest date and time when the background job must be run.  
    3.	When you run the process using the **Start** action, you can track the status in the **Processing** and **Lines** FastTabs.   
5.	Once when you have finished job, you can execute the **Download as File** action to download audit file for the selected line.  

> [!IMPORTANT]  
> If you have a lot of entries for exporting, we do not recommend exporting in the current session, because of the potential performance issues. In this situation we highly recommend using **Parallel Processing** during not working days/hours.  

## See Also

[Financial Management](finance.md)  
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)
[Work with Dimensions](finance-dimensions.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
