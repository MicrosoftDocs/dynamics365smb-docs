---
title: Credit memos and cancellation
description: You can use credit memos in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8059,
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
---

# Credit memos

If a contract invoice contains a mistake, such as incorrect customer information due to a name change, you can credit the invoice. Once credited, you can correct the information in the contract and recreate the invoice.

If a customer cancels a service, you can terminate a contract line and it won't be billed.

If deferrals were created by a contract invoice, they're automatically fully released on the **Posting Date of Credit Memo** when you credit the contract invoice. To learn more, go to [Contract deferrals](../working-with-contracts/contract-deferrals.md).

## Delete unposted invoices

You can delete an invoice as long as it isn't posted. The billing lines are still in **Recurring Billing** page where you can edit, update, or delete them.

To avoid discrepancy between contract and posting documents, the ability to edit unposted [Posting documents](../posting-documents.md) is limited. The same applies to processing of billing and contract lines if there's a posting document.

If the posting document was deleted, you can edit the billing and contract lines normally. After editing a contract line, the billing line must be updated before a new posting document is created. To learn more, go to [Need to update](../recurring-billing.md#need-to-update).

## Credit memos for contract invoices

After an invoice is posted, it must be credited in order to make changes. The credit memo can be created in the posted invoice using the **Create Corrective Credit Memo** action. A credit memo and corresponding billing lines are created automatically for the entire invoice.

> [!CAUTION]
> The credit memo can't be created if there are new billing lines for the same contract line. Delete the billing lines on the **Recurring Billing** page so that you can create the credit memo.
>
> You can only credit the last contract invoice. If a subsequent bill was already created for a contract, you must credit it first.

The credit memo is opened on creation. In the credit memo, positions can be deleted. In this way, individual positions of an invoice can be credited. When the positions are deleted, the billing lines are also deleted. The same applies if the entire credit memo is deleted.

You can't create a new billing line for a contract line if a posting document already exists for it. Delete or post the posting document first.

> [!NOTE]
> If the billing lines for the credit memo don't appear in the billing proposal, you might need to refresh the page or change the billing template changed.

On the contract lines, the **Next Billing Date** reset when the credit memo was created. After posting the credit memo, the contract lines can be edited and calculated with the new values.

## Related information

[Customer subscription contracts](../working-with-contracts/customer-contracts.md)  
[Vendor subscription contracts](../working-with-contracts/vendor-contracts.md)  
