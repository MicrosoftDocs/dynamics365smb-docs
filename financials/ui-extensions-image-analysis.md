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
ms.search.keywords: API, extension, Cognitive Services, image, computer vision, attribute, tag, recognition
ms.date: 05/11/2017
ms.author: bholtorf

---

# The Image Analysis Extension for Microsoft Dynamics 365 for Financials
The Image Analysis extension uses powerful image analytics provided by the Computer Vision API to detect certain attributes in the images that you attach to items and contacts, and assign them: 
  
* Contacts: Recognize the person's gender, or age  
* Items: Identify the type of item, and it's color. For example, whether it't a table or chair, or red or blue.  
  
Image Analysis looks for the attributes you've set up in Financials, and suggests them based on a confidence level, that is, only if there's at least an 80% chance that it's correct. The attributes that the analysis suggets are estimates. Image Analysis suggests attributes based on a confidence level. For example, we need to be at least 80% sure that the attribute is correct. If you need the attributes to be exact, you can verify and adjust the results yourself. 

<!-- What is the actual confidence level? -->

The API is free, and you just need to turn it on in [!INCLUDE[d365fin](includes/d365fin_md.md)]. There is, however, a limit to the number of items that you can upload during a certain period of time.

## Requirements

* Image formats: JPEG, PNG, GIF, BMP
* Max. file size: Less than 4 number
* Image dimensions: Greater than 50 x 50 pixels

<!-- The requirements are copied from the Computer Vision API documentation. Do we have additional requirements? -->

## See Also
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Welcome to [!INCLUDE[d365fin](includes/d365fin_md.md)]](index.md)