---
    title: Belgian Electronic Banking
    description: Electronic banking allows you to electronically exchange data with Belgian financial institutions. This ensures faster processing times and avoids errors.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 11308
    ms.date: 01/10/2022
    ms.author: bholtorf

---
# Belgian Electronic Banking

In the Belgian version of [!INCLUDE [prod_short](../../includes/prod_short.md)], you can exchange data with Belgian financial institutions  electronically. This speeds up processing time and helps avoid errors caused by manual data entry or processing.  

You can use electronic banking to perform the following functions:  

- Send electronic payments.  
- Process bank statements with CODA.  
- Process direct debits with domiciliations.  

## Setup

Before you can process electronic payments and statements, you must set up electronic banking in the **Electronic Banking Setup** page as described in the following table.

|Field|Description |
|-----|------------|
|**Summarize Gen. Jnl. Lines**| Select to indicate if you want to group the payment journal lines for each vendor. Payments with a structured message will not be grouped. |
|**Cut off Payment Message Texts** |Select to indicate if you want to truncate long payment messages. Messages will be truncated if greater than 106 characters for domestic payments and less than 140 characters for international payments. |

For information about the impact of the two fields on how payment journal lines are transferred to the general journal, see [Summarizing Payment Lines and General Journal Lines](summarizing-payment-lines-and-general-journal-lines.md).  

## See Also

[Belgium Local Functionality](belgium-local-functionality.md)  
[Belgian Electronic Payments](belgian-electronic-payments.md)  
[CODA Bank Statements](coda-bank-statements.md)  
[Direct Debit Using Domiciliation](direct-debit-using-domiciliation.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]