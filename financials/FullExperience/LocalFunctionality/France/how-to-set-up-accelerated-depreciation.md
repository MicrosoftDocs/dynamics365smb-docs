---
title: "How to: Set Up Accelerated Depreciation"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "accelerated depreciation, setting up"
ms.assetid: 4afd453b-4d58-4954-abbd-35a0572351bf
caps.latest.revision: 27
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# How to: Set Up Accelerated Depreciation
To use the accelerated depreciation calculation, you must set up the following depreciation books for fixed assets:  
  
-   The accounting depreciation book \(integrated with the general ledger\).  
  
-   The tax depreciation book \(not integrated with the general ledger\).  
  
> [!NOTE]  
>  When you post an acquisition, depreciation, or disposal for the accounting depreciation book, the transaction is duplicated and posted in the tax depreciation book when the fixed asset journal is posted.  
  
### To set up the accounting depreciation book  
  
1.  In the **Search** box, enter **Depreciation Books**, and then choose the relevant link.  
  
2.  In the **Depreciation Book List** window, on the **Home** tab, choose **New**.  
  
3.  On the **General** FastTab, fill in the required fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique identification code for the accounting depreciation book. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The depreciation book description.|  
  
    > [!IMPORTANT]  
    >  Leave the **Derogatory Calculation** field blank.  
  
4.  On the **Integration** FastTab, select the **Derogatory** check box to integrate accelerated depreciation with the general ledger.  
  
     For more information, see [How to: Set Up Depreciation Books](../../Finance/how-to-set-up-depreciation-books.md) and Depreciation Book.  
  
5.  Choose the **OK** button.  
  
### To set up the tax depreciation book  
  
1.  In the **Search** box, enter **Depreciation Books**, and then choose the relevant link.  
  
2.  In the **Depreciation Book List** window, on the **Home** tab, choose **New**.  
  
3.  On the **General** FastTab, fill in the required fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique identification code for the tax depreciation book. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The tax depreciation book description.|  
  
4.  In the **Derogatory Calculation** field, select the accounting depreciation book code to indicate that this is a tax depreciation book to calculate derogatory depreciation.  
  
     For more information, see [How to: Set Up Depreciation Books](../../Finance/how-to-set-up-depreciation-books.md) and Depreciation Book.  
  
5.  Choose the **OK** button.  
  
     The **Used with Derogatory Book** field in the accounting depreciation book is updated with the tax depreciation book code.  
  
## See Also  
 [Accelerated Depreciation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/accelerated-depreciation.md)   
 [How to: Calculate Accelerated Depreciation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-calculate-accelerated-depreciation.md)   
 [How to: Set Up Depreciation Books](../../Finance/how-to-set-up-depreciation-books.md)   
 Depreciation Book   
 Fixed Asset   
 Fixed Asset Card   
 [Set Up Depreciation](../../Finance/set-up-depreciation.md)