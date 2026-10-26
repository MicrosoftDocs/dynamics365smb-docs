---
title: Bill of Lading [RU]
description: Enhancements for Bill of Lading documents in the Russian version of Business Central.
author: altotovi
ms.topic: how-to
ms.search.keywords: bills of lading, lading report, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: altotovi
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Bill of lading in the Russian version

In Russia, a bill of lading is a legal document between the company that ships the items and the carrier. The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.

## Set up bills of lading report

Set **Bill of Lading Template Code** in **Sales & Receivables Setup** before you generate the report.

To set up the **Bill of Lading** report, use the following steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selection – Sales**, and then choose the related link.
1. In the **Usage** field, choose **Shipment**
1. On the relevant line, add the report *14951* to the line so it can be printed from the **Posted Sales Shipment** page.

The report is exported to Microsoft Excel.

## Print document

When you set up the document, it can be printed from any **Posted Sales Shipment**. When you print the report, the report is exported to Excel.

If **Report Selection - Print** opens, select **Print Report** for **Bill of Lading**, and then choose **OK**. Complete the report options and choose **OK** to generate the workbook.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
