---
title: "How to: Set Up Cost Centers"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, setting up cost centers"
ms.assetid: cf116143-d296-4f01-89c7-a990cdef9a61
caps.latest.revision: 15
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
# How to: Set Up Cost Centers
Cost centers are departments that are responsible for costs and income. The chart of cost centers is similar to the dimension information for the general ledger. You can set up the chart of cost centers in the following ways:  
  
-   Transfer dimension values in the general ledger to the chart of cost centers. You can make any necessary adjustments after the transfer.  
  
-   Create a new chart of cost center that is independent of the general ledger or add a new cost center to an existing chart of cost center. You must create each cost center individually.  
  
### To transfer dimension values in the general ledger to the chart of cost centers  
  
1.  Set up a dimension to be the cost center dimension in the **\($ R\_1140 Update Cost Acctg. Dimensions $\)** window. Only the values from this dimension are transferred.  
  
2.  In the Search box, enter **\($ N\_1122 Chart of Cost Centers $\)**, and then choose the related link.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Get Cost Centers from Dimension** to transfer dimension values to the chart of cost centers. The function transfers the dimension values that you defined in step 1.  
  
    > [!NOTE]  
    >  You can set up the **\($ T\_1108\_4 Align Cost Center Dimension $\)**  field to define a one\-way synchronization of dimension values from the general ledger to the chart of cost centers. You cannot define a synchronization of the chart of cost centers to dimension values from the general ledger.  
  
 The chart of cost centers now contains all specified dimension values from the general ledger and includes titles and subtotals.  
  
### To create new cost centers in the \($ N\_1122 Chart of Cost Centers $\) window  
  
1.  > [!NOTE]  
    >  You can set up and maintain cost centers in either the **\($ N\_1111 Cost Center Card $\)** card or in the **\($ N\_1122 Chart of Cost Centers $\)** window. In this procedure, you set up cost centers in the **\($ N\_1122 Chart of Cost Centers $\)** window.  
  
     Open the **\($ N\_1122 Chart of Cost Centers $\)** window in edit mode.  
  
2.  In the **\($ T\_1112\_1 Code $\)** field, enter the cost center code. All cost centers must have a code.  
  
3.  In the **\($ T\_1112\_2 Name $\)** field, enter the cost center name.  
  
4.  Choose the drop\-down arrow in the **\($ T\_1112\_12 Line Type $\)** field to specify the purpose of the cost center.  
  
    -   For cost centers of the **Total** type, you must fill in the **\($ T\_1112\_17 Totaling $\)** field. Use the **or** operator, which is a vertical line \(**&#124;**\) to set ranges of cost centers.  
  
    -   For cost centers of the **End\-Total** line type, this field is filled in automatically when you use the indent function.  
  
5.  Fill in the **\($ T\_1112\_10 Sorting Order $\)** and **\($ T\_1112\_3 Cost Subtype $\)** fields.  
  
6.  Choose the next empty line to create a new cost center, and then repeat steps 2 through 5.  
  
7.  After you have set up all the cost centers, on the **Home** tab, in the **Process** group, choose **Indent Cost Centers**. Choose the **Yes** button.  
  
> [!IMPORTANT]  
>  If you have entered definitions in the **\($ T\_1112\_17 Totaling $\)** fields for **End\-Total** cost centers before you run the indent function, then you must enter them again. The function overwrites the values in all **End\-Total** fields.  
  
## See Also  
 [\($ N\_1122 Chart of Cost Centers $\)](assetId:///45601b31-e343-43d4-b828-9f6f8fd249e4)   
 [\($ N\_1111 Cost Center Card $\)](assetId:///90cc9486-e6b5-4590-862b-1e8f309d3c8b)   
 [Defining Cost Centers and Cost Objects for Chart of Accounts](../Finance/defining-cost-centers-and-cost-objects-for-chart-of-accounts.md)   
 [Balances Between Cost Type, Cost Center, and Cost Object](../Finance/balances-between-cost-type-cost-center-and-cost-object.md)   
 [\($ B\_1140 Update Cost Acctg. Dimensions $\)](../Topic/\($%20B_1140%20Update%20Cost%20Acctg.%20Dimensions%20$\).md)   
 [\($ T\_1108\_4 Align Cost Center Dimension $\)](assetId:///49e0e7d3-2519-4177-a6f0-87e941c78861)   
 [Set Up Cost Accounting](../Finance/set-up-cost-accounting.md)   
 [Terminology in Cost Accounting](../Finance/terminology-in-cost-accounting.md)   
 [About Cost Accounting](../Finance/about-cost-accounting.md)