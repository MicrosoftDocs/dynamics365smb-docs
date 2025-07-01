---
title: Import and export data in the standard import export (SIE) format
description: This article explains how to import and export general ledger data according to the standard import export (SIE) format for Sweden.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: import data, export data, SIE, standard import export, audit files export
ms.search.form: 5264, 5266, 5267, 5270, 5315
ms.date: 02/07/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Import and export data in the standard import export (SIE) format

You can import and export general ledger data according to the standard import export (SIE) format. By specifying SIE dimensions and file types, you can define the level of detail that's covered by import or export transactions. Learn more about Standard Import Export Group [here](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).

> [!NOTE]
> SIE Audit Files Export is part of the Swedish localization. However, as of version 22.1, the Swedish localization is based on the W1 base app, and the SIE functionality has been moved to the extension that's installed by default. This functionality is based on the Audit Files Export app that has the preinstalled SIE format. Learn more about Audit Files Export [here](../../finance-how-to-export-audit-files.md).

Even if the feature is preinstalled, it isn't enabled by default. To enable the feature, follow these steps.

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, go to the **Feature Management** workspace, and then select the related link.
1. Find the **Feature update: Enable using SIE Audit Files Exports** feature. Then, in the **Enabled for** column, select **All users**.

## Audit files export

When you enable **SIE Audit Files Export** in Feature Management, you're guided through a wizard to set up the feature. However, you can set up the feature later by running the **SIE Audit File Export Setup Guide** page. If you want to manually set up the system, follow the steps in the [Audit files export](../../finance-how-to-export-audit-files.md) article.

### Set up SIE dimensions

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dimensions SIE**, and then select the related link.
1. In the **Dimension Code** field, select one of the standard dimensions that you want to map.
1. In the **SIE Dimension** field, specify the number that you want to assign to the dimension.
1. In the **Selected** field, specify whether the dimension should be used when General ledger (G/L) data is imported or exported.

### Audit file export document for SIE

The **Audit File Export Document** page includes a few fields that are specific to SIE. You must set these fields before you begin.

- On the **SIE** FastTab, in the **File type** field, select one of the following values to specify the type of SIE file to create:

   - Year - End Balances
   - Periodic Balances
   - Object Balances
   - Transactions

    All other fields are set by default, based on your previous setup.

## See also

- [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)  
- [Sweden Local Functionality](sweden-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
