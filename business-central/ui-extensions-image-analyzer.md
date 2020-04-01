---
title: Using the Image Analyzer Extension | Microsoft Docs
description: This extensions lets you analyze images of contact persons and items to find attributes, so you can quickly assign them in Business Central.
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: API, extension, Cognitive Services, image, computer vision, attribute, tag, recognition
ms.date: 04/01/2020
ms.author: bholtorf

---

# The Image Analyzer Extension
The Image Analyzer extension uses powerful image analytics provided by the Computer Vision API for Microsoft Cognitive Services to detect attributes in the images that you import for items and contact persons, so you can easily review and assign them. For items, attributes could be whether the item is a table or a car, and whether it is red or blue. For contact persons, attributes can be gender or age.

Image Analyzer suggests attributes based on tags that the Computer Vision API finds, and a confidence level. By default, it suggests attributes only if it is at least 80% sure that the attribute is correct. You can set another confidence level, if needed. To learn more about how the tags and confidence level are determined, see [Computer Vision API](https://go.microsoft.com/fwlink/?linkid=851476).  

Image Analyzer is free in [!INCLUDE[d365fin](includes/d365fin_md.md)], but there is a limit to the number of items that you can analyze during a certain period of time. By default, you can analyze 100 images per month.

After you enable the extension, Image Analyzer runs each time you import an image to an item or contact person. You will see the attributes, confidence level, and details right away, and can decide what to do with each attribute. If you imported images before you enabled the Image Analyzer extension, you must go to the item or contact cards and choose the **Analyze Picture** action.  

## Privacy Notice
This extension uses the Computer Vision API from Microsoft Cognitive Services, which may have varying levels of compliance commitments than [!INCLUDE[d365fin](includes/d365fin_md.md)]. When you enable the Image Analyzer extension, Customer Data such as a contact image or an item image will be sent to the Computer Vision API. By installing this extension you agree for this limited set of data to be sent to the Computer Vision API. Note that you may disable, as well as uninstall, the Image Analyzer extension at any time to discontinue use of this functionality. For more information, see [Microsoft Trust Center](https://go.microsoft.com/fwlink/?linkid=851463).

## Requirements
There are a few requirements for the images:

* Image formats: JPEG, PNG, GIF, BMP  
* Maximum file size: Less than 4 MB  
* Image dimensions: Greater than 50 x 50 pixels  

## To enable Image Analyzer
The Image Analyzer extension is built-in to [!INCLUDE[d365fin](includes/d365fin_md.md)]. You just need to turn it on.

> [!NOTE]  
> To enable the Image Analyzer extension, you must be an administrator. Make sure that you are assigned the **SUPER** user permission set.

1. To enable the Image Analyzer extension, do one of the following:

* Open an item or contact card. In the notification bar, choose **Analyze Images**, and then follow the steps in the assisted setup guide.  
* Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Connections**, and then choose **Image Analysis Setup**. Choose the **Enable Image Analyzer** check box, and then complete the steps in the assisted setup guide.  

    > [!TIP]  
    > The **Image Analysis Setup** page is also where you can change the degree of confidence for attribute suggestions. For example, if you want to require a greater degree of confidence, you can enter a higher percentage.

## To analyze an image of an item
The following steps describe how to analyze an image that was imported before you enabled the Image Analyzer extension.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Choose the item, and then choose the **Analyze Picture** action.  
3. The **Image Analyzer Attributes** page displays the detected attributes, the confidence level, and other details about the attribute. Use the **Action to perform** options to specify what to do with the attribute.  

    > [!TIP]  
    > You can add the name of the attribute to the item description by choosing **Add to item description**. For example, this can be useful for quickly adding detail.  

## To analyze a picture of a contact person
The following steps describe how to analyze an image that was imported before you enabled the Image Analyzer extension.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.  
2. Choose the contact person, and then choose the **Analyze Picture** action.  
3. On the **Profile Questionnaire** FastTab, review the suggestions, and make corrections if needed.  

## Blacklisting suggested attributes
If the analysis suggests an attribute that you do not want to see you can blacklist the attribute. Use caution, however. Blacklisted attributes are not suggested for other items or contact persons either. If you regret blacklisting an attribute, you can choose **Blacklisted Attributes**, and then delete the attribute from the list.

## To use your own account for the Computer Vision API
You can also use your own account for the Computer Vision API, for example, if you want to analyze more images than we allow.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Image Analyzer Setup**, and then choose the related link.  
2. Enter the **API URI** and **API Key** that you received for Computer Vision API.  

    > [!NOTE]  
    > You must add **/analyze** at the end of the API URI, if it isn't already there. For example: ```https://cronus.api.cognitive.microsoft.com/vision/v1.0/analyze```.

## To see how many analyses you have left in the current period
You can view the number of analyses you've done, and how many you can still do, in the current period.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Image Analyzer Setup**, and then choose the related link.  
2. The **Limit type**, **Limit value**, and **Analyzes performed** provide the usage information.  

## To stop using the Image Analyzer extension
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Connections**, and then choose **Image Analyzer Setup**.  
2. Clear the **Enable Image Analyzer** check box.  

## See Also
[Work with Item Attributes](inventory-how-work-item-attributes.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Getting Started](product-get-started.md)  
