---
title: Payment lines and general journal lines [BE]
description: Business Central summarizes payment lines and journal lines across domestic, international, SEPA, and non-Euro payments.
author: brentholtorf
ms.topic: conceptual
ms.search.form: 11308
ms.search.keywords: payment lines, journal lines, SEPA, summarize payment lines, summarize journal lines, Belgian version
ms.date: 04/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Summarizing payment lines and general journal lines in the Belgian version

Business Central summarizes payment lines and journal line across the following types of payments:  

- Domestic payments  
- International payments  
- SEPA payments  
- Non-Euro SEPA payments  

## How payment journal lines are transferred to the general journal

When you export the payment journal lines to a file, [!INCLUDE[prod_short](../../includes/prod_short.md)] transfers the payment journal lines to the specified general journal. By default, a general journal line is created for each payment journal line.  

The following two fields on the **Electronic Banking Setup** page affect how the payment lines are summarized:  

- **Summarize Gen. Jnl. Lines**  
- **Cut off Payment Message Texts**  

If you select the **Summarize Gen. Jnl. Lines** checkbox on the **Electronic Banking Setup** page, [!INCLUDE[prod_short](../../includes/prod_short.md)] summarizes all payment journal lines for a specific vendor into one general journal line. The general description "Payment %1," where %1 is the vendor number, is used for the summarized journal line description. A separate payment line and a separate general journal line are created to handle:  

- Payment journal lines that contain partial payments, with both the **Partial Payment** and the **Separate Line** fields selected.  
- Payment journal lines that contain a standard format message (passes the MOD97 test), which sets **Standard Format Message** to True in the electronic banking journal.

## Example 1

In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** checkbox is selected. [!INCLUDE[prod_short](../../includes/prod_short.md)] creates:  

- One combined payment line in an XML file that has a concatenated payment message. White space is the delimiter.  
- One payment line in the general journal with a generic description that includes the vendor name.  

## Example 2

In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** checkbox is selected. The **Cut off Payment Message Texts** checkbox is cleared, and the combined SEPA and non-Euro SEPA payment lines exceed 140 characters in the payment message. [!INCLUDE[prod_short](../../includes/prod_short.md)] creates:  

- Two combined payment lines in an XML file. The first payment line contains the first concatenated payment messages. The second payment line contains the payment message from the third line.  
- One payment line in the general journal with a generic description that includes the vendor name.  

## Example 3

In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** checkbox is selected. The **Cut off Payment Message Texts** checkbox is also selected, and the combined SEPA and non-SEPA payment lines exceed 140 characters in the payment message. [!INCLUDE[prod_short](../../includes/prod_short.md)] creates:  

- One combined payment line in an XML file that has two concatenated payment messages. An ellipsis (…) is used to indicate that the message is truncated.  
- One payment line in the general journal with a generic description that includes the vendor name.  

Based on the XML structure, the payments are summarized per account number, beneficiary bank account number, and bank account number. The bank account filter can be empty.  

The EndToEndId in the SEPA message is taken from the payment message and can be truncated to the maximum length of 45 characters.  

## Related information

- [Set Up Electronic Banking](how-to-set-up-electronic-banking.md)   
- [Setting Up Finance](../../finance-setup-finance.md)  
- [Record Purchases](../../purchasing-how-record-purchases.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
