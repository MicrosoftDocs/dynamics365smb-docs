---
    title: How to Set Up Tax Register Sections | Microsoft Docs
    description: You can either create a new tax register section or select a tax register section to be used in a company during the current taxation period. You can select a tax register section that was valid during previous taxation periods and view tax information for any of the periods. You can copy tax registers from one tax register section into another. You can also set up tax registers and adjust the algorithm of information collection into tax registers.
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
# How to: Set Up Tax Register Sections
You can either create a new tax register section or select a tax register section to be used in a company during the current taxation period. You can select a tax register section that was valid during previous taxation periods and view tax information for any of the periods. You can copy tax registers from one tax register section into another. You can also set up tax registers and adjust the algorithm of information collection into tax registers.  
  
 The following procedure shows how to set up tax register sections.  
  
### To set up a tax register  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Registers**, and choose the related link.  
  
2.  In the **Tax Registers Sections** window, choose **New**.  
  
3.  On the **General** FastTab, enter the fields described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**Code**|The code of the existing tax register version for a certain taxation period is displayed.<br /><br /> Create the code for a new tax register section, if necessary.|  
    |**Description**|Enter a description for the tax register section.|  
    |**Status**|This field can have any one of the following values:<br /><br /> -   **Blocked**<br />-   **Open**<br />-   **Reporting**<br />-   **Closed**<br /><br /> The **Blocked** status is set by default when you create a new section. This shows that a new tax register section is created and that the register does not contain any data.<br /><br /> Change the status to **Open manually** to continue further set up. Using this status, during tax register calculation and recalculation, you cannot check the availability of data for the previous and following taxation periods. The continuity of creating tax registers in the current period is not controlled. This status target allows you to enable debugging of the tax register calculation accuracy.<br /><br /> If the Status has the value **Reporting**, the continuity of tax data creation is controlled. This is the production working mode with the Tax Accounting module. In this status, only the end date must be changed.<br /><br /> The status value **Closed** indicates a closed taxation period. It can be set after all tax registers for the taxation period are built.|  
    |**Starting Date**|Enter the start date of the tax register section.|  
    |**Ending Date**|Enter the end date of the tax register section.|  
  
4.  On the **Dimensions** FastTab, enter the dimension codes to filter the information selected for tax registers. Dimension codes can be changed only when the **Status** field of the tax register version has the value **Open**.  
  
5.  On the **Balance** FastTab, enter the deadlines for debtor and creditor liabilities applied in accordance with the current taxation period. For example, Debit Balance Point 1 = - 45D, Debit Balance Point 2 = - 90D.  
  
6.  On the **System** FastTab, select the actual norm code for the current tax register version in the **Norm Jurisdiction Code** field. Select the form number **17209** in the **Form ID** field.  
  
     Choose the **OK** button.  
  
7.  In the **Tax Registers** window, on the **Home** tab, in the **Process** group, choose **Registers**.  
  
8.  In the **Tax Register Names**window, you can add new registers to the list. To create a new tax register, do one of the following:  
  
    1.  Place the cursor in an empty line at the end of the register list and enter the information on the new register.  
  
    2.  Place the cursor on the register you want to create the new one after. Then press F3 and enter the information on the new register.  
  
9. Enter the fields described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**No.**|Enter the number of the tax register.|  
    |**Description**|Enter the name of the tax register.|  
    |**Storing Method**|Select the tax register type.<br /><br /> You can choose one of the following options:<br /><br /> -   Calculation (accumulating)<br />-   Build entry (creation on the basis of posted ledgers entries)|  
    |**Table ID**|Select 17208 for the tax register with storing method calculation.<br /><br /> For the tax register with storing method build entry depending on the source entry of the register, select one of following: **17209**, **17210**, **17211**, **17212**, **17213**, **17214**.|  
  
 Mapping of the source entries of the register and Table IDs are listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|**17209**|For registers created based on general ledger entries|  
|**17210**|For registers created based on customer and vendor entries|  
|**17211**|For registers created based on fixed assets and immaterial assets entries|  
|**17212**|For register created based on item entries|  
|**17213**|For registers created based on expenses of future periods|  
|**17214**|For registers created based on the payroll entry ledger|  
  
 If a new version of the tax register is created, the window with the register list will be empty. In this window, you can manually enter all the tax registers to be used, or you can select **Copy Section** by clicking **Functions** in the Tax Register Section card and copy the register list with its settings from any of the existing tax register sections.  
  
 In the Copy Tax Register Section window, enter the section from which you want to copy the register.  
  
 The following procedure shows how to remove a tax register from the register list.  
  
### To remove a tax register from the register list.  
  
1.  Choose **Registers**, and then choose **Edit** to select the **Register card**.  
  
2.  Choose the **OK** button.  
  
3.  Choose **Delete** to remove the register from the register list.  
  
## See Also  
 [Tax Accounting](tax-accounting.md)   
 [Tax Registers](tax-registers.md)   
 [How to: Create Tax Registers](how-to-create-tax-registers.md)   
 [Collecting Profit Tax Information for Tax Declaration](collecting-profit-tax-information-for-tax-declaration.md)