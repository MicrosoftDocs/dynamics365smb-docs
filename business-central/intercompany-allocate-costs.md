---
title: Allocate Costs to Intercompany Partners| Microsoft Docs
description: Learn how VAT settings for customers and vendors control whether, and how, VAT is calculated.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: incoming document
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Allocate Costs to Intercompany Partners
When you use intercompany postings to transfer documents between partner companies, the VAT-related settings (primarily the VAT business posting group) assigned to the customer or vendor accounts (associated with the intercompany Partner) control whether, and how, VAT is calculated and registered. 
You can also do cost distributions directly from a purchase order to partner companies. For example, if you register a purchase invoice from an external vendor and you want to distribute some or all of the costs to one or more intercompany partners.

You can allocate costs can be to one or more intercompany partners using the following:

* **Intercompany General Journals** - These journals are useful when a service is purchased. For example, when a parent company hires a service to set up computer systems in two subsidiaries. The invoice is sent to the parent company, but the costs are allocate to the intercompany partners. For more information, see [Work with Intercompany Documents and Journals](intercompany-how-work-documents-journals.md).
* Purchase orders and invoices - Using purchase documents is useful when the purchasing functions of, for example, operating expenses, are centralized in one company and then allocated to the intercompany partners.

## To allocate costs using an intercompany general journal
To enter a  line in an intercompany general journal, follow these steps. 

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany General Journal** , and then choose the related link.
2. If required, in the **External Document No.** field, enter the document number on the invoice from the vendor.
3. In the **Document Type** field, choose **Invoice**.
4. In the **Account Type** field, choose **Vendor**.
5. In the **Account No.** field, choose the vendor.
6. In the **Amount** field, enter a negative amount equal to the amount on the invoice.
7. In the **Bal. Account Type** field, choose **G/L Account**.
8. In the **Bal. Account No.** field, choose the balancing account to use.
9. To allocate costs to intercompany partners, follow these steps:
   1. Create a new line.
   2. Leave the **Document Type** field, choose the option that leaves the field blank.
   3. In the **Document No.** field, enter a number that is different than the number in the **External Document No.** field. The cost allocation is considered a different transaction.
   4. In the **Account Type** field, choose **IC Partner**.
   5. In the **Account No.** field, choose the intercompany partner to allocate the cost to.
   6. In the **Balance Account Type** field, choose **G/L Account**.
   7. In the **Balance Account No.** field, choose the G/L account to which to post the amount you receive from the intercompany partner.
   1. In the **Amount** field, enter the amount of the invoice to allocate to the intercompany partner.
   1. In the **IC Partner G/L Acc. No.** field, choose the G/L account that you want to post the amount to for the intercompany partner. 
   1. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Repeat these steps for each intercompany partner who should share in the cost.
1. To post the document and allocate the costs, choose **Post**.  

## To allocate costs using a purchase document
The following procedure describes how to allocate costs using a purchase invoice. The steps are the same for purchase orders.

> [!NOTE]
> To complete these steps you must personalize the **Purchase Invoice** page by adding the **IC Partner Code**, **IC Partner Ref. Type**, and **IC Partner** fields. For more information, see [To start personalizing a page through the Personalizing banner](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoice** , and then choose the related link.
2. In the **Type** field, choose **G/L Account**.
   
   G/L Account is the only option you can use to allocate costs.  
1. In the **No.** field, choose the G/L account to post to.
1. In the **IC Partner Code** field, choose the intercompany partner to allocate the cost to.
1. In the **IC Partner Ref. Type** choose the G/L account to use for the allocation. This account will map the expense to an account in the intercomany partner's chart of accounts.
1. In the **Quantity** field, specify the number of units to charge to the intercompany partner.
1. In the **Direct Unit Cost Excl. VAT (or Incl. VAT)** field, enter the cost per item to charge to the intercompany partner.
1. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 
1. To post the purchase order, choose **Post**.

## To send the allocated costs to intercompany partners
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IC Outbox Transactions**, and then choose the related link.
2. Choose lines to send, and then choose the **Send to IC Partner** action. 
3. To allocate the costs, choose the **Complete Line Actions** action.

## Calculating VAT for Cost Distributions
When you use a document to distribute costs to intercompany partners, there are two VAT settings to be aware of: 
* The settings on the G/L account for expenses:
   * If the general business or VAT business posting groups are set up on the G/L account, then the calculation depends on the groups and the product groups from the document line.
   * If the general business or VAT business posting groups are not specified on the G/L account, the calculation depends on the following:
* The posting group settings on the intercompany partner
   * Whether the intercompany partner is assigned to a customer number that does not have a general business or VAT business posting groups specified.
   * There is no customer number associated with the intercompany partner. Then the general business or VAT business posting groups are blank, and the line in the VAT posting setup is used, which is usually a group where 0% VAT is specified.

> [!NOTE]
> It is important to validate both the intercompany partner setup and the G/L account setup (for the expense account used for the cost distribution) before you allocate costs to intercompany partners.

## Related information
[Set Up Intercompany](intercompany-how-setup.md)  
[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
