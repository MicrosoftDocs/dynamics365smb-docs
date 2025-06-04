---
title: Troubleshoot and correct dimensions
description: Learn how to troubleshoot typical dimension errors, and how to correct dimensions after they're used on posted transactions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: troubleshooting-general
ms.search.keywords: dimension, correction, correct, business intelligence
ms.search.form: 116, 540, 2588
ms.date: 08/08/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Troubleshoot and correct dimensions

Financial reporting and analysis views often rely on data from dimensions. Despite the safeguards that are available, sometimes a mistake happens that can lead to inaccuracies. This article describes some of the typical errors, and explains how to correct dimension assignments on posted transactions so that financial reports are accurate.

## Troubleshooting dimensions errors

When you post documents or journal lines that contain dimensions, various errors might occur. However, they're typically related to an incorrect dimension setup or assignment.

> [!NOTE]
> In the following list of potential error messages, the *%X* codes are placeholders for the data variables that the actual message will contain in the UI depending on the context. For example, *%1 %2 is blocked.* could appear in the UI as "Dimension Code AREA is blocked.".  

|Issue|Error Message|Possible Solution|
|-----|-------------|-----------------|
|Blocked dimension|%1 %2 is blocked.|-Find nonposted documents containing the dimension set with the blocked dimension and unblock it.<br />-Remove the dimension set line for the blocked dimension.|
|Deleted dimension|%1 %2 can't be found.|-Restore the missing dimension.<br />-Find nonposted documents containing the dimension set with the missing dimension and add it.<br />-Remove the dimension set line for the missing dimension.|
|Blocked dimension value|%1 %2 - %3 is blocked.|-Find nonposted documents containing the dimension set with the blocked dimension value and unblock it.<br />-Remove the dimension set line for the blocked dimension value.|
|Deleted dimension value|    %1 for %2 is missing.|-Restore the missing dimension value.<br />-Find nonposted documents containing the dimension set with the missing dimension value and add it.<br />-Remove the dimension set line for the missing dimension value.|
|Disallowed dimension value|Dimension Value Type for %1 %2 - %3 must not be %4.|-Change the **Dimension Value Type** field on the **Dimension Values** page to **Standard** or **Begin-Total**.<br />-Remove the dimension set line for the blocked dimension value.|
|Blocked dimension combination|Dimensions %1 and %2 can't be used concurrently.|-Find nonposted documents containing the dimension set with the blocked dimension combination and unblock it.<br />-Modify one of the conflicting permission set lines for the dimension combination.|
|Blocked dimension value Combination|Dimension combinations %1 - %2 and %3 - %4 can't be used concurrently.|-Find nonposted documents containing the dimension set with the blocked dimension value combination and unblock it.<br />-Modify one of the conflicting permission set lines for the dimension value combination.|
|Blank dimension value code for default dimension where the **Value Posting** field contains **Code Mandatory**|-Select a %1 for the %2 %3.<br />-Select a %1 for the %2 %3 for %4 %5.|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Enter a nonblank dimension value for the conflicting dimension in the dimension set.|
|Wrong dimension value code for default dimension where the **Value Posting** field contains **Same Code**|-Select %1 %2 for the %3 %4.<br />-Select %1 %2 for the %3 %4 for %5 %6|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Enter the required dimension value for the conflicting dimension in the dimension set.|
|Nonblank dimension value code for blank default dimension where the **Value Posting** field contains **Same Code**|-%1 %2 must be blank.<br />-%1 %2 must be blank for %3 %4.|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Enter a blank dimension value code for the conflicting dimension in the dimension set.|
|Unexpected dimension value for default dimension where the **Value Posting** field contains **No Code**|-%1 %2 must not be mentioned.<br />-%1 %2 must not be mentioned for %3 %4|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Remove the conflicting line from the dimension set.|
|A dimension correction doesn't complete correctly.||-Choose **Reset** to revert the correction to a draft state. This resets the changes, and you can run the correction again.|

## Changing dimension assignments after posting

If you discover an incorrect dimension on posted general ledger entries, you can correct the dimension values and update your analysis views. The correction helps keep your financial reports and analyses accurate.

> [!IMPORTANT]
> The features for correcting dimensions are intended only to help make financial reporting accurate. Dimension corrections apply only to the G/L entries. They do not change the dimensions assigned to the entries in other ledgers for the same transaction. There will be a mismatch between the dimensions assigned in the general ledger and the sub-ledgers.

### Set up dimension corrections

There are two things to consider when setting up dimension corrections:

* Are there dimensions that you don't want to allow people to change? On the **Dimension Correction Settings** page, specify the dimensions that you want to block for changes.
* Who can change dimensions? To allow people to make changes, assign the **D365 DIM CORRECTION** permission to the users. The permissions allow them to create dimension corrections, run them, and undo them if needed. They can also specify blocked dimensions. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md). 

