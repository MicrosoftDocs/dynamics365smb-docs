---
title: Specify the Layout of a Check| Microsoft Docs
description: You can design and print your checks in different formats to conform with standards.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: print check, customize
ms.date: 10/01/2019
ms.author: edupont

---
# Select a Check Layout
You can design your checks to conform with the standards set by the local authorities. Check images can be printed in English, French, or Spanish.

Checks are designed to print in both the United States and Canadian check image formats in either a check-stub-check format or a stub-stub-check format.

## To select a check layout
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selections Bank Account**, and then choose the related link.
2. On the **Report Selection - Bank Acc.** page, in the **Usage** field, select **Check**.
3. Select one of the following report IDs.

| Report ID | Report Name | Description |
| --- | --- | --- |
| 1401 |Check |This is the default report. |
| 10411 |Check (Stub/Stub/Check) |This report is designed to print checks in a stub/stub/check format. |
| 10412 |Check (Stub/Check/Stub) |This report is designed to print checks in a stub/check/stub format. |
| 10413 |Three Checks per Page |This report is designed to print three checks on each page. |

When you have set up check layouts, you can print checks from the **Payment Journal** page. For more information, see [Work with Checks](payables-how-work-checks.md).

To change one of these default check layouts, use either the Word or the RDLC integration to do so. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

## See Also
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Managing Payables](payables-manage-payables.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)   
[Completing Period-End Processes](year-how-complete-period-end-processes.md)  
[Working with [!INCLUDE[prodshort](includes/prodshort.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)
