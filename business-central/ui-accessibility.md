---
title: Assistive features
description: Keyboard shortcuts and other assistive features.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 11/26/2020
ms.author: edupont

---
# Accessibility and Keyboard Shortcuts

This topic provides information about the features that make [!INCLUDE[prod_short](includes/prod_short.md)] readily available to people with disabilities. [!INCLUDE[prod_short](includes/prod_short.md)] supports the following accessibility features:  

- Keyboard shortcuts

    For more information, see [Keyboard Shortcuts](keyboard-shortcuts.md)

- Navigation  

- Headings  

- Alternative text for images and links  

- Support for common assistive technologies  

- Use keyboard shortcuts to zoom in or out on any page

<!-- moved to separate article
##  <a name="Keyboard"></a> Keyboard Shortcuts in the browser
 [!INCLUDE[prod_short](includes/prod_short.md)] supports the keyboard shortcuts that are supported by most web browsers. The keyboard shortcuts described here refer to the U.S. keyboard layout. The layout of the keys on other keyboards may not correspond exactly to the keys on a U.S. keyboard.  

|To do this|Press|  
|----------------|-----------|  
|To move focus to the next or previous control or element on a page, such as buttons, fields, or items in a list.|Tab, Shift+Tab|  
|To enable or access the element or control that is in focus.|Enter|  
|To scroll items up and down in a list.|Up Arrow, Down Arrow|  
|To scroll columns of an item left and right in a list.|Left Arrow, Right Arrow|  
|To open a drop-down list or look up a value for a field.|Alt+Down Arrow|  
|To move focus to the next element outside the list.|Ctrl + Enter|  
|To see the transactions that resulted in a calculated value in a field.|Alt+Right Arrow|  

-->

## <a name="Navigation"></a> Navigation  
 You can navigate between the tabs and actions in the ribbon, elements in the navigation bar, and other controls on [!INCLUDE[prod_short](includes/prod_short.md)] pages and reports using the keyboard. To move the focus from one tab, action, or control to another, press the Tab key to move forward. Press Shift+Tab to move backward.  

 By using the tab order, you can also switch between the main browser page and dialog boxes that request confirmation, for example, or the login page.  

## <a name="Headings"></a> Headings in Content
 
 The HTML source for [!INCLUDE[prod_short](includes/prod_short.md)] content uses tags to help users of assistive technology to understand the structure and content of the page. For example, on list pages, the columns are defined in TH tags and the column headings are set with TITLE attribute inside the tag. Captions for elements, such as FastTabs, FactBoxes, and fields are included in heading tags (H1, H2, H3, and H4).  

## <a name="Images"></a> Image and Links

 A descriptive text for images is set with the ALT attribute inside the IMG tag. A descriptive text for hyperlinks is set with the title attribute inside the A tag.  

## <a name="AssistiveTech"></a> Assistive Technologies

[!INCLUDE[prod_short](includes/prod_short.md)] supports various assistive technologies, such as high contrast, screen readers, and voice recognition software. Some assistive technologies may not work well with certain elements in [!INCLUDE[prod_short](includes/prod_short.md)] pages.  

## <a name="zoom"></a> Zoom

Most browsers use standard keyboard shortcuts to zoom in and out on the current page. These keyboard shortcuts are not specific to [!INCLUDE [prod_short](includes/prod_short.md)], but they work when you use [!INCLUDE [prod_short](includes/prod_short.md)] in a browser. For a list of supported keyboard shortcuts, see [Keyboard Shortcuts for Zooming In and Out](keyboard-shortcuts.md#zoomshortcuts).  

## For more accessibility information

You can find additional information about accessibility with Microsoft products and assistive technologies on the [Microsoft Accessibility](https://go.microsoft.com/fwlink/?LinkId=262160) site.

## See Also

[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Frequently Asked Questions](across-faq.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]