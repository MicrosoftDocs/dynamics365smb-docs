---
title: 'Image Analysis| Microsoft Docs'
description: Provides information about the Image Analysis extension.
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: API, extension, Cognitive Services, image
ms.date: 05/11/2017
ms.author: bholtorf

---

# The Image Analysis Extension for Microsoft Dynamics 365 for Financials
The Image Analysis extension uses the Computer Vision API from Microsoft Cognitive Services to let you analyze the images that you attach to items and contacts in Financials to detect a few attributes. 

* For contancts, the analysis can detect things like the person's gender, or their age. 
* For items, the analysis will identify the type of item, and it's color.

You set up the attributes, and if we detect these, and ten assign them to the item for you.

We'll suggest attribujtes based on a confidence level, that is, for example, only if we're at least 80% sure that we've spotted an attribute. However, we let you decide whether we've gotten it right.

The attributes that the analysis suggets are estimates. Image Analysis suggests attributes based on a confidence level. For example, we need to be at least 80% sure that the attribute is correct. If you need the attributes to be exact, you can verify and adjust the results yourself. 

The API is free, and you just need to turn it on in Financials. There is, however, a limit to the number of items that you can upload during a certain period of time.

## See Also