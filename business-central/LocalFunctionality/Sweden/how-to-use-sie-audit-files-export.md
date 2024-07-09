---
title: Import and export data in the standard import export (SIE) format
description: This article explains how to import and export general ledger data according to the standard import export (SIE) format for Sweden.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.search.form: 5264, 5266, 5267, 5270, 5315
ms.date: 06/08/2023
ms.author: altotovi

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Import and export data in the standard import export (SIE) format

You can import and export general ledger data according to the standard import export (SIE) format. By specifying SIE dimensions and file types, you can define the level of detail that's covered by import or export transactions. For more information, see [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).

> [!NOTE]
> SIE Audit Files Export is part of the Swedish localization. However, as of version 22.1, the Swedish localization will be based on the W1 base app, and the SIE functionality will be moved to the extension that's installed by default. This functionality is based on the Audit Files Export app that has the preinstalled SIE format. To learn more about this change, see [Audit Files Export](../../finance-how-to-export-audit-files.md).

Even if the feature is preinstalled, it isn't enabled by default. Follow these steps to enable the feature.

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, go to the **Feature Management** workspace, and then select the related link.
2. Find the **Feature update: Enable using SIE Audit Files Exports** feature. Then, in the **Enabled for** column, select **All users**.

## Audit files export 

When you enable **SIE Audit Files Export** in Feature Management, you're guided through a wizard to set up the feature. However, you can set up the feature later by running the **SIE Audit File Export Setup Guide** page. If you want to manually set up the system, follow the steps in the article, [Audit files export](../../finance-how-to-export-audit-files.md).

### Set up SIE dimensions

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimensions SIE**, and then select the related link.
2. In the **Dimension Code** field, select one of the standard dimensions that you want to map.
3. In the **SIE Dimension** field, specify the number that you want to assign to the dimension.
4. In the **Selected** field, specify whether the dimension should be used when General ledger (G/L) data is imported or exported.

### Audit file export document for SIE

The **Audit File Export Document** page includes a few fields that are specific to SIE. You must set these fields before you begin.

- On the **SIE** FastTab, in the **File type** field, select one of the following values to specify the type of SIE file to create:

    - Year - End Balances
    - Periodic Balances
    - Object Balances
    - Transactions

    All other fields are set by default, based on your previous setup.

## See also

[Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)  
[Sweden Local Functionality](sweden-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
