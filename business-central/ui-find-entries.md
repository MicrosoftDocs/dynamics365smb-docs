---
title: Find Related Entries for Documents
description: Find related documents and entries by document number, posting date, business contact, serial number, or lot number to investigate transactions.
author: jswymer
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: find
ms.search.form: 344_Primary
ms.date: 11/10/2026
ai-usage: ai-assisted
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Find related entries for documents

Learn how to find documents and entries that are related to each other based on a piece of common information, like:

- Document number or posting date.
- Business contact type, number, or external document number.
- Item serial number or lot number.

This feature is useful for finding the ledger entries that resulted from certain transactions. When you search by document number, you can print the summary from the **Document Entries** report.

## Open the Find Entries page

The find entries feature is readily available from almost any page by pressing the <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Q</kbd> keys. From pages that specifically display posted documents or posted document entries&mdash;for both lists and cards&mdash;you can also open the feature by choosing the **Find entries** action.

The **Find Entries** page includes all related documents and entries based on the document no. and posting date. The page is divided into three sections:

- The top section displays fields and actions that you use for filtering your search.
- The middle section displays related documents based on the search.
- The bottom section displays information about the source document that was found by searching.

## Search for entries

You can search for entries based on information about either the document, business contact, or item reference. In the **Search By** field at the top of the page, select an option based on the type of information you have:

|Option|Description|
|------|-----------|
| **Search for documents** | View entries based on a document number, posting date, or external document number. |
| **Search for business contacts** | View entries based on a contact type, contact number, or external document number. The external document number lets you search for vendor or customer documents by using the number assigned by the contact. |
| **Search for item references** | View entries based on a serial number or lot number. You can enter a number or a filter. Use this option to see where an item tracking number was used, which vendor supplied the item, or which customer bought it. |

After you make a selection, enter the relevant search information in the fields at the top of the page. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] When you're finished, choose **Find** to start the search. If you change any of the filters, you have to choose **Find** again.

> [!TIP]
> For a couple of examples about using **Find Entries**, see [Trace Item-Tracked Items](inventory-how-to-trace-item-tracked-items.md) and [Walkthrough: Tracing Serial-Lot Numbers](walkthrough-tracing-serial-lot-numbers.md).

## Related information

[Trace Item-Tracked Items](inventory-how-to-trace-item-tracked-items.md)  
[Find Posted Documents without Incoming Document Records](across-how-find-posted-documents-without-income-document-records.md)  
[Accessibility and Keyboard Shortcuts](ui-accessibility.md)  
[Work with Business Central](ui-work-product.md)  
[Add a Page Action to Your Role Center](ui-bookmarks.md)  
[Find Pages and Information with Tell Me](ui-search.md)  
[Find Pages with the Role Explorer](ui-role-explorer.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
