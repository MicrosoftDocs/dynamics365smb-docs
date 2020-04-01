---
title: Fields Required to Complete Processes | Microsoft Docs
description: Learn about fields marked with a red asterisk, which indicates that they are required and must be filled in to complete a processes.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2020
ms.author: solsen

---
# Detecting Mandatory Fields
When you enter data on pages in [!INCLUDE[d365fin](includes/d365fin_md.md)], certain fields are marked with a red asterisk. The red asterisk means that the field must be filled to complete a certain process that uses the field, such as posting a transaction that uses the value in the field.

Even though the field contains a red asterisk, you are not forced to fill in the field before you continue to other fields or close the page. The red asterisk only serves as a reminder that you will be blocked from completing a certain process.

## Examples
On the **Customer Card** page, the red asterisk appears in the **Name** field, in the **Tax Area Code** field, and in the posting group fields to indicate that you cannot post a sales transaction for the customer unless the fields are filled.

On the **Item Card** page, the red asterisk appears in the **Description** field to indicate that you cannot enter the item on a document line, such as a sales order, unless this field is filled.

## See Also
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
