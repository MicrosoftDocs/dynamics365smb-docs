---
title: 'Image Analysis| Microsoft Docs'
description: Analyze images of contacts and items to recognize and assign attributes.
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
The Image Analysis extension uses powerful image analytics provided by the Computer Vision API for Microsoft Cognitive Services to detect certain attributes in the images that you attach to items and contacts, and assign them in [!INCLUDE[d365fin](includes/d365fin_md.md)]: 
  
* Contact persons: Recognize a person's gender, or age  
* Items: Identify the type of item, and it's color. For example, whether it't a table or a car, or red or blue.  
  
Image Analysis assigns attributes based on a confidence level, that is, it will assign attributes only if there's at least an 80% chance that the attribute is correct. If you need the attributes to be 100% exact, you can verify and adjust them yourself. To learn more about how the confidence level is determined, see the documentation for the [Computer Vision API](https://azure.microsoft.com/en-us/services/cognitive-services/computer-vision/). 

<!-- What is the actual confidence level? -->

Image Analysis is free in [!INCLUDE[d365fin](includes/d365fin_md.md)], but there is a limit to the number of items that you can upload during a certain period of time.

<!-- What's the period of time? -->

For contacts, Image Analysis is part of a questionnaire. 

## Requirements
There are a few requirements for the images:

* Image formats: JPEG, PNG, GIF, BMP
* Maximum file size: Less than 4 MB
* Image dimensions: Greater than 50 x 50 pixels

<!-- The requirements are copied from the Computer Vision API documentation. Do we have additional requirements? -->

## To set up Image Analysis
The Image Analysis extension is built-in to [!INCLUDE[d365fin](includes/d365fin_md.md)]. You just need to turn it on.

1. In the top right corner, choose the **Search for Page or Report** icon, enter ****, and then choose the related link.

## To analyze an image of a contact or item
After you turn on Image Analysis, you can start analyzing images right away.

1. In the top right corner, choose the **Search for Page or Report** icon, enter ****, and then choose the related link.

<!-- Do we start analyzing automatically, or do they need to open a card and click a button? -->

## See Also
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Welcome to [!INCLUDE[d365fin](includes/d365fin_md.md)]](index.md)
[Creating Contact Persons](marketing-how-create-contact-persons.md)