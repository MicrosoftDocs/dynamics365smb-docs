---
title: Czech Local Functionality - Inventory Movement Templates
description: Learn about Inventory Movement Templates in the Czech version of Business Central, including how to define custom templates for posting inventory movements.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Inventory, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Inventory movement templates in the Czech version

Movements of items from item journals must post with the **Inventory Adjmt. Account** that corresponds to the given type of movement.

## Define custom templates for posting inventory movements

Within a template, you can set the type of transaction (**Positive Adjmt.**, **Negative Adjmt.**, **Transfer**, and so on) and the **Gen. Bus. Posting Group** that defines the inventory adjustment account.
These settings are automatically copied to the item journal line based on the selected inventory movement template.

You can use inventory movement templates to post movements in the item journal and job journal. They're also used to post differences found during physical inventory counting.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
