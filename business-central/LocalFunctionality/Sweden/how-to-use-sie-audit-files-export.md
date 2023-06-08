---
title: Import and export data in the standard import export (SIE) format
description: This article explains how to import and export general ledger data according to the standard import export (SIE) format for Sweden.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 5264, 5266, 5267, 5270, 5315
ms.date: 06/08/2023
ms.author: altotovi

---

# Import and export data in the standard import export (SIE) format

You can import and export general ledger data according to the standard import export (SIE) format. By specifying SIE dimensions and file types, you can define the level of detail that's covered by import or export transactions. For more information, see [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).

> [!NOTE]
> SIE Audit Files Export is part of the Swedish localization. However, as of version 22.1, the Swedish localization will be based on the W1 base app, and the SIE functionality will be moved to the extension that's installed by default. This functionality is based on the Audit Files Export app that has the pre-installed SIE format. To learn more about this change, see [Audit Files Export](../../finance-how-to-export-audit-files.md).

Even if the feature is preinstalled, it's not enabled by default. Follow these steps to enable the feature.

1.  Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, go to the **Feature Management** workspace, and then select the related link.  
2.  Find the feature, **Feature update: Enable using SIE Audit Files Exports** and in the **Enabled for** column, select **All users**.

## Audit files export 

When you enable **SIE Audit Files Export** in **Feature Management**, you're lead through the wizard to set up your feature. However, you can set up the feature at a later time by running the **SIE Audit File Export Setup Guide** page. If you want to set up the system manually, use the following steps:

    [!INCLUDE [Audit Files Export](../../finance-how-to-export-audit-files.md)]

### To setup SIE dimensions

1.  Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimensions SIE**, and then select the related link.  
2.  In the **Dimension Code** field, select one of standard dimensions you want to map. 
3.  in the **SIE Dimension** field, specify the number you want to assign to the dimension. 
4.  in the **Selected** field, specify if the dimension should be used when importing or exporting G/L data.

### Audit file export document for SIE

When you have opened **Audit File Export Document** page, you will find a few fields specific only for SIE you need to populate before starting.

- On the **SIE** FastTab, in the **File type** field, select a value to specify the type of SIE file to create. Select from the following options: 
    
    - Year - End Balances
    - Periodic Balances
    - Object Balances
    - Transactions

   All other fields are populated by default based on your previous set up.

## See also

[Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)  
[Sweden Local Functionality](sweden-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
