---
title: Map e-documents to purchase order lines with Copilot
description: Learn about how to use Copilot to map e-documents to purchase order lines.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to 
ms.collection:
  - get-started
  - bap-ai-copilot
ms.date: 04/10/2024
ms.custom: bap-template 
---

# Map e-documents to purchase order lines with Copilot (preview)

As procurement processes become more digital, the e-documents feature in Business Central plays a key role in automating the vendor invoice reception and processing. Copilot can help this process by improving the mapping and matching of vendor invoices to purchase orders. This reduces time-consuming tasks that would normally include extensive search, lookup, and data entry. The benefit is compounded by the fact that vendor invoices often don't relate exactly with purchase orders, in which case Copilot is better positioned to identify the corresponding purchase orders. Enhanced matching capabilities particularly benefit small and midsized organizations that need efficient document tracking for purchase order lines. Copilot is the AI-powered assistant for work that boosts creativity and improves productivity for Business Central users.

> [!IMPORTANT]
> - This is a Production Ready Preview feature for production and sandbox environments in any country localization, with the exception of Canada.
> - Production Ready Previews are subject to supplemental terms of use. More information: [Supplemental terms of use for Dynamics 365 preview](https://go.microsoft.com/fwlink/?linkid=2105274)
> - AI-generated content may be incorrect.

In the initial release of the **e-document** app, we introduced fundamental scenarios for e-documents for the entire sales process. However, there's a need for enhancements and automation in handling the received documents, especially in the context of purchase processes. Copilot refines how you manage e-documents in the purchase process, particularly with respect to purchase orders. The e-documents framework lets you specify the type of purchase document to create for each vendor when you receive e-invoices from them. Previously, the only option was to create a purchase invoice, either as a document or a general ledger journal.

You can now update an existing purchase order in Business Central with the information received in the e-invoice.

<!--
> [!NOTE]
> - This feature is available as a production-ready preview for production and sandbox environments in any country localization, with the exception of Canada. Production-ready previews are subject to supplemental terms of use. For more information, see [Supplemental terms of use for Dynamics 365 preview](https://go.microsoft.com/fwlink/?linkid=2105274).
> - AI-generated content may be incorrect.-->

## To activate Copilot  

If you didn't activate the **E-Document Matching Assistance** Copilot, you must do so manually. To enable the **E-Document Matching Assistance** copilot, follow these steps: 

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Copilot & AI Capabilities**, and then select the related link. 
2. In the list of capabilities choose **E-Document Matching Assistance** and change the status to **Active**.  

You can start using Copilot as soon as it's activated. 

## Identify purchase orders

First, you can identify the purchase orders that you can automatically match. If your **Vendor** has configured the **Receive E-Document To** field to work with **Purchase Orders**, once the electronic document is created in [!INCLUDE[prod_short](includes/prod_short.md)] (manually or from an external endpoint), [!INCLUDE[prod_short](includes/prod_short.md)] will do the following:

1. If the **Purchase Order** for this particular vendor *exists and there's a purchase order number* in the received **E-Document** file, [!INCLUDE[prod_short](includes/prod_short.md)] will automatically link this **E-Document** with the specified **Purchase Order**. The **Document Status** of this **E-Document** will be **In Progress**, and the **E-Document Status** in the **Service Status** subpage will be **Order linked**.  
This link will be visible in the **Document** field on this specific **E-Document**. If you need to change the **Purchase Order** linked automatically, you can do so by using the **Update Purchase Order Link** action and then manually choose one of the existing purchase orders for this vendor. You can only do so before matching the lines between **E-Document** and **Purchase Order**.  
2. If the **Purchase Order** for this particular vendor *exists but there's no purchase order number* in the received **E-Document** file, if you uploaded this document manually, [!INCLUDE[prod_short](includes/prod_short.md)] allows you to choose from one of the existing purchase orders, opening the **Purchase Orders** list from the orders that you got from vendors containing only **E-Document**, where you need to select **Purchase Order** you want and select **OK**. If you don't select the right **Purchase Order**, or you got the **E-Document** automatically from an external endpoint using the **Job Queue**, the new **E-Document** won't be linked with any purchase document and the **Document Status** is shown as **Error** and the **E-Document Status** in the **Service Status** subpage is **Imported document processing error**. To finish linking the **Purchase Order**, choose the **Update Purchase Order Link** action, and then choose one of the existing purchase orders for this vendor.  

## Map lines

Copilot helps you automatically match e-invoice lines with purchase order lines, and offers extra matching intelligence to improve the matches.

After they're matched and mapped, [!INCLUDE [prod_short](includes/prod_short.md)] updates the matched purchase order with the relevant receipt information to ensure the right quantities are received on the order lines.

You can match your received electronic documents with the purchase orders’ lines from two different places, from the **E-Documents** page or from the **Purchase Order** page. The easiest way to locate the already linked **Purchase Orders** is to use the **Linked Purchase Orders** tile as part of **E-Document Activities**. All non-linked documents are found using the tile **Waiting Purchase E-Invoices** where you have a list of **E-Documents** that you must review.  

> [!NOTE]
> The **E-Document Activities** with these two tiles is found in the following Role Centers: **Business Manager Evaluation**, **Business Manager**, **Accountant**, **Inventory Manager**, and **Shipping and Receiving**.

When you want to run matching from the purchase order, choose the **Map E-Document Lines** action, which exists on both the purchase order and purchase order list pages. But, if you want to run matching from the **E-Documents** page, choose the **Match Purchase Order** action from this page. To process with matching, follow these steps:

1. Choose the **Map E-Document Lines** or **Match Purchase Order** action, for already linked documents.  
2. You can notice that **E-Document Match Order Lines with Copilot** prompt is working and you have the **Purchase Order Matching** page in the background. That means the same process is happening, but with the automatic support of **Copilot**, who runs the process of matching instead of you. 
3. After a few seconds, the **E-Document Match Order Lines with Copilot** will suggest lines for matching with some more details: 

    1. In the prompt header, you can find the following information: 

    |Field name |Description |
    |--------|-----------------|
    |Auto-matched | Specifies the number of matches proposed automatically. This is based on a string comparison and if there's 80% or more description overlapping, the system will match these descriptions automatically without using GPT capabilities. |
    |Copilot matched | Specifies the number of matches proposed by Copilot using both string and semantic comparison. |
    |E-Document No. | Specifies the linked e-document number. |
    |Invoice Total Amount Excl. VAT | Specifies the total invoice amount excluding VAT. |
    |Matched Total Amount Incl. VAT | Specifies the matched amount excluding VAT. |
    
    2. If all lines are matched, you see the green text in the upper-right corner: **All lines (100%) are matched. Review match proposals**.  
    3. In the **Matched proposal** lines, you find the following information:  

    |Field name |Description |
    |--------|-----------------|
    |E-Document Line No. | Specifies the e-document line number (coming from the original e-document file). |
    |E-Document Line Description | Specifies the e-document line description (coming from the original e-document file). |
    |Matched Quantity | Specifies the quantity that will be applied to the purchase order line. |
    |Proposal | Specifies the action proposed by AI, and these suggested actions are related to matching the purchase order lines. |

    4. All fully suggested and matched lines are marked with green color. If there's any issue, for example, different price, but in the allowed price range, this line will be marked with yellow color, and if there's any similarity between the description fields, but the price difference is bigger than allowed, this line will be marked with red color. 
    5. If you aren't satisfied with some suggestions, you can delete them using the **Delete Line** action.  
    6. If you want to see proposal matchings, you can select the link in the **Proposal** column to open the **E-Document Match Details** page. 
    7. On the **E-Document Match Details** page you can compare details from the **E-Documents** and **Purchase Order**, to be sure about the suggested matching before confirming it. 
    8. After reviewing, close the page.   

4. If you aren't satisfied with most of the suggestions, or in a case you don't want to use the **E-Document Match Order Lines with Copilot** feature, select **Discard it**, and you can continue with the [manual matching](finance-how-use-edocuments-purchase.md).  
5. If you want to keep suggestions, choose the **Keep it** button and the system saves all suggestions made by the **Copilot**.  
6. [!INCLUDE[prod_short](includes/prod_short.md)] closes the Copilot prompt and lines on the **Purchase Order Matching** page are marked as green, as they're already matched.  
7. From now on, you can continue to work as you're doing manual matching, and that means you can remove matches, manual matches, reset matching or if there aren't any changes you want to make, just choose the **Apply To Purchase Order** action and continue working with the **Purchase Order**. 

> [!NOTE]
> You can also choose the **Match with Copilot** action from the **Purchase Order Matching** page again, but in this case, you are asked if you want to overwrite the existing matches, as all lines are already matched.  

> [!NOTE]
> Price/Cost analyze, and the available quantity check is a part of preprocessing activity. 

## See also

[E-documents overview](finance-edocuments-overview.md)    
[Use e-documents in sales](finance-how-use-edocuments.md)    
[Use e-documents in purchase](finance-how-use-edocuments-purchase.md)   
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)    
[Responsible AI FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)    
