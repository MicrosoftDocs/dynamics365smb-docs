---
title: "How to: Set Up Cost Objects"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, setting up cost objects"
ms.assetid: 6863684d-f873-4dd3-a8bf-2b0d4dc1ecc6
caps.latest.revision: 12
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
# How to: Set Up Cost Objects
Cost objects are projects, products, or services of a company. The chart of cost objects is similar to the dimension information for the general ledger. You can set up the chart of cost objects in the following ways:  
  
-   Transfer dimension values in the general ledger to the chart of cost objects. You can make any necessary adjustments after the transfer.  
  
-   Create a new chart of cost object that is independent of the general ledger or add a new cost object to an existing chart of cost objects. You must create each cost object individually.  
  
### To transfer dimension values from the general ledger to the chart of cost objects  
  
1.  Set a dimension to be the cost object dimension in the **\($ R\_1140 Update CA Dimensions $\)** window. Only the values from this dimension are transferred.  
  
2.  In the **Search** box, enter **\($ N\_1123 Chart of Cost Objects $\)**, and then choose the related link.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Get Cost Objects from Dimension** to transfer dimension values to the chart of cost objects. The function transfers the dimension values that you defined in step 1.  
  
    > [!NOTE]  
    >  You can set up the **\($ T\_1108\_5 Align Cost Object Dimension $\)**  field to define a one\-way synchronization of dimension values from the general ledger to the chart of cost objects. You cannot define a synchronization of the chart of cost objects to dimension values from the general ledger.  
  
 The chart of cost objects now contains all specified dimension values from the general ledger and includes titles and subtotals.  
  
### To create new cost objects in the \($ N\_1123 Chart of Cost Objects $\) window  
  
1.  > [!NOTE]  
    >  You can set up and maintain cost objects in either the **\($ N\_1112 Cost Object Card $\)** card or in the **\($ N\_1123 Chart of Cost Objects $\)** window. In this procedure, you set up cost objects in the **\($ N\_1123 Chart of Cost Objects $\)** window.  
  
2.  Open the **\($ N\_1123 Chart of Cost Objects $\)** window in edit mode.  
  
3.  In the **\($ T\_1113\_1 Code $\)** field, enter the cost object code. All cost objects must have a code.  
  
4.  In the **\($ T\_1113\_2 Name $\)** field, enter the cost object name.  
  
5.  Choose the drop\-down arrow in the **\($ T\_1113\_9 Line Type $\)** field to specify the purpose of the cost object.  
  
    -   For cost objects of the **Total** line type, fill in the **\($ T\_1113\_14 Total From\/To $\)** field. Use the **or** operator, which is a vertical line \(**&#124;**\), to set ranges of cost objects.  
  
    -   For cost objects of the **End\-Total** line type, this field is filled in automatically when you use  the indent function.  
  
6.  Fill in the **\($ T\_1113\_7 Sorting Order $\)** field.  
  
7.  Chose the next empty line to create a new cost object, and then repeat steps 2 through 5.  
  
8.  After you have set up all the cost objects, on the **Home** tab, in the **Process** group, choose **Indent Cost Objects**. Choose the **Yes** button.  
  
> [!IMPORTANT]  
>  If you have entered definitions in the **\($ T\_1113\_14 Total From\/To $\)** fields for **End\-Total** cost objects before you run the indent function, then you must enter them again. The function overwrites the values in all **End\-Total** fields.  
  
## See Also  
 [\($ N\_1123 Chart of Cost Objects $\)](assetId:///56ef6dfc-5c76-498d-a256-a611107e7694)   
 [\($ N\_1112 Cost Object Card $\)](assetId:///273a3cf5-cedf-4c39-849a-79c6fd561583)   
 [Defining Cost Centers and Cost Objects for Chart of Accounts](../Finance/defining-cost-centers-and-cost-objects-for-chart-of-accounts.md)   
 [Balances Between Cost Type, Cost Center, and Cost Object](../Finance/balances-between-cost-type-cost-center-and-cost-object.md)   
 [\($ B\_1140 Update Cost Acctg. Dimensions $\)](../Topic/\($%20B_1140%20Update%20Cost%20Acctg.%20Dimensions%20$\).md)   
 [\($ T\_1108\_5 Align Cost Object Dimension $\)](assetId:///0fed2fed-c7a7-49ec-b96f-75b082094d38)   
 [Set Up Cost Accounting](../Finance/set-up-cost-accounting.md)   
 [Terminology in Cost Accounting](../Finance/terminology-in-cost-accounting.md)   
 [About Cost Accounting](../Finance/about-cost-accounting.md)