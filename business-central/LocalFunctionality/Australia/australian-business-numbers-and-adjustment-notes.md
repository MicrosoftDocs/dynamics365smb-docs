---
title: Australian Business Numbers and Adjustment Notes
description: An Australian Business Number (ABN) is a single identifier for all business dealings with the tax office and for dealings with other government departments and agencies.
author: brentholtorf
ms.topic: article
ms.search.keywords: Australian business numbers, ABN, adjustment notes, TFN, BAS adjustment
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Australian business numbers and adjustment notes

An Australian Business Number (ABN) is a single identifier for all business dealings with the tax office, and for dealings with other government departments and agencies.  

ABNs and adjustment notes—or credit memos—are used to satisfy tax requirements.  

## ABN

All companies must register and apply for an ABN to report the details of payment summaries issued to their payees during the financial year. The payment summary includes the Tax File Numbers (TFN) or business numbers of the payees.  

## Adjustment notes

Adjustment notes are issued by suppliers to a business when the amount of consideration for taxable supplies changes. The recipient needs an adjustment note to claim more or less GST credits than previously claimed.  

Section 19-10 of A New Tax System (Goods and Services Tax) Act 1999 defines an adjustment event as any event that has the effect of:  

- Canceling a supply or acquisition.  
- Changing the consideration for a supply or acquisition.  
- Causing a supply or acquisition to start or stop being a taxable supply or creditable acquisition.  

An adjustment event may result in an increase or decrease to your net amount for the tax period.  

Adjustment notes—or credit memos—should be connected to an invoice.  

Because credit memos are used for adjustment notes, each credit memo should satisfy all of the legal requirements for an adjustment note. Each credit memo should have an original invoice number, date, and reason code assigned to it. On a sales or purchase credit memo, the **Adjustment Details** FastTab includes the following fields:  

- **Adjustment**: Shows that the transaction is an adjustment transaction. [!INCLUDE[prod_short](../../includes/prod_short.md)] sets this field automatically and you can't edit it.  

- **BAS Adjustment**: Shows that you've applied the adjustment note to an invoice from an earlier period than the one the BAS relates to. [!INCLUDE[prod_short](../../includes/prod_short.md)] sets this field automatically.  

- **Adjustment Applies-to**: The number of the document that the adjustment note applies to. If you use the **Copy Document** function, this field populates automatically. You can also select the document manually, including for a paid or closed transaction. Adjustment notes can only be applied against a single document. If the **Adjustment Mandatory** setting is turned on in the **General Ledger Setup** page and you leave this field blank, you get a confirmation message before you can continue.  

- **Reason Code**: The reason code for the credit memo. Assign a reason code to satisfy the legal requirements for an adjustment note.  

## Related information

- [Enter Australian Business Numbers](how-to-enter-australian-business-numbers.md)
- [Australia Local Functionality](australia-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
