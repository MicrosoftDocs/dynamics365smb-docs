---
title: Czech local functionality - Posting groups in transfer orders
description: The Transfer Orders feature includes fields for specifying General Business Posting Groups for both shipping and receiving postings.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: concept-article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Posting groups in transfer orders in the Czech version

Czech posting rules require location transfers to post with an **Inventory Adjmt. Account** that's different from other item journal postings.

The transfer order functionality includes **Gen. Bus. Post. Group Ship** and **Gen. Bus. Post. Group Receive** fields, so you can post transfer orders with a different general posting setup than the one used for item journal postings.

The **Transfer Route** page also includes **Gen. Bus. Post. Group Ship** and **Gen. Bus. Post. Group Receive** fields. This setup is automatically copied to a transfer order based on the transfer route it uses.

For direct transfers, you can also set a default posting group. On the **Inventory Setup** page, enter a value in the **Default Gen. Bus. Posting Group for Direct Transfer** field, and it's used automatically whenever a direct transfer order is created.

## Related information

- [Advanced Localization Pack for Czech](ui-extensions-advanced-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
