---
title: Accessibility and Keyboard Shortcuts
description: This article provides information about keyboard shortcuts and other assistive features in Business Central for people with disabilities.
author: jswymer

ms.topic: article
ms.devlang: al
ms.search.keywords: accessibility, shortcuts, charts, tooltips, screen reader
ms.search.form: 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
ms.date: 06/23/2021
ms.author: jswymer

ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# Accessibility and keyboard shortcuts

This article provides information about the features that make [!INCLUDE[prod_short](includes/prod_short.md)] readily available to people with disabilities. [!INCLUDE[prod_short](includes/prod_short.md)] supports the following accessibility features:  

- Keyboard shortcuts. See [Keyboard Shortcuts](keyboard-shortcuts.md).
- Touch and pen gestures on tablets and phones. See [Touch and Pen Gestures](touch-gestures.md).
- Navigation  
- Headings  
- Alternative text for images and links  
- Support for common assistive technologies 
- Zoom in or out on any page
- Tooltips on elements in the user interface

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## <a name="Navigation"></a> Navigation
  
You can use different combinations of the Tab, Shift, and arrow keys of your keyboard to move between elements on a page. Elements include actions, fields and columns, parts, and other controls. In general, select <kbd>Tab</kbd> or <kbd>Shift</kbd>+<kbd>Tab</kbd> to move to the next or previous element.

When you focus on an area that contains actions, like the navigation bar on the top of role center or action bar on other pages, use the arrows keys to move through the different actions and groups. Select <kbd>Enter</kbd> on a group to open its underlying actions, and then continue using the arrows keys. Select <kbd>Tab</kbd> or <kbd>Shift</kbd>+<kbd>Tab</kbd> to move out of the action area.

By using the tab order, you can also switch between the main browser page and dialog boxes that request confirmation, for example, or the sign-in page.  

## <a name="Headings"></a> Headings in content

The web client uses semantic markup and accessibility attributes to help assistive technologies identify page structure and controls. The exact HTML elements vary by control. For example, a list can use accessibility roles rather than HTML table tags.

## <a name="Images"></a> Images and links

Images and links can provide descriptive text through text alternatives and accessible names. Icons can also be rendered without an HTML image element. Decorative icons can be hidden from assistive technologies.

## <a name="AssistiveTech"></a> Assistive technologies

[!INCLUDE[prod_short](includes/prod_short.md)] supports various assistive technologies, such as high contrast, screen readers, and voice recognition software. Some assistive technologies may not work well with certain elements in [!INCLUDE[prod_short](includes/prod_short.md)] pages.  

## <a name="zoom"></a> Zoom

Most browsers use standard keyboard shortcuts to zoom in and out on the current page. These keyboard shortcuts aren't specific to [!INCLUDE [prod_short](includes/prod_short.md)], but they work when you use [!INCLUDE [prod_short](includes/prod_short.md)] in a browser. For a list of supported keyboard shortcuts, see [Keyboard Shortcuts for Zooming In and Out](keyboard-shortcuts.md#zoomshortcuts).

## Tooltips

Tooltips are available on most elements in the user interface, like page fields and columns, actions, cues tiles, and charts. A tooltip provides extra text that explains an element to help you better understand its purpose. 

Tooltips are accessed in different ways, depending on the client (web or mobile) and the device that you're working with. Use the following table as a guide. Some tooltips can be read by screen-readers. In this case, you access the tooltips as described in the table, then use the screen reader to navigate to the tooltip as you would with any other element.

### Access tooltips

|Element|Mouse action for web client|Keyboard shortcut for web client|Touch gesture on tablet/phone for mobile app|Screen reader support|
|-------|-----------------|------------|--------------------------|---------------------|
|Page fields and column headings|Hover over or click the field caption or column heading|Move focus to the field or column heading, and select <kbd>Alt</kbd>+<kbd>Up Arrow</kbd> keys|Tap the field caption |yes|
|Charts elements, like a bar, line, pie slice|Hover over the element|Move focus to element, for example, by using arrow keys|Tap and hold the element|yes|
|Actions|Hover over the action|none|none |no|
|Cue tiles|Hover over the tile |none|none|no|


<!--
- With a mouse, hover over the element.
- With keyboard, press the Alt+Up Arrow keys.
- On a tablet or phone, tap and hold on the element. To learn about more gestures, see [Touch and Pen Gestures](touch-gestures.md)

-->

## For more accessibility information

You can find additional information about accessibility with Microsoft products and assistive technologies on the [Microsoft Accessibility](https://go.microsoft.com/fwlink/?LinkId=262160) site.

## Related information

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Frequently Asked Questions](across-faq.yml)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
