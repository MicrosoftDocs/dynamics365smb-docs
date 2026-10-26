---
title: Import Post Code Updates in the Dutch Version [NL]
description: Import monthly Dutch post code updates in Business Central, check the update period, and review the import log for changes to the post code ranges.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: import post code file, post code file, Dutch version, Netherlands, post code range table, post code import, post code update
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import post code updates in the Dutch version

Every month, a post code file is delivered with all post code mutations for that month. This post code file can be imported to update the relevant data of the **Post Code Range** table.  

## Import the update file  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Post Code Updates**, and then choose the related link.
1. On the **Post Code Updates** page, choose **Import Post Codes Update**.
1. If no full post code data set has been imported, review the warning and decide whether to continue.
1. Select the monthly post code update file in the supported text format.
1. If a warning identifies skipped periods, review it before you confirm that you want to continue.

If no full post code data set has been imported, a warning asks whether you want to continue.

Before you update the post codes, the following checks are performed:  

- An update for the same or an earlier period than the last imported period is rejected.
- If monthly updates are missing between the last imported period and the new file, a warning asks whether you want to continue. If you continue, you can't import those skipped updates afterward.

The **Post Code Updates** page shows the imported **Period**, **Date**, **Time**, and **User ID**. These values are saved in the **Post Code Update Log Entry** table.

## Related information

[Dutch Post Codes](dutch-post-codes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
