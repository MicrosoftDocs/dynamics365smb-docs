---
title: Create and Export Payment History in the Dutch Version [NL]
description: After creating and modifying your proposal as needed, you can move forward with processing it to create a payment history.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: create payment history, export payment history, Dutch version, Netherlands, proposal
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create and export payment history in the Dutch version

After creating a proposal and making any modifications, you can process the proposal to create a payment history. Proposals can be created manually or automatically from a vendor or customer ledger entry. Learn more in [Create Proposals](how-to-create-proposals.md).  

The export protocol linked to the transaction mode determines the payment file format. Use a format accepted by your bank, such as SEPA ISO 20022 for euro credit transfers or direct debits. Learn more in [Activate SEPA payments](how-to-activate-sepa-payments.md) and [Telebanking](telebanking.md#exchange-protocols).

## Create a payment history for a proposal  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Telebank - Bank Overview**, and then choose the related link.  

1. Select the relevant bank account and choose **Proposal**.
1. Review the proposal and choose **Check**. Resolve any errors before processing. If needed, choose **Print** to print the proposal.
1. To process the proposal, choose the **Process** action.  
1. To view the payment history, close the **Telebank Proposal** page. Make sure the same bank account on the **Telebank – Bank Overview** page is selected, and then choose the **Payment History** action.  

The **Payment History List** page displays the payment history that you created.  

## Export a payment history  

On the **Payment History List** page, select the payment history and choose **Export**. Complete any options for the configured export report.

> [!NOTE]  
> The export protocol determines the file format and uses **Default File Names** to generate the file name. Exporting creates a file for you to submit through your bank's banking software or portal. It doesn't send the payment instructions to the bank.

## Related information

[Create Proposals](how-to-create-proposals.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