### Correct a dimension

You can manually select one or more general ledger entries, or use filters to select sets of entries. If needed, you can also add or delete dimensions. 

1. To start a dimension correction, use one the following pages:

    * On the **G/L Registers** page, by selecting a register, and then choosing the **Correct Dimensions** action. This action starts a correction for the entries in the selected register.
    * On the **General Ledger Entries** page, by choosing the **Correct Dimensions** action. 

2. In the **Description** field, enter information about the change. Other people might use this information later to understand what was done.
3. On the **Selected Ledger Entries** FastTab, choose the relevant entries.

    > [!IMPORTANT]
    > When you change a selection, the values on the **Dimension Correction Changes** FastTab are reset. Therefore, always select the entries before you specify dimension value changes.

   The following table describes the options.

   |Option  |Description  |
   |---------|---------|
   |Add Related Entries     |Add G/L entries that are in the same G/L register.|   
   |Add by Filter     |Use filter criteria when adding G/L entries.|
   |Manual Selection     |Select specific G/L entries.         |
   |Add by Dimensions     |Filter G/L entries by dimensions.         |
   |Remove Entries     |Deselect G/L entries.         |
   |Manage Selection Criteria     |Keep track of the selection process, and undo selections if needed.         |

4. On the **Dimension Correction Changes** FastTab, choose the dimension that you want to change in the **Dimension Code** field, and the new value in the **New Dimension Value Code** field.
5. To validate that the correction, choose **Validate Dimension Changes**. For more information, see [Validating Dimension Corrections](finance-troubleshooting-correcting-dimensions.md#validate-dimension-corrections).
6. Choose **Run**.

### Validate dimension corrections

Before you run a correction, it's a good idea to validate it first. Validation checks for restrictions on value posting for the G/L accounts, restrictions for dimensions, and whether the dimension values are blocked. During validation, the status of the correction is set to **Validation in Process**. After you validate a correction, the result is shown in the **Validation Status** field. If errors were found, you can use the **View Errors** action to investigate them. After you correct an error, you must use the **Reopen** action to run the correction or a new validation.

You can either run a correction immediately, or schedule it to run a later time. If you're running corrections on a large data set, we recommend that you schedule it to run outside business hours. For more information, see [Dimension Corrections on Large Data Sets](finance-troubleshooting-correcting-dimensions.md#dimension-corrections-on-large-data-sets).

### Undo a correction

After you correct a dimension, if you don't like what you see you can use the **Undo** action to reset the previous value. However, you can only undo the most recent correction. Before you undo a correction, you can validate the changes that result from the undo action. For example, validation is useful if dimension restrictions changed after the correction was made.

If the Undo action isn't available, for example because you have many corrections, you can use the **Copy to Draft** action to start a new correction for the same entries.

### Dimension corrections on large data sets

Use caution when correcting large sets of entries, for example, sets that include more than 10,000 entries. If you can, we recommend that you use the filters to run the corrections on smaller sets of data. It's also a good idea to run corrections outside the normal business hours. 

### Use analysis views with dimension corrections

If **Update on Posting** is enabled for an analysis view, [!INCLUDE[prod_short](includes/prod_short.md)] can update the view when documents and journals are posted. You can also update views with this setting enabled with results of dimension corrections. To do so, turn on the **Update Analysis Views** toggle. Updating analysis views can affect performance, especially for large data sets, so we recommend that you update analysis views only for small data sets.  

### View historical dimension corrections

If a general ledger entry was corrected, you can investigate the change by using the **History of Dimension Corrections** action.

### Handle incomplete corrections

If a correction doesn't complete, a warning displays on the correction card. If that happens, you can use the **Reset** action to revert the correction to a draft status and undo the changes. You can then run the correction again.

> [!NOTE]
> Resetting an incomplete correction will not affect updates to analysis views because those happen at the end of the correction process.

### Use cost accounting with corrected G/L entries

After you correct dimensions, your data for cost accounting is out of sync. Cost accounting uses dimensions to aggregate amounts for cost centers and cost objects, and to run cost allocations. Changing dimensions for G/L entries probably means that you should rerun your cost accounting models. Depending on the data that was updated and how your cost accounting capabilities are set up, you might need to:

* Delete just a few cost registers and rerun allocations.
* Delete everything and rerun all of your models.

You must manually identify where dimension corrections affect cost accounting, and where updates are needed. [!INCLUDE[prod_short](includes/prod_short.md)] doesn't currently provide an automated way to do that.

## Related information

[Work with Dimensions](finance-dimensions.md)    
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
