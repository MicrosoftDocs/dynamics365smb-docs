---
title: Allocate Costs to Intercompany Partners| Microsoft Docs
description: Learn how VAT settings for customers and vendors control whether, and how, VAT is calculated.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: incoming document
ms.date: 10/01/2020
ms.author: bholtorf

---
# Allocate Costs to Intercompany Partners
When you use intercompany postings to transfer documents between partner companies, the VAT-related settings (primarily the VAT business posting group) assigned to the customer or vendor accounts (associated with the intercompany Partner) control whether, and how, VAT is calculated and registered. 
You can also do cost distributions directly from a purchase order to partner companies. For example, if you register a purchase invoice from an external vendor and you want to distribute some or all of the costs to one or more intercompany partners.

You can allocate costs can be to one or more intercompany partners using the following:

* **Intercompany General Journals** - These journals are useful when a service is purchased. For example, when a parent company hires a service to set up computer systems in two subsidiaries. The invoice is sent to the parent company, but the costs are allocate to the intercompany partners. For more information, see [Work with Intercompany Documents and Journals](intercompany-how-work-documents-journals.md).
* Purchase orders and invoices - Using purchase documents is useful when the purchasing functions of, for example, operating expenses, are centralized in one company and then allocated to the intercompany partners.

## To allocate costs using an intercompany general journal
To enter a  line in an intercompany general journal, follow these steps. 

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany General Journal** , and then choose the related link.
2. If required, in the **External Document No.** field, enter the document number on the invoice from the vendor.
3. In the **Document Type** field, choose **Invoice**.
4. In the **Account Type** field, choose **Vendor**.
5. In the **Account No.** field, choose the vendor.
6. In the **Amount** field, enter the amount on the invoice.
7. In the **Bal. Account Type** field, choose **G/L Account**.
8. In the **Bal. Account No.** field, choose the balancing account to use.
9. To enter lines that allocate costs to intercompany partners, follow these steps:
   1. Create a new line.
   2. Leave the **Document Type** field, choose the option that leaves the field blank.
   3. In the **Account Type** field, choose **IC Partner**.
   4. In the **Account No.** field, choose the intercompany partner to allocate the cost to.
   5. In the **Amount** field, enter the amount of the invoice to allocate to the intercompany partner.
   6. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Repeat these steps for each intercompany partner who should share in the cost.
10. To post the document and allocate the costs, choose **Post**.  

<!--What about the IC Partner G/L Account. No. field? Also, should we describe how to do it using a PO? -->

## To allocate costs using a purchase document
<!--> [!NOTE]
> Calculating VAT for cost allocation-->
When you use a document to distribute costs to intercompany partners, there are two VAT settings to be aware of: 
1. The settings on the G/L account for expenses:
    a. If the general business or VAT business posting groups are set up on the G/L account, then the calculation depends on the groups and the product groups from the document line.
    b. If the general business or VAT business posting groups are not specified on the G/L account, the calculation depends on the following:
2.	The posting group settings on the intercompany partner
    a. Whether the intercompany partner is assigned to a customer number that does not have a general business or VAT business posting groups specified.
    b. There is no customer number associated with the intercompany partner. Then the general business or VAT business posting groups are blank, and the line in the VAT posting setup is used, which is usually a group where 0% VAT is specified.

It is important to validate both the intercompany partner setup and the G/L account setup (for the expense account used for the cost distribution) before you allocate costs to intercompany partners.

## See Also
[Set Up Intercompany](intercompany-how-setup.md)  
[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)