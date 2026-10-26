---
title: Create an Audit File for the Dutch Tax Authority
description: Create a Dutch tax authority audit file from general ledger transactions in Business Central, and choose the reporting dates and opening balance options.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: audit file, Dutch version, Netherlands, tax authority, create audit file, basis transactions
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create an audit file for the tax authority in the Dutch version

During an examination of the books for a fiscal year, a tax inspector can ask for data about the basis transactions from the general ledger for that fiscal year. Basis transactions usually are processed via journal entries. That is the reason why the journal entries are the basis for the audit file.  

The tax authority stimulates companies to use the audit file but it isn't prescribed.  

The audit file can also be used to exchange data between companies. The start and end dates must be in the same fiscal year. The start date can't be after the end date, and the end date can't be later than today.

## Create an audit file  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Tax Authority - Audit File**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Start Date**|Specify the start date of the period on which the data must be based.|  
    |**End Date**|Specify the end date of the period on which the data must be based.|  
    |**Exclude Begin Balance**|Select to leave the opening balances of general ledger accounts out of the audit file. This option is available only when the start date is the first day of a fiscal year.|

1. Choose the **OK** button to create the audit file. If you don't want to create the audit file, choose the **Cancel** button to close the page.  

When you run the report, you must specify the name and location of the exported file. The default file name is **audit.xaf**, but you can change that. The file extension must be *.xaf*.  

## Related information

[Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
