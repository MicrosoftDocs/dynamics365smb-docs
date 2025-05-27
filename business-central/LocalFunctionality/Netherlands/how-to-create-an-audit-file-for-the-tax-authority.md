---
title: Create an Audit File for Tax Authority [NL]
description: Learn how to create an audit file for the tax authority with the Dutch version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: audit file, Dutch version, Netherlands, tax authority, create audit file, basis transactions
ms.date: 03/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create an audit file for the tax authority in the Dutch version

During an examination of the books for a fiscal year, a tax inspector can ask for data about the basis transactions from the general ledger for that fiscal year. Basis transactions usually are processed via journal entries. That is the reason why the journal entries are the basis for the audit file.  

The tax authority stimulates companies to use the audit file but it isn't prescribed.  

The audit file can also be used to exchange data between companies. You can select every period you want, but the start and end date of the entered period must be in the same fiscal year.  

## Create an audit file  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Authority - Audit File**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Start Date**|Specify the start date of the period on which the data must be based.|  
    |**End Date**|Specify the end date of the period on which the data must be based.|  
    |**Exclude Begin Balance**|Specifies if the audit file must contain the begin balance of general ledger accounts.<br><br/> The field is editable if the start date of the period is equal to the start date of a fiscal year.|  

1. Choose the **OK** button to create the audit file. If you don't want to create the audit file, choose the **Cancel** button to close the page.  

When you run the report, you must specify the name and location of the exported file. The default file name is **audit.xaf**, but you can change that. The file extension must be *.xaf*.  

## Related information

[Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
