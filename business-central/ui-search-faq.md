---
title: Frequently Asked Questions about Tell Me | Microsoft Docs
description: This article provides answers to questions that our partners and customers often ask about Tell Me.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: find
ms.date: 04/01/2020
ms.author: bholtorf

---
# Tell Me FAQ
This topic answers questions that our advanced users often ask about the Tell Me feature.

### Are all actions from my current page discoverable in Tell Me?
No. Actions in parts, such as the Sales Lines part or FactBoxes, are not displayed in Tell Me.

### Are the results in Tell Me filtered by permissions?
If the user does not have AccessByPermissions then actions are not displayed. However, pages and reports appear in the results but require that the user has permission to access them. A message will display if the user does not have permission to view the object.

### Does Tell Me display content from my customizations or installed third-party extensions?
Actions, pages, and reports that originate from extensions are picked up by Tell Me, but custom help documentation is not. For technical information about how to make custom pages and reports discoverable, see [Adding Pages and Reports to Search](/dynamics365/business-central/dev-itpro/developer/devenv-al-menusuite-functionality).

### What makes this different from what was previously known as Page Search?
Page Search has evolved into Tell Me to help you get work done quickly. Page Search could only help you navigate to pages or reports. At a technical level, Tell Me is no longer based on the legacy MenuSuite concept.

### I use on-premises [!INCLUDE[d365fin](includes/d365fin_md.md)]. Does that include Tell Me?
You can use Tell Me in the on-premises Web Client to find actions, pages, and reports, but not documentation, or apps and consulting services on AppSource.

### Is Tell Me available for all form factors?
Tell Me is only available in the Web Client or Windows desktop app.

### Are the documentation results available in any language?
The help articles display in the language you have specified in **My Settings**, if help is available in that language.

### Why don't I see a bookmark icon for my search results?
The bookmark icon is not displayed in the Tell Me window when personalization is disabled for a user role.


## See Also  
[Save and Personalize List Views](ui-views.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Finding Pages with the Role Explorer](ui-role-explorer.md)  
[Bookmark a Page or Report on Your Role Center](ui-bookmarks.md)
