---
title: Map e-documents to purchase order lines with Copilot
description: Learn about how to use Copilot to map e-documents to purchase order lines.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: how-to 
ms.collection:
  - get-started
  - bap-ai-copilot
ms.date: 10/13/2025
ms.update-cycle: 180-days
ms.custom: bap-template 
---

# Map e-documents to purchase order lines with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

As procurement processes become more digital, the e-documents feature in [!INCLUDE [prod_short](includes/prod_short.md)] plays a key role in automating how companies receive and process vendor invoices. Copilot can help by improving the mapping and matching of lines on vendor invoices to purchase orders. Copilot can reduce the time you spend on tasks that would normally require extensive search, lookup, and data entry. Another benefit is when vendor invoices don't relate exactly with purchase orders. Copilot can identify the corresponding purchase orders. Enhanced matching capabilities particularly benefit small and mid-sized organizations that need efficient document tracking for purchase order lines.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

The **E-Document** app supports scenarios for e-documents throughout the sales process. Copilot can also refine how you manage e-documents in the purchase process, particularly with respect to purchase orders. The app lets you specify the type of purchase document to create for each vendor when you receive e-invoices from them.

You can update existing purchase orders in [!INCLUDE [prod_short](includes/prod_short.md)] with the information from you received in the e-invoice.

## Supported languages

[!INCLUDE[copilot-language-support-en-only](includes/copilot-language-support-en-only.md)]

## Prerequisites

- Your admin must activate the **E-Document Matching Assistance** capability. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).  

## Identify purchase orders

First, you can identify the purchase orders that you can automatically match. If your **Vendor** configured the **Receive E-Document To** field to work with **Purchase Orders**, when the electronic document is created in [!INCLUDE[prod_short](includes/prod_short.md)] (manually or from an external endpoint), [!INCLUDE[prod_short](includes/prod_short.md)] does the following:

1. If the purchase order for this vendor exists and there's a purchase order number in the received e-document file, [!INCLUDE[prod_short](includes/prod_short.md)] automatically links the e-document with the purchase order. The **Document Status** of this **E-Document** is **In Progress**, and the **E-Document Status** in the **Service Status** subpage is **Order linked**.  
The link shows in the **Document** field on the e-document. If you need to change the purchase order, you can use the **Update Purchase Order Link** action and then manually choose another purchase order for this vendor. You can only do so before you match the lines on the e-document and purchase order.  
2. If the purchase order for this vendor exists but there isn't a purchase order number in the received e-document file, if you manually upload the document you can choose an existing purchase order by opening the **Purchase Orders** list from the orders that you got from vendors that contain only e-document. If you don't select the correct purchase order, or if you received the e-document automatically from an external endpoint using the **Job Queue**, the new e-document isn't linked with a purchase document and the **Document Status** field shows **Error** and the **E-Document Status** in the **Service Status** subpage is **Imported document processing error**. To finish linking the purchase order, choose the **Update Purchase Order Link** action, and then choose a purchase order for the vendor.  

## Map lines

Copilot helps you automatically match e-invoice lines with purchase order lines, and offers extra matching intelligence to improve the matches.

After they're matched and mapped, [!INCLUDE [prod_short](includes/prod_short.md)] updates the matched purchase order with the relevant receipt information to ensure the correct quantities are received on the order lines.

You can match your received electronic documents with purchase order lines from two different places, from the **E-Documents** page or from the **Purchase Order** page. The easiest way to find purchase orders that are already linked is to use the **Linked Purchase Orders** tile on your Role Center. To find documents that aren't linked, use the **Waiting Purchase E-Invoices** tile to open a list of e-documents that are waiting for review.  

> [!NOTE]
> The **E-Document Activities** group with these two tiles is available in the following Role Centers:
>
> - Business Manager Evaluation
> - Business Manager
> - Accountant
> - Inventory Manager
> - Shipping and Receiving

