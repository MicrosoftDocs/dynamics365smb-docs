---
title: Credit Memos and Cancellation
hide_title: true
sidebar_label: Credit Memos
slug: /srb/sales/credit-memo-cancellation
---

# Credit Memos
If a contract invoice contains incorrect information, such as incorrect customer information due to a name change, the invoice can be credited. Once credited, the information in the contract can be corrected and the invoice recreated.
If a customer cancels a service, this can be maintained in the contract line. Once the contract line is terminated, it will no longer be billed.
If [deferrals](/docs/srb/working-with-contracts/contract-deferrals.md) have been created by a contract invoice, they will automatically be fully released on the **Posting Date of Credit Memo** when the contract invoice is credited.


## Delete unposted invoices
As long as the invoice is not posted, it can be easily deleted. The billing lines are still in **Recurring Billing** and can be edited, updated or deleted there.

The ability to edit unposted contract invoices or Credit Memos (**[posting documents](/docs/srb/posting-documents.md)**) is severely limited to avoid discrepancy between contract and posting documents. The same applies to the processing of billing lines and contract lines if there is a posting document.

If the posting document has been deleted, the billing and contract lines can be edited normally. After editing a contract line, the billing line must be updated before a new posting document is created [Update Recurring Billing](/docs/srb/recurring-billing.md#need-to-update).

## Credit Memos for contract invoices
Once the invoice is posted, it must be credited in order to make changes. The Credit Memo can be created in the posted invoice using the **Create Corrective Credit Memo** function. A Credit Memo and corresponding billing lines will be created automatically for the entire invoice.

:::caution Attention
The Credit Memo cannot be created if there are already new billing lines for the same contract line. The billing lines must be deleted in **Recurring Billing** before the Credit Memo can be created.
Only the *last* contract invoice can be credited. If a subsequent bill has already been created for a contract, it must be credited first.
:::

The Credit Memo is opened on creation. In the Credit Memo, positions can be deleted. In this way, individual positions of an invoice can be credited. When the positions are deleted, the billing lines are also deleted. The same applies if the entire Credit Memo is deleted.

A new billing line cannot be created for a contract line if a posting document already exists for it. The posting document must be deleted or posted first.

:::info
If the billing lines for the Credit Memo do not appear in the Billing Proposal, the page may need to be manually refreshed (**Refresh**) or the Billing Template changed.
:::

In the contract lines, the **Next Billing Date** was immediately reset when the Credit Memo was created. After posting the Credit Memo, the contract lines can be edited and calculated with the new values.