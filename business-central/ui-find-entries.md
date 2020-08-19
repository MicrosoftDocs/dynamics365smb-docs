---
title: Finding entries | Microsoft Docs
description: This topic describes how to use search to find actions, pages, reports, documentation, and data, as well as other apps and consulting services.
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: find
ms.date: 04/01/2020
ms.author: jswymer

---
# Finding Related Entries for Posted Documents 

In this article, you learn how to find documents and entries that are related to each other based on a common information, like:

- Document number or posting date
- Business contact type, number or external document number
- Item serial number or lot number

This feature is useful if you want to find the ledger entries that resulted from certain transactions. When you search by document number, you can print the summary from the Document Entries report. 
<!--Shows the number and type of entries that have the same document number or posting date. You can also use this feature to find the documents and entries where certain lot numbers and serial numbers are used.. in [!INCLUDE[d365fin](includes/d365fin_md.md)] -->

## Get started 

The first thing to do is open the **Find Entries** page. There are two ways to open this page:

- Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Find Entries**, and then choose the related link.

    With this way, the **Find Entries** page might be empty, and you'll have to start searching for entries from scratch.
    
- Open a page that displays posted documents or posted documents entries, either a list or a card. Then, locate and select the **Find Entries** action.

    With this way, the **Find Entries**, page will include all related documents and entries based on the document no. and posting date.


    > [!TIP]
    > If you are on a page that has the **Find Entries** action, press crtl+G to open the **Find Entries** page directly. 
<!--   
    y, list posted entries and in posted sales invoices, purchase invoices, credit memos, sales receipts, and purchase shipments. In this case, the Navigate window will show the document number and posting date of the entries that you selected. The Navigate window also lists the documents that have the same document number and posting date as the entries that you selected.a page thas posted  e You can open the Navigate window in two ways:

- By opening an empty Navigate window. On the Home tab, in the Find by group, you can choose the type of data that you want to navigate from. You can navigate from a document, a business contact, or the lot number or serial number for an item.
- From pages that display posted entries and in posted sales invoices, purchase invoices, credit memos, sales receipts, and purchase shipments. In this case, the Navigate window will show the document number and posting date of the entries that you selected. The Navigate window also lists the documents that have the same document number and posting date as the entries that you selected.
-->

The **Finding Entries** page is divided into three sections:

- The top section displays fields and actions that you use for filtering your search.
- The middle section displays related documents based on the search.
- The bottom section displays information about the source document that was found by searching.

## Search for entries

You can search for entries based on information about either the document, business contact, or item reference. To change the search, select **Actions**, **Find By**, then one of the following actions:

|Action|Description|
|------|-----------|
|Find by Document|View entries based on a specific document number and/or posting date.|
|Business Contact |View entries based on a specific contact type, contact number, anr/or external document number. You can enter document information that was assigned by a vendor or a customer. Use the available fields to search for vendor documents by using the numbers that the vendor has assigned the documents.|
|Item reference|View entires based on a serial number or lot number. You can enter the lot number or serial number, or you can filter on the lot number or serial number that you want to search for. This option is useful if you want to see where a specific item tracking number was used, what vendor it came from, or what customer it was sold to.|

After you make a selection enter the relevant search information in the fields at the top. Use the tooltips on the fields to help. When you are finished, choose **Find** to start the search. If you change any of the filters, you must choose **Find** again.
<!--
 To eactrh If the search finds more than one document number, these fields will be empty.
ay he  is divided into four areasa different first FastTab, depending on your selection in the Find by group. You must enter information about the documents or item tracking numbers that you want to search for before information is filled in from the records located.
The **Finding Entries** page a different first FastTab, depending on your selection in the Find by group. You must enter information about the documents or item tracking numbers that you want to search for before information is filled in from the records located.

After you have entered the relevant search information, on the Actions tab, choose Find to start the search. If you change any of the filters, you must choose Find again.

The **Finding Entries** page shows the following information for the located documents.

Field    Description
Document Type, Source Type, Source No., and Source Name

These fields contain information about the source document that was found by searching for the document number. If the search finds more than one document number, these fields will be empty.

Table Name

This column shows a list of the ledger entry tables that contain the ledger entries located by the search.

No. of Records

This column shows the number of records found in each of the ledger entry tables that are listed.

After the Navigate feature has located the ledger entries, they are listed in the Related Entries column. You can quickly see the individual entries in each table by choosing the relevant line and then choosing the Show Details command.

The following sections describe the filters you can specify.
-->

<!--
### Find by Document
On the Document FastTab, enter the document numbers and posting dates as described in the following table.

Field    Description
Document No.

Enter the document numbers on which you require additional information. You can insert a filter if you want Microsoft Dynamics NAV to search for a certain interval of document numbers.

Posting Date

Enter the posting date on which the document you are searching for was posted. You can insert a date filter if the documents that you are searching for were posted in a certain time interval.

### Find by Business Contact

On the Business Contact FastTab, you can enter document information that was assigned by a vendor or a customer. You can use the options on this tab to search for vendor documents by using the numbers that the vendor has assigned the documents. For example, the following table shows how you can use this feature to find an invoice when you only have the invoice number assigned by the vendor.

Field    Description
Business Contact Type

Select one of the options: <Blank>, Vendor, or Customer. <Blank> is the default value. Select Vendor or Customer when you want to search for vendor or customer documents.

Business Contact No.

Select the number of the vendor or customer who assigned a number to the invoice that you are searching for.

Document No.

Enter the document number assigned by the vendor.

Microsoft Dynamics NAV will match this number with the number in the External Document No. field for all customer or vendor ledger entries. Then Microsoft Dynamics NAV will show all ledger entries that contain this document number.

### Find by Item Reference
On the Item Reference FastTab, you can enter the lot number or serial number, or you can filter on the lot number or serial number that you want to search for. This option is useful if you want to see where a specific item tracking number was used, what vendor it came from, or what customer it was sold to.

Field    Description
Serial No.

Enter the serial numbers on which you require additional information. You can insert a filter if you want to search for a certain set of serial numbers.

Lot No.

Enter the lot numbers on which you require additional information. You can insert a filter if you want to search for a certain set of lot numbers.

-->
## See Related Training at [Microsoft Learn](/learn/modules/user-interface-dynamics-365-business-central/index)

## See Also
[Working with Business Central](ui-work-product.md)  
[Add a Page Action to Your Role Center](ui-bookmarks.md)