When you want to run matching from a purchase order, select the **Map E-Document Lines with Copilot** action. The action is available on the **Purchase Orders** list page and the **Purchase Order** page. If you want to run matching from the **E-Documents** page, select the **Match Purchase Order with Copilot** action. To process with matching, follow these steps:

1. Select the **Map E-Document Lines with Copilot** or **Match Purchase Order with Copilot** action for documents that are already linked.  
1. The **E-Document Match Order Lines with Copilot** prompt displays and the **Purchase Order Matching** page in the background. Copilot is automatically creating the mapping for you.
1. After a few seconds, the **E-Document Match Order Lines with Copilot** page suggests lines for matching with a few details:

    1. The prompt header has the following information:

    |Field name |Description |
    |--------|-----------------|
    |Auto-matched | Specifies the number of matches proposed automatically. This number is based on a string comparison. If 80% or more of the descriptions overlap, [!INCLUDE [prod_short](includes/prod_short.md)] matches them automatically without using Copilot capabilities. [!INCLUDE [prod_short](includes/prod_short.md)] also shows lines as auto-matched as item references exist with appropriate conditions. |
    |Copilot matched | Specifies the number of matches proposed by Copilot using both string and semantic comparison. |
    |E-Document No. | Specifies the linked e-document number. |
    |Invoice Total Amount Excl. VAT | Specifies the total invoice amount excluding VAT. |
    |Matched Total Amount Incl. VAT | Specifies the matched amount excluding VAT. |

    1. If all lines match, the following text displays in green font in the upper-right corner, **All lines (100%) are matched. Review match proposals**.  
    1. The **Matched proposal** lines contain the following information:  

       |Field name |Description |
       |--------|-----------------|
       |E-Document Line No. | Specifies the e-document line number from the original e-document file. |
       |E-Document Line Description | Specifies the e-document line description from the original e-document file. |
       |Matched Quantity | Specifies the quantity that is applied to the purchase order line. |
       |Proposal | Specifies the action that Copilot proposed for matching the purchase order lines. |
       |Learn Matching Rule | Specifies whether to create a matching rule for this proposal. If you select this checkbox, [!INCLUDE [prod_short](includes/prod_short.md)] creates item references for items and text to account mappings for G/L accounts. |

    1. All fully suggested and matched lines are marked with green color. If there's an issue, for example, a different price but within the allowed price range, this line is marked with a yellow color. If there's any similarity between the description fields but the price difference is larger than allowed, this line is marked with a red color.
    1. If you aren't satisfied with some suggestions, you can delete them using the **Delete Line** action.  
    1. If you want to see proposal matchings, you can select the link in the **Proposal** column to open the **E-Document Match Details** page.
    1. On the **E-Document Match Details** page you can compare details from the **E-Documents** and **Purchase Order**, to be sure about the suggested matching before confirming it.
    1. After reviewing, close the page.

1. If you aren't satisfied with most of the suggestions, or if you don't want to use the **E-Document Match Order Lines with Copilot** feature, select **Discard it**. You can create the matches manually. To learn more, go to[manual matching](finance-how-use-edocuments-purchase.md).  
1. If you want to keep suggestions, select **Keep it**.
1. [!INCLUDE[prod_short](includes/prod_short.md)] closes the Copilot prompt and lines on the **Purchase Order Matching** page are marked as green.  
1. You can continue to work as if you're doing a manual matching. For example, you can remove, create, or reset matches. If you don't want to change anything, just select the **Apply To Purchase Order** action and continue to work with the purchase order.

> [!NOTE]
> You can also select the **Match with Copilot** action from the **Purchase Order Matching** page again. If you do, you're asked whether you want to overwrite the existing matches.  

> [!NOTE]
> Price/Cost analysis and the check for available quantity are preprocessing activities.

## Related information

[E-documents overview](finance-edocuments-overview.md)  
[Use e-documents in sales](finance-how-use-edocuments.md)  
[Use e-documents in purchase](finance-how-use-edocuments-purchase.md)  
[Troubleshoot Copilot and agent capabilities](ai-copilot-troubleshooting.md)  
[Responsible AI FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)  
