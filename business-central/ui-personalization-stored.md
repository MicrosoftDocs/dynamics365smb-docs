---
title: Where is personalization stored?
description: Learn which UI adjustments are automatically saved and roam with you across devices and browsers, while others only affect your current browser.
author: mikebc
ms.author: mikebc
ms.reviewer: jswymer
ms.topic: concept-article
ms.custom: bap-template 
ms.date: 02/14/2025
---
# Where is personalization stored?

When you interact with the Business Central web client to optimize your workspace, some user interface (UI) adjustments are automatically saved and roam with you across devices and browsers. Others are local and only affect your current browser.

- *Roaming personalization* is stored in the Business Central service and affects your experience no matter which device or browser you sign in to. Personalizing in one browser or device immediately affects other browsers or devices that you use. Roaming personalization is typically infrequent, more permanent, or time-consuming to recreate. Roaming settings can only be reset by clearing personalization from the Business Central web client.
- *Local personalization* is stored in your browser and only affects your experience when using different browser tabs in that same browser. It doesn't affect your Business Central experience on other devices, browsers, or browser profiles. UI adjustments that are saved locally are typically those adjustments that users frequently do and redo as they work in Business Central.  

  > [!NOTE]
  > If you delete the browsing data in your browser, specifically cookies and site data, you also delete any local personalization that you've done. To avoid deleting local personalization, make sure that the browser isn't set up to clear cookies and site data every time you close the browser. For example, in Microsoft Edge, you turn off the **Cookies and other site data** toggle in the **Privacy, search, and services** settings. Learn more at [Manage cookies in Microsoft Edge](https://support.microsoft.com/windows/manage-cookies-in-microsoft-edge-view-allow-block-delete-and-use-168dab11-0753-043d-7c16-ede5947fc64d#bkmk_deletecookieseverytimeyouclosethebrowser) or consult the documentation for your browser.

## Roaming versus local UI adjustments

The following table indicates which UI adjustments are roaming, local, or both. An \* indicates that the roaming personalization can be made without entering the personalization mode.  

|UI element|Options|Roaming|Local|
|-|-|:-:|:-:|
|Fields|Reorder or move to another group|X||
||Hide or show|X||
||Add or remove|X||
||Lock or unlock editing|X||
||Exclude or include in Quick Entry|X||
||Show when collapsed or show under **Show more**|X||
|Columns|Hide or show|X||
||Reorder |X||
||Resize|X*|X|
||Set freeze pane|X||
||Lock or unlock editing |X||
||Exclude or include in Quick Entry|X||
|List views|Add* or remove*|X||
||Hide or show|X*||
||Reorder|X*||
||Rename|X*||
|Cue tiles|Move|X||
||Hide|X||
|Role Center parts|Move|X||
||Hide or show|X||
|Actions|Move|X||
||Hide or show|X||
|Action bar|Hide or show|X||
||Pin or unpin||X|
||Show as menu or as action bar||X|
|Navigation menu|Hide or show link|X||
||Reorder or move to another group|X||
||Pin or unpin||X|
|Lists|Display as rows or tiles||X|
||Show or hide filter pane||X|
||Display in analysis mode||X|
|Hierarchical lists|Expand or collapse hierarchy|X*||
|Page|Show as wide or narrow||X|
||Bookmark the page|X*||
|Other UI|Collapse or expand field section||X|
||Resize, collapse, or expand FactBox pane||X|
||Show FactBox pane attachments or details||X|
||Resize, collapse, or expand Copilot, Help, and Page Scripting panes||X|
||Collapse or expand page inspection pane||X|
||Collapse or expand part on a page||X|
||Show or hide teaching tips|X||

## Related information

[Personalize your workspace](ui-personalization-user.md)  
[Why a Page is Locked from Personalization](ui-personalization-locked.md)  
