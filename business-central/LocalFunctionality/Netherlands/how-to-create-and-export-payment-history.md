---
title: How to Create and Export Payment History [NL]
description: After creating and modifying your proposal as needed, you can move forward with processing it to create a payment history.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: create payment history, export payment history, Dutch version, Netherlands, proposal
ms.date: 03/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create and export payment history in the Dutch version

After creating a proposal and making any modifications, you can process the proposal to create a payment history. Proposals can be created manually or automatically from a vendor or customer ledger entry. Learn more in [Create Proposals](how-to-create-proposals.md).  

 For exporting payment histories, the following protocols are supported:  

- BTL91 $)  
- BBV  
- PAYMUL  

## Create a payment history for a proposal  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Telebank - Bank Overview**, and then choose the related link.  

   If you want to print the proposal before you process it, choose the **Print** button.  

1. To process the proposal, choose the **Process** action.  
1. To view the payment history, close the **Telebank Proposal** page. Make sure the same bank account on the **Telebank – Bank Overview** page is selected, and then choose the **Payment History** action.  

The **Payment History List** page displays the payment history that you created.  

## Export a payment history  

On the **Payment History List** page, choose the **Export** action.  

> [!NOTE]  
> A text file is created. This file contains the path and file name as defined in the **Default File Names Field** field of the export protocol.  

## Related information

[Create Proposals](how-to-create-proposals.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
