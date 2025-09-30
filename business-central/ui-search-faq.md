---
title: Frequently Asked Questions about Tell Me
description: This article provides answers to questions that our partners and customers often ask about the Tell Me feature.
author: brentholtorf
ms.topic: faq
ms.service: dynamics-365-business-central
ms.search.keywords: find, search, Tell Me
ms.search.form: TellMe
ms.date: 09/30/2025
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Tell Me FAQ

This article answers questions that our advanced users often ask about the Tell me what you want to do feature.

## Why isn't there an Advanced tab?

There are a couple reasons why the **Advanced** tab isn't available:

- You're using a Business Central on-premises version. The **Advanced** tab is only available in Business Central online.
- The **Advanced Tell Me** feature isn't enabled in the **Feature Management** page. Learn more in [Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management).

## Are all actions from my current page discoverable in Tell Me?

No. Actions in parts, such as the Sales Lines part or FactBoxes, aren't displayed in Tell Me.

## Can I search for a specific record?

Yes. For example, if you want to quickly find a sales order, enter it's identifier, and then choose the **Search company data** action. If you only know the customer's name, enter that. Tell Me arranges results by type, so you could find the order under the Sales Orders category.

## Are the results in Tell Me filtered by permissions?

If the user doesn't have AccessByPermissions, then actions aren't displayed. However, pages and reports appear in the results but require that the user has permission to access them. A message displays if the user doesn't have permission to view the object.

## Does Tell Me display content from my customizations or installed third-party extensions?

Actions, pages, and reports that originate from extensions are picked up by Tell Me. For technical information about how to make custom pages and reports discoverable, see [Adding Pages and Reports to Search](/dynamics365/business-central/dev-itpro/developer/devenv-al-menusuite-functionality).

## What makes this different from what was previously known as Page Search?

Page Search has evolved into Tell Me to help you get work done quickly. Page Search could only help you navigate to pages or reports. At a technical level, Tell Me is no longer based on the legacy MenuSuite concept.

## I use on-premises [!INCLUDE[prod_short](includes/prod_short.md)]. Does that include Tell Me?

You can use Tell Me in the on-premises Web Client to find actions, pages, and reports, but not apps and consulting services on AppSource.

## Is Tell Me available for all form factors?

Yes. It was introduced on phones and tablets in Business Central 2023 release wave 2. In 2023 release wave 2, it must be enabled in [Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management) using the **Feature: Search for pages and data in the mobile app** switch. In 2024 release wave 1 and later, it's always enabled.

<!-- removed in v20 because of Help pane
### Are the documentation results available in any language?
The help articles display in the language you have specified in **My Settings**, if help is available in that language.
-->

## Does Tell Me give me help on how to use pages, reports, and other things?

No, but you can easily get this information from the Help pane. Just select the **Search Help** action in the **Tell me what you want to do** page or select <kbd>Ctrl</kbd>+<kbd>F1</kbd> on your keyboard. To learn more about the Help pane, go to [Help pane](product-help-and-support.md#help-pane).

### Why don't I see a bookmark icon for my search results?

The bookmark icon isn't displayed in the Tell Me window when personalization is disabled for a user role.

## Related information  

[Save and Personalize List Views](ui-views.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Finding Pages with the Role Explorer](ui-role-explorer.md)  
[Bookmark a Page or Report on Your Role Center](ui-bookmarks.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
