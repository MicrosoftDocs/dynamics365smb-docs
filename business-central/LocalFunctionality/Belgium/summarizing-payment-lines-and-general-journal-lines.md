---
title: Summarizing Payment Lines and General Journal Lines
description: Business Central summarizes payment lines and journal lines.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords:
ms.date: 10/01/2020
ms.author: edupont

---
# Summarizing Payment Lines and General Journal Lines

Business Central summarizes payment lines and journal line across the following types of payments:  

- Domestic payments  
- International payments  
- SEPA payments  
- Non-euro SEPA payments  

## How Payment Journal Lines are Transferred to the General Journal

When you export the payment journal lines to a file, [!INCLUDE[prod_short](../../includes/prod_short.md)] transfers the payment journal lines to the specified general journal. By default, a general journal line is created for each payment journal line.  

The following two fields on the **Electronic Banking Setup** page affect how the payment lines are summarized:  

- **Summarize Gen. Jnl. Lines**  
- **Cut off Payment Message Texts**  

[!INCLUDE[summarize-gen-journal-lines](../includes/BE/summarize-gen-journal-lines.md)]

## Example 1

In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** check box is selected. [!INCLUDE[prod_short](../../includes/prod_short.md)] creates:  

- One combined payment line in an XML file that has a concatenated payment message. White space is the delimiter.  
- One payment line in the general journal with a generic description that includes the vendor name.  

## Example 2

In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** check box is selected. The **Cut off Payment Message Texts** check box is cleared, and the combined SEPA and non-euro SEPA payment lines exceed 140 characters in the payment message. [!INCLUDE[prod_short](../../includes/prod_short.md)] creates:  

- Two combined payment lines in an XML file. The first payment line contains the first concatenated payment messages. The second payment line contains the payment message from the third line.  

- One payment line in the general journal with a generic description that includes the vendor name.  

## Example 3

In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** check box is selected. The **Cut off Payment Message Texts** check box is also selected, and the combined SEPA and non-SEPA payment lines exceed 140 characters in the payment message. [!INCLUDE[prod_short](../../includes/prod_short.md)] creates:  

- One combined payment line in an XML file that has two concatenated payment messages. An ellipsis (…) is used to indicate that the message is truncated.  

- One payment line in the general journal with a generic description that includes the vendor name.  

Based on the XML structure, the payments are summarized per account number, beneficiary bank account number, and bank account number. The bank account filter can be empty.  

The `EndToEndId` in the SEPA message is taken from the payment message and can be truncated to the maximum length of 45 characters.  

## See Also

[Set up electronic banking](belgian-electronic-banking.md#set-up-electronic-banking)  
[Set Up Finance](../../finance-setup-finance.md)  
[Record Purchases](../../purchasing-how-record-purchases.md)  
