---
title: "How to: Set Up Cost Types"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, setting up cost types"
ms.assetid: d8323111-3a9a-469b-98ed-7b16ff00d19d
caps.latest.revision: 19
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up Cost Types
Chart of cost types are similar to the chart of accounts in the general ledger. You can set up the chart of cost types in the following ways:  
  
-   Structure the chart of cost types similar to the income statement accounts in the general ledger chart of accounts. Then, you can transfer the general ledger chart of accounts to the chart of cost types. You can make any necessary adjustments after the transfer.  
  
-   Create new chart of cost types or add new cost types to existing chart of cost types. You must create each new cost type individually.  
  
### To transfer the general ledger chart of accounts to the chart of cost types  
  
1.  In the **Search** box, enter **Chart of Cost Types**, and then choose the related link.  
  
2.  On the **Actions** menu, in the **Functions** group, choose **Get Cost Types from Chart of Accounts**. In the dialog box, choose the **Yes** button to confirm the transfer. The function uses the chart of accounts to create a chart of cost types.  
  
     The chart of cost types now contain all income statement accounts in the general ledger and include headings and subtotals. You can change the chart of cost types, as necessary. For example, you can delete duplicate existing cost types.  
  
> [!IMPORTANT]  
>  The **Register Cost Types in Chart of Accounts** function updates the relationship between the chart of accounts and the chart of cost types. The **No.** field is filled and verified to make sure that each general ledger account is related to only one cost type. The function runs automatically before transferring general ledger entries to cost accounting.  
  
### To set up new cost types in the Chart of Cost Types window  
  
1.  Open the **Chart of Cost Types** window in edit mode.  
  
2.  Fill in the fields as described in the following table.  
  
    > [!NOTE]  
    >  You can set up and maintain cost types in either the **Cost Type Card** window or in the **Chart of Cost Types** window. In this procedure, you set up cost types in the **Chart of Cost Types** window.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Enter the cost type number. All cost types must have a number.|  
    |**Name**|Enter the cost type name.|  
    |**Line Type**|Specify the purpose of the cost type. Only the cost type option indicates a cost type that you can post to. The other types are used to create totals and headings. For line types of the **Total** type, you must fill in the **Totaling** field. For line types of the **End\-Total** type, the field is filled in automatically when you use the **Indent Cost Types** function.|  
    |**G\/L Account Range**|Enter the general ledger account range.|  
    |**Cost Center Code**|Enter the cost center code.|  
    |**Cost Object Code**|Enter the cost object code.|  
    |**Combine Entries**|Select to set the option to allow for general ledger entries to be posted individually or posted as a combined posting for a specific day or month.|  
    |||  
  
3.  After you have created all cost types, on the **Home** tab, in the **Process** group, choose **Indent Cost Types**. In the dialog box, choose the **Yes** button.  
  
4.  Link the new cost type to the corresponding general ledger account.  
  
> [!IMPORTANT]  
>  If you have entered definitions in the **Totaling** fields for the line type of **End\-Total** before you run the **Indent Cost Types** function, then you must enter the definitions again because the function overwrites the values in all **End\-Total** fields.  
  
### To update cost types  
  
1.  In the **Cost Accounting Setup** window, select if you want the chart of cost types to be automatically updated when the chart of accounts is changed.  
  
2.  In the **Align G\/L Account** field, you can choose from the following options.  
  
    -   **No Alignment** \- There is no corresponding change in the chart of cost types when you change the chart of accounts.  
  
    -   **Automatic** \- A corresponding change is made in the chart of cost types when you change the chart of accounts.  
  
    -   **Prompt** \- A message is displayed asking if you want to make a corresponding change in the chart of cost types when you change the chart of accounts.  
  
## See Also  
 Chart of Cost Types   
 Cost Type Card   
 [Defining the Relationship Between Cost Types and General Ledger Accounts](../Finance/defining-the-relationship-between-cost-types-and-general-ledger-accounts.md)   
 [Defining Cost Centers and Cost Objects for Chart of Accounts](../Finance/defining-cost-centers-and-cost-objects-for-chart-of-accounts.md)   
 [Balances Between Cost Type, Cost Center, and Cost Object](../Finance/balances-between-cost-type-cost-center-and-cost-object.md)   
 [Set Up Cost Accounting](../Finance/set-up-cost-accounting.md)   
 [Terminology in Cost Accounting](../Finance/terminology-in-cost-accounting.md)   
 [About Cost Accounting](../Finance/about-cost-accounting.md)