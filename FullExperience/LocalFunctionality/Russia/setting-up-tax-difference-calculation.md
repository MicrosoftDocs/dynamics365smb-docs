---
title: "Setting up Tax Difference Calculation"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tax differences, posting"
  - "tax differences, registers"
  - "tax differences, calculating"
ms.assetid: 9353ed68-4dd9-4349-887d-8107c80a3b51
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Setting up Tax Difference Calculation
Tax difference calculations must be set up if there is a tax difference for the presentation of fixed asset entries, item cost entries, or finance transactions in bookkeeping and tax accounting for which expenses to write off must be fixed. To set tax difference, click **Setup** and then click **Tax Differences**.  
  
## Setting Up Posting Groups  
 In the menu sub\-item **Posting Groups**, you must determine finance accounts from the set up chart of accounts, where finance transactions with tax differences are accounted for.  
  
 In the Tax Difference Posting Groups form, enter the fields described in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**Code**|The unique code of the posting group that will be used for accounting tax difference transactions.|  
|**Description**|The name of the posting group, which displays the purpose.|  
|**CTA Tax Account**|Select an account which is debited for the constant tax arising \(CTA\) amount.|  
|**CTL Tax Account**|Select an account which is debited for the constant tax liability \(CTL\) amount.|  
|**DTA Tax Account**|Select an account which is debited for the deferred tax asset \(DTA\) amount.|  
|**DTL Tax Account**|Select an account which is debited for the deferred tax liability \(DTL\) amount.|  
|**CTA Account**|The account to post the amount at the CTA arising.|  
|**CTL Account**|The account to post the amount at the CTL arising.|  
|**DTA Account**|The account to post the amount at the DTA arising.|  
|**DTL Account**|The account to post the amount at the DTL arising.|  
|**DTA Disposal Account**|The account for posting the gain and loss, on the debit side of which the amount of a DTA that is not discharged is written off at disposal of the asset object.|  
|**DTL Disposal Account**|The account for posting the gain and loss, on the credit side of which the amount of a DTL that is not discharged is written off at disposal of the asset object.|  
|**DTA Transfer Bal. Account**|The account for posting tax and fee payments used as a balance account for DTA transfer into CTL.|  
|**DTL Transfer Bal. Account**|The account for posting tax and fee payments used as a balance account for DTL transfer into CTA.|  
|**CTA Transfer Tax Account**|The account for posting the gain and loss, on the credit side of which the amount of a DTL that is not discharged is written off for DTL transfer into CTA.|  
|**CTL Transfer Tax Account**|The account for the posting gain and loss, on the debit side of which the amount of a DTA that is not discharged is written off for DTA transfer into CTL.|  
  
## Setting Up Tax Difference Journals  
 After setting up the posting groups, you need to set up the Tax Difference Accounting journal.  
  
 The following procedure shows how to set up the Tax Difference Accounting journal.  
  
1.  In the **Tax Accounting** menu, click **Setup**, and then click **Tax Differences**.  
  
2.  Click **Journal Templates**.  
  
3.  Enter the fields described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**Name**|The name of the tax accounting journal template.|  
    |**Description**|The description showing the purpose of the journal template.|  
    |**Type**|Select the **General** type.|  
    |**Source Code**|Select a code corresponding to the tax differences from the source code list.|  
  
4.  Click the **Template** button at the bottom of the form, and then select **Batches**.  
  
5.  Enter the batch name in the Name column and the description of the batch purpose in the Description column.  
  
## Setting Up Tax Difference Registers  
 In the Tax Accounting menu, click **Setup**, click **Tax differences**, and then click **Calc. Sections** to form a list of tax difference registers and to describe a tax difference counting algorithm in each register.  
  
 Entering the fields needed and the values shown in the information fields are similar to that of the Tax register section described in detail in the topic Tax Accounting.  
  
 To create a register list for tax differences  
  
-   Click the **Registers** button, and select **List**.  
  
 In the **Tax Calc. List** form, you can enter or delete an existing register.  
  
 Enter the fields described in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**No.**|The code of a tax difference counting register.|  
|**Description**|The description showing the purpose of the register.|  
|**Table ID**|Select one of the following options:<br /><br /> -   **17314** – For registers intended to count on the basis of norms and information from other registers.<br />-   **17315** – For registers intended to collect information from finance accounts.<br />-   **17317** – For registers intended to collect information on the basis of item entries.<br />-   **17318** – For registers intended to collect information on fixed assets.|  
|**Storing Method**|Select **Calculation** for counted registers \(17314\) and **Build Entry** for other registers.|  
|**Tax Diff. Code**|The code of the tax difference from the list that must be counted in this register|  
  
 After setting up the list of tax difference counting registers, you must set up an algorithm of data collection and presentation in tax difference registers.  
  
 The following procedure shows how to set up tax difference registers.  
  
1.  In the **Tax Accounting** menu, click **Setup**, click **Tax Differences**, and then click **Calc. Sections**.  
  
2.  Click the **Registers** button, and then select **Register Card**.  
  
 Setting up tax difference registers is similar to setting up tax registers, which is described in detail in the topic Tax Accounting.  
  
 Registers intended for collecting information from finance accounts \(option **17315** in the **Table ID** field\) contain the **Tax Diff. Amount \(Tax\)** field and the **Tax Diff. Amount \(Base\)** field in the form. You can select one of the following:  
  
-   **Tax Diff. Amount \(Base\)** field \- The value of this register line will be used as the basis to calculate the tax difference. The value corresponds to expenses in bookkeeping.  
  
