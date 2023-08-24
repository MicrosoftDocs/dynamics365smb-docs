---
author: brentholtorf
ms.topic: include
ms.date: 03/15/2022
ms.author: bholtorf
---
As companies operate in more countries/regions, it becomes essential that they are able to trade and report financial information in more than one currency. The local currency (LCY) is defined in the **General Ledger Setup** page as described in the article [Understanding the General Ledger and the Chart of Accounts](../finance-general-ledger.md). Once the local currency (LCY) has been defined, it will be represented as a blank currency, so when the **Currency** field is blank, it means that the currency is LCY.  

Next, you must set up currency codes for each currency that you use if you buy or sell in currencies other than your local currency (LCY). Also bank accounts can be created using currencies. It is possible to record G/L transactions in different currencies, however, the G/L transaction will always be posted in the local currency (LCY).

[!INCLUDE [finance-currencies-lcy](finance-currencies-lcy-note.md)]

Your general ledger is set up to use your local currency (LCY), but you can set it up to also use another currency with a currency exchange rate assigned. By designating a second currency as a so-called additional reporting currency, [!INCLUDE[prod_short](prod_short.md)] will automatically record amounts in both LCY and this additional reporting currency on each G/L entry and other entries, such as VAT entries. For more information, see [Set Up an Additional Reporting Currency](../finance-how-setup-additional-currencies.md). The additional reporting currency is most often used to facilitate financial reporting to owners that reside in countries/regions using different currencies than the local currency (LCY).  

> [!IMPORTANT]
> If you want to use an additional reporting currency for financial reporting, make sure that you understand the limitations. For more information, see [Set Up an Additional Reporting Currency](../finance-how-setup-additional-currencies.md).

> [!NOTE]  
> When you post to G/L using a currency code, such as to post an expense in a general journal using a currency code, the transaction is converted to LCY using the currency exchange rate for the posting date. The G/L entry will not contain information of which currency was used, only its value in LCY. If you want to keep track of the original currency, such as for an invoice, you must use the sales and purchase documents as well as bank accounts that do store currency code information for the entries.
