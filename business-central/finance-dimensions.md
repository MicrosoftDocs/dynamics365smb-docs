---
title: Work with Dimensions
description: You use dimensions to categorize entries, for example, by department or project, so you can easily track and analyze data.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, history, track
ms.date: 10/01/2020
ms.author: edupont

---
# Working with Dimensions

Dimensions are values that categorize entries so you can track and analyze them on documents, such as sales orders. Dimensions can, for example, indicate the project or department an entry came from.  

For example, instead of setting up separate general ledger accounts for each department and project, you can use dimensions as a basis for analysis and avoid having to create a complicated chart of accounts. For more information, see [Business Intelligence](bi.md).

Another example is to set up a dimension called *Department*, and use this dimension when you post sales documents. This will let you use business intelligence tools to see which department sold which items. The more dimensions you use, the more detailed reports you can base your business decisions on. For example, a single sales entry can include information from multiple dimensions, such as:  

* The account the item sale was posted to  
* Where the item was sold
* Who sold it
* The kind of customer who bought it  

For more information about how to set up dimensions, see [Setting Up Dimensions](finance-setup-dimensions.md).  

## Analyzing by Dimensions

Dimensions play an important role in business intelligence, such as when defining analysis views. For more information, see [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

> [!TIP]
> A quick way to analyze transactional data by dimensions is to use the **Set Dimension Filter** action filter totals by dimensions in the chart of accounts and on pages for entries.

## Dimension Sets
<!--we describe what they are, but not their value.-->
A dimension set is a unique combination of dimension values. It is stored as dimension set entries in the database. Each dimension set entry represents a single dimension value. The dimension set is identified by a common dimension set ID that is assigned to each dimension set entry that belongs to the dimension set.  

When you create a journal line, document header, or document line, you can specify a combination of dimension values. Instead of explicitly storing each dimension value in the database, a dimension set ID is assigned to the journal line, document header, or document line to specify the dimension set.  

## Getting an Overview of Dimensions used Multiple Times

The **Default Dimensions-Multiple** page specifies how a group of accounts use dimensions and dimension values. You can do this by highlighting multiple accounts and then specifying default dimensions and dimension values for all the accounts you have highlighted in the account list. When you specify default dimensions for the highlighted accounts, application will suggest these dimensions and dimension values whenever one of these accounts is used, for example on a journal line. This makes entry posting easier for the user, as the dimension fields are filled in automatically. However, the dimension values that are suggested can be changed on, for example, a journal line.

The **Default Dimensions-Multiple** page contains the following fields:

|Field|Description|
|-----|-----------|  
|**Dimension Code**|Shows all dimensions that have been defined as default dimensions on one or more of the highlighted accounts. By choosing the field, you can see a list of all available dimensions. If you select a dimension, the selected dimension will be defined as a default dimension for all highlighted accounts.|
|**Dimension Value Code**|Shows either a single dimension value or the term (Conflict). If a dimension value is shown in the field, then all highlighted accounts have the same default dimension value for a dimension. If the term (Conflict) is shown in the field, then not all of the highlighted accounts have the same default dimension value for a dimension. By choosing the field, you can see a list of all available dimension values for a dimension. If you select a dimension value, the selected dimension value will be defined as a default dimension value for all highlighted accounts.|
|**Value Posting**|Shows either a single value posting rule or the term (Conflict). If a value posting rule is shown in the field, then all highlighted accounts have the same value posting rule for a dimension value. If the term (Conflict) is shown in the field, then not all of the highlighted accounts have the same value posting rule for a dimension value. By choosing the Value Posting field, you can see a list of value posting rules. If you select a value posting rule, it will be applied for all highlighted accounts.|

## Using Dimensions

In a document such as a sales order, you can add dimension information for both an individual document line and the document itself. For example, on the **Sales Order** page, you can enter dimension values for the first two shortcut dimensions on the individual sales lines, and you can add more dimension information if you choose the **Dimensions** button.  

If you work in a journal instead, you can add dimension information to an entry in the same way, if you have set up shortcut dimensions as fields directly on journal lines.  

You can set up default dimensions for accounts or account types, so that dimensions and dimension values are filled in automatically.

### To view global dimensions in ledger entry pages

Global dimensions are always company\-defined and company-named. To see the global dimensions for your company, open the **General Ledger Setup** page.  

In a ledger entry page, you can see whether there are global dimensions for the entries. The two global dimensions differ from the rest of your dimensions because you can use them as filters anywhere in [!INCLUDE[prod_short](includes/prod_short.md)].  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. On the **Chart of Accounts** page, choose the **Ledger Entries** action.  
3. To see only the entries that are relevant, set one or more filters on the page.  
4. To see all the dimensions for an entry, select the entry, and then choose the **Dimensions** action.  

> [!NOTE]  
> The **Ledger Entry Dimensions** page displays the dimensions for one ledger entry at a time. As you scroll through the ledger entries, the content on the **Ledger Entry Dimensions** page changes accordingly.

## Troubleshooting Dimensions Errors

When you post documents or journal lines that contain dimensions, various errors may occur that are typically related to wrong dimension setup or assignment.

> [!NOTE]
> In the following list of potential error messages, the *%X* codes are placeholders for the data variables that the actual message will contain in the UI depending on the context. For example, *%1 %2 is blocked.* could appear in the UI as *Dimension Code AREA is blocked.*.  

|Issue|Error Message|Possible Solution|
|-----|-------------|-----------------|
|Blocked dimension|%1 %2 is blocked.|-Find non-posted documents containing the dimension set with the blocked dimension and unblock it.<br />-Remove the dimension set line for the blocked dimension.|
|Deleted dimension|%1 %2 can't be found.|-Restore the missing dimension.<br />-Find non-posted documents containing the dimension set with the missing dimension and add it.<br />-Remove the dimension set line for the missing dimension.|
|Blocked dimension value|%1 %2 - %3 is blocked.|-Find non-posted documents containing the dimension set with the blocked dimension value and unblock it.<br />-Remove the dimension set line for the blocked dimension value.|
|Deleted dimension value|    %1 for %2 is missing.|-Restore the missing dimension value.<br />-Find non-posted documents containing the dimension set with the missing dimension value and add it.<br />-Remove the dimension set line for the missing dimension value.|
|Disallowed dimension value|Dimension Value Type for %1 %2 - %3 must not be %4.|-Change the **Dimension Value Type** field on the **Dimension Values** page to **Standard** or **Begin-Total**.<br />-Remove the dimension set line for the blocked dimension value.|
|Blocked dimension combination|Dimensions %1 and %2 can't be used concurrently.|-Find non-posted documents containing the dimension set with the blocked dimension combination and unblock it.<br />-Modify one of the conflicting permission set line for the dimension combination.|
|Blocked dimension value Combination|Dimension combinations %1 - %2 and %3 - %4 can't be used concurrently.|-Find non-posted documents containing the dimension set with the blocked dimension value combination and unblock it.<br />-Modify one of the conflicting permission set line for the dimension value combination.|
|Blank dimension value code for default dimension where the **Value Posting** field contains **Code Mandatory**|-Select a %1 for the %2 %3.<br />-Select a %1 for the %2 %3 for %4 %5.|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Enter a non-blank dimension value for the conflicting dimension in the dimension set.|
|Dimension value is not allowed for the account|Dimension value %1, %2 is not allowed for %3, %4.|-Find the account mentioned in the error message, open its default dimensions and correct the filter in the **Allowed Values Filter** field.<br />-Use the dimension value from the range defined in the **Allowed Values Filter** field for the account.|
|Dimension value is not allowed for the account type|Dimension value %1 %2 is not allowed for account type %3.|- Find the dimension and open the **Account Type Default Dim.** page. Find the default dimension for the account type mentioned in the error message and correct filter in the **Allowed Values Filter** field.<br />-Use the dimension value from the range defined in the **Allowed Values Filter** field for this account type.|
|Wrong dimension value code for default dimension where the **Value Posting** field contains **Same Code**|-Select %1 %2 for the %3 %4.<br />-Select %1 %2 for the %3 %4 for %5 %6|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Enter the required dimension value for the conflicting dimension in the dimension set.|
|Non-blank dimension value code for blank default dimension where the **Value Posting** field contains **Same Code**|-%1 %2 must be blank.<br />-%1 %2 must be blank for %3 %4.|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Enter a blank dimension value code for the conflicting dimension in the dimension set.|
|Unexpected dimension value for default dimension where the **Value Posting** field contains **No Code**|-%1 %2 must not be mentioned.<br />-%1 %2 must not be mentioned for %3 %4|-Change the **Value Posting** field on the **Default Dimension** page.<br />-Remove the conflicting line from the dimension set.|

## See Related Training at [Microsoft Learn](/learn/modules/dimensions-dynamics-365-business-central/index)

## See Also

[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)  
[Setting Up Dimensions](finance-setup-dimensions.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