-   **Tax Diff. Amount \(Tax\)** field \- The value of this register line will be used as the basis to calculate the tax difference. The value corresponds to expenses in tax accounting.  
  
-   Calculated amounts for lines with **Tax Diff. Amount \(Tax\)** field and **Tax Diff. Amount \(Base\)** field \- If the amounts are different, a tax difference will appear.  
  
 A line in the register reflects the value of the counting register \(option **17314** in the **Table ID** field\). To set this value, select **Link** in the **Expression Type** field and select the code of the counting register in the **Link Register No.** field.  
  
## Tax Difference for Future Expenses Calculation Settings  
 If the reason for the tax difference is the income and expense of future periods, the tax difference calculation is set by using the **Future Expenses** menu in the **Setup** submenu of the **Tax Accounting** menu.  
  
 The set up of entries for expenses of future periods is organized similar to how you set up and work with fixed assets.  
  
### Posting Groups  
 In the Posting Groups sub\-item, you can set up posting groups to create finance transactions for writing\-off expenses of future periods in bookkeeping. You can use posting groups if the finance transactions must be created automatically when counting the depreciation of the expenses of future periods.  
  
### Depreciation Books  
 In the Depreciation Books sub\-item, you must set up depreciation books for expenses of future periods for tax accounting and bookkeeping. The set up of depreciation book of future expenses is similar to the depreciation book set up for fixed assets. If the depreciation book is used to create tax accounting entries, the value of the **Posting Book Type** field must be **Tax Accounting**. If the depreciation book is intended to create bookkeeping entries, the value of the **Posting Book Type** field must be **Accounting**.  
  
### Depreciation Tables  
 If none of the standard depreciation methods \(such as SL or DB\) is suitable for writing off the expenses, then, in the Depreciation Tables sub\-item, you can set up the creation of future periods writing off entries. The settings of depreciation tables for future expenses are similar to the settings of depreciation tables for fixed assets.  
  
### Journal Templates  
 Templates and batches of the journals are set up in the same way as FA Journal Templates in the sub\-item Journal Templates.  
  
## Create Future Expenses Writing\-off  
 The following procedure shows how to create lines for writing off expenses for future periods.  
  
1.  In the **Tax Accounting** menu, click **Periodic Activities,** and then click **Calculate FE Depreciation** to open the **Calculate FE Depreciation** form.  
  
2.  In the **Calculate FE Depreciation** form, on the **Options** tab, in the **Depreciation Book Filter** field, select **Tax Accounting Depreciation Book**.  
  
3.  Enter the **Accounting Period** field.  
  
4.  Select the **Change Details** field and manually enter the details in the following fields:  
  
    -   **FA Posting Date**  
  
    -   **Posting Date**  
  
    -   **Document No**  
  
    -   **Posting Description**  
  
    -   **Use Force No. of Days**  
  
    -   **Force No. of Days**  
  
    -   **Insert Bal. Account**  
  
        > [!NOTE]  
        >  If the **Change Details** field is not selected, the other fields are filled automatically.  
  
5.  On the **Fixed Asset** tab, set up a filter for **Future expenses** that must be depreciated. If no filter is determined, the periodic activity will process all the set up expenses of future periods.  
  
6.  Click **OK**.  
  
7.  In the **Tax Accounting** menu, click **Future Expense Journal** to view the result of this periodic activity.  
  
## Future Expenses Journal  
 The Future Expenses journal is used to create and post transactions that contain expenses of future periods.  
  
 When you select **Future Expense Journals** in the**Tax Accounting** menu, you can manually create journal lines for acquisition, write off, and depreciation of expenses for future periods.  
  
 The journal enables you to use values in the lines created as a result of running periodic activities. After you check existing journal lines, you can post the journal to create entries with expenses of future periods. Tax differences will be formed on the basis of these entries.  
  
 Fields in the Future Expenses journal are described in the following table.  
  
|Field|Description|  
|-----------|-----------------|  
|**FA Posting Date**|Enter the transaction date.|  
|**Document No.**|Enter the document number that the current transaction is created with.|  
|**FA No.**|Enter the code of the expense of the future period that the current transaction is created with.|  
|**Depreciation Book Code**|Select the code of the depreciation book that the transaction will be formed with.|  
|**FA Posting Type**|Select the **Transaction** type. The values are: **Purchase**, **Depreciation**, and **Sales**.|  
|**Description**|Enter a description of the transaction.|  
|**Amount**|Enter the amount of the transaction.|  
|**Depr. Amount w\/o Normalization**|Displays the depreciation amount before calculating norms of expenses to write off.|  
  
 If there are journal lines that must be normalized before writing off expenses, those journals cannot be posted without running a periodic job of normalizing.  
  
 The following procedure shows how to process a normalization function.  
  
1.  In the Future Expenses journal, click **Function**, and then click **Calculate Depreciation by Norm.**  
  
2.  In the **Calculate FE Depr. With Norm** form, on the **Tax Difference** tab, enter the filter for the tax difference.  
  
3.  On the **Options** tab, enter the accounting period for which the counting is done.  
  
4.  Click **Print** to print the report.  
  
5.  Post the Future Expenses journal.  
  
## See Also  
 [Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-registers.md)   
 [Tax Differences](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)   
 [Tax Difference Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-difference-registers.md)   
 [How to: Set Up Norm Jurisdictions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-norm-jurisdictions.md)   
 [How to: Post Tax Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-post-tax-differences.md)