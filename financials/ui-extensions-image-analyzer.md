---
title: Using the Image Analyzer Extension | Microsoft Docs
description: This extensions lets you analyze images of contact persons and items to find attributes, so you can quickly assign them in Financials.
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: API, extension, Cognitive Services, image, computer vision, attribute, tag, recognition
ms.date: 05/22/2017
ms.author: bholtorf

---

# The Image Analyzer Extension for Microsoft Dynamics 365 for Financials
The Image Analyzer extension uses powerful image analytics provided by the Computer Vision API for Microsoft Cognitive Services to detect attributes in the images that you add to items and contact persons, so you can easily review and assign them. 
  
* Contact persons: Recognize a person's gender, or age  
* Items: Identify attributes like type and color. For example, whether it's a table or a car, or red or blue.  
  
Image Analyzer suggests attributes based tags that the Computer Vision API finds, and a confidence level. By default, it suggests attributes only if it's at least an 80% sure that the attribute is correct. If you need the attributes to be 100% exact, you can verify and adjust them yourself. To learn more about how the tags and confidence level are determined, see [Computer Vision API](https://azure.microsoft.com/en-us/services/cognitive-services/computer-vision/). 

Image Analyzer is free in [!INCLUDE[d365fin](includes/d365fin_md.md)], but there is a limit to the number of items that you can upload during a certain period of time. By default, you can analyze 100 images per month.

After you enable the extension, Image Analyzer kicks in each time you add an image to an item or contact person. You'll see the attributes, confidence level, and details right away, and can decide what to do with each attribute. If you added images before you enabled the Image Analyzer extension, you'll need to go to the item or contact person cards and choose the **Analyze Picture** action.   

## Requirements
There are a few requirements for the images:

* Image formats: JPEG, PNG, GIF, BMP
* Maximum file size: Less than 4 MB
* Image dimensions: Greater than 50 x 50 pixels

## To enable Image Analyzer
The Image Analyzer extension is built-in to [!INCLUDE[d365fin](includes/d365fin_md.md)]. You just need to turn it on.

1. To enable the Image Analyzer extension, do one of the following:
  
* Go to an item card or contact card. In the notification bar, choose **Analyze Images**, and then follow the steps in the assisted setup guide.  
* In the top right corner, choose the **Search for Page or Report** icon, enter **Service Connections**, and then choose **Image Analysis Setup**. Choose the **Enable Image Analyzer** check box, and then complete the steps in the assisted setup guide.  

## To analyze an image of an item
The following steps describe how to analyze an image that was uploaded before you enabled the Image Analyzer extension.  

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Items**, and then choose the related link.  
2. Choose the item, and then choose the **Analyze Picture** action.  
3. The **Image Analyzer Attributes** page displays the detected attributes, the confidence level, and other details about the attribute. Use the **Action to perform** options to specify what to do with the attribute.  

> [!TIP]  
>   You can add the name of the attribute to the item description by choosing **Add to item description**. For example, this can be useful for quickly adding detail. 

## To analyze a picture of a contact person
The following steps describe how to analyze an image that was uploaded before you enabled the Image Analyzer extension.  

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Contacts**, and then choose the related link.  
2. Choose the contact person, and then choose the **Analyze Picture** action.  
3. Review the suggestions, and make corrections if needed.  

## Tips for deciding what to do with a suggested attribute
 
If the analysis suggests an attribute that you don't want to see you can blacklist it. Use caution, however. Blacklisted attributes are not suggested for other items either. If you regret blacklisting an attribute, you can choose **Blacklisted Attributes**, and then delete the attribute from the list. 

## Using your own account for the Computer Vision API
You can also use your own account for the Computer Vision API, for example, if you want to analyze more images than we allow.  
  
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Image Analyzer Setup**, and then choose the related link.  
2. Enter the **API URI** and **API Key** that you received for Computer Vision API.  
  
    > [!NOTE]  
>   You must add **/analyze** at the end of the API URI, if it isn't already there. Here's an example: <https://cronus.api.cognitive.microsoft.com/vision/v1.0/analyze>.

## To see how many analyses you have left in the current period
You can view the number of analyses you've done, and how many you can still do, in the current period.  
  
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Image Analyzer Setup**, and then choose the related link.  
2. The **Limit type**, **Limit value**, and **Analyzes performed** provide the usage information.  

## To stop using the Image Analyzer extension
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Service Connections**, and then choose **Image Analyzer Setup**.  
2. Clear the **Enable Image Analyzer** check box.  

## See Also
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Welcome to [!INCLUDE[d365fin](includes/d365fin_md.md)]](index.md)
[Creating Contact Persons](marketing-how-create-contact-persons.md)