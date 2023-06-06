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
ms.date: 04/05/2023
ms.author: altotovi

---

# Import and export data in the standard import export (SIE) format

You can import and export general ledger data according to the standard import export (SIE) format. By specifying SIE dimensions and file types, you can define the level of detail that's covered by import or export transactions. For more information, see [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).

> [!NOTE]
> SIE Audit Files Export is part of the Swedish localization. However, as of version 22.1, the Swedish localization will be based on the W1 base app, and the SIE functionality will be moved to the extension that's installed by default. This functionality is based on the Audit Files Export app that has the pre-installed SIE format. To learn more about this change, see [Audit Files Export](../../finance-how-to-export-audit-files.md).

Even feature is preinstalled, it is not enabled by default. To enable it
1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature Management**, and then choose the related link.  
2.  Find the **Feature update: Enable using SIE Audit Files Exports** and choose **All users** option in the **Enabled for** column.

## Audit Files Export 

When you enable **SIE Audit Files Export** in the **Feature Management** you will be lead through the wizard to set up your feature, but you can also do it later running the **SIE Audit File Export Setup Guide** page. If you want to set up the system manually, you can do it using the following steps:

[!INCLUDE [Audit Files Export](../../finance-how-to-export-audit-files.md)]

### To setup SIE dimensions

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimensions SIE**, and then choose the related link.  
2.  In the **Dimension Code** field choose one of standard dimensions you want to map. 
3.  in the **SIE Dimension** field specifiy the number you want to assign to the dimension. 
4.  in the **Selected** field specify if this dimension should be used when importing or exporting G/L data.

### Audit File Export Document for SIE

When you have opened **Audit File Export Document** page, you will find a few fields specific only for SIE you need to populate before starting:
1.  You need to choose the **File Type** in the **SIE** FastTab to specify the type of SIE file to create. You can choose one of the options: 
    i. Year - End Balances
    ii. Periodic Balances
    iii. Object Balances
    iv. Transactions
2.  All other fields will be populated by default based on your previous set up.

## See also

[Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)  
[Sweden Local Functionality](sweden-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
