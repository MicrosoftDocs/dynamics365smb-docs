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
# How to: Test Databases Before Consolidating
After you have set up the consolidated company and the business units and exported the necessary data, you are ready to do the consolidation. This means you can transfer the figures from the business units to the consolidated company.  

 Before you do this, it is a good idea to check whether there are differences between the basic information in the business units and in the consolidated company. There are two reports that you can use to test the database and file.  

 For more information, see [How to: Export Business Unit Information](../how-to-test-files-before-consolidating.md).  

### To test databases before consolidating  

1.  Open the consolidated company.  

2.  In the **Search** box, enter **Business Units**, and then choose the related link.  

3.  In the **Business Units**, on the **Actions** tab, in the **Functions** group, choose **Test Database**.  

4.  On the **Business Unit** FastTab, you can set a filter to select the business units to be tested. If you do not set a filter, all business units that are selected in **Consolidate** field will be tested.  

5.  On the **Options** FastTab, fill in the appropriate fields. ADD INCLUDE<!--[!INCLUDE[bp_fieldhelp]()]--> Choose the **Copy Dimensions** field and select the dimension codes.  

6.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

 "[!INCLUDE[d365fin](../../includes/d365fin_md.md)] prints a message.  

 If the report contains errors, you must correct them before you run the consolidation.  

## See Also  
 [How to: Process Consolidations](../how-to-process-consolidations.md)   
 [How to: Enter Basic Information for Consolidated Companies](../how-to-enter-basic-information-for-consolidated-companies.md)   
 [How to: Enter Consolidation Information on General Ledger Accounts](../how-to-enter-consolidation-information-on-general-ledger-accounts.md)   
 [How to: Export Business Unit Information](../how-to-export-business-unit-information.md)   
 [How to: Consolidate from Databases](../how-to-consolidate-from-databases.md)   
 [How to: Consolidate from Files](../how-to-consolidate-from-files.md)   
 Dimension   
 [How to: Select a Company](../company-how-to-select-a-company.md)
