---
title: Deferrals in Sales Ledger and Purchase Ledger reports [BE]
description: This topic tells you how to set up and use deferrals in Sales Ledger and Purchase Ledger reports in Belgian version of Business Central.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: deferral, sales ledger, purchase ledger
ms.search.form: 279, 1700, 1701
ms.date: 03/10/2023
ms.author: altotovi

---

# Deferrals in Belgium Sales Ledger and Purchase Ledger reports

When user uses deferrals, the purchase ledger and sales ledger reports in Belgian version of Business Central need to show only original entries from invoices and credit memos, without entries created from usage of deferrals.

## To make a set up  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Source Code Setup**, and then choose the related link.  
2. Fill in the fields in the General FastTabb, including the fields that are described in the following table.  

    |Field|Description|
    |--------------|----------------------------|
    |**General Deferral**|Specifies the **Source Code** system will use for deferrals created from posting in General Journals.|
    |**Sales Deferral**|Specifies the **Source Code** system will use for deferrals created from posting in Sales Document.|
    |**Purchase Deferral**|Specifies the **Source Code** system will use for deferrals created from posting in Purchase Documents.|
    
3. Choose the **OK** button.  

> [!NOTE]
> User can configure specific source codes for deferrals postings, but is also able to use the same source codes used for general journal, sales journals, purchase journals.  

## Belgium Sales Ledger and Purchase Ledger reports

Once the deferral entries have specific** Source Code** it is possible to manipulate the reports’ view with the option **Exclude Deferral Entries** in both Sales Ledger and Purchase Ledger reports. 

When the option is set to **Off** the user will see the report prints all the entries related to specified period, but when switch is **On** the user will get deferral entries excluded from the report.  

> [!NOTE]
> Next period for one month does not include deferral entries when the switch in **On**.

## See Also

[Belgium Local Functionality](belgium-local-functionality.md)
[Make Journal Templates Mandatory](specify-journal-template-mandatory.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
