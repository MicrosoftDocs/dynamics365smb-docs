---
title: Belgian Electronic Banking
description: Electronic banking enables quick and error-free data exchange with Belgian financial institutions.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Belgian version, electronic banking, domiciliation, electronic banking setup, CODA
ms.search.form: 11308
ms.date: 04/01/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Belgian electronic banking

In the Belgian version of [!INCLUDE [prod_short](../../includes/prod_short.md)], you can exchange data with Belgian financial institutions  electronically. This speeds up processing time and helps avoid errors caused by manual data entry or processing.  

You can use electronic banking to perform the following functions:  

- Send electronic payments.  
- Process bank statements with CODA.  
- Process direct debits with domiciliation.  

## Setup

Before you can process electronic payments and statements, you must set up electronic banking in the **Electronic Banking Setup** page as described in the following table.

|Field|Description |
|-----|------------|
|**Summarize Gen. Jnl. Lines**| Select to indicate if you want to group the payment journal lines for each vendor. Payments with a structured message aren't grouped. |
|**Cut off Payment Message Texts** |Select to indicate if you want to truncate long payment messages. Messages are truncated if greater than 106 characters for domestic payments and less than 140 characters for international payments. |

Learn more in [Summarizing Payment Lines and General Journal Lines](summarizing-payment-lines-and-general-journal-lines.md), which explains how the two fields affect the transfer of payment journal lines to the general journal.

## Related information

- [Belgium Local Functionality](belgium-local-functionality.md)  
- [Belgian Electronic Payments](belgian-electronic-payments.md)  
- [CODA Bank Statements](coda-bank-statements.md)  
- [Direct Debit Using Domiciliation](direct-debit-using-domiciliation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
