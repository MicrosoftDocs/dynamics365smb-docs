---
author: brentholtorf
ms.topic: include
ms.date: 03/15/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
When you receive an invoice from a company in a foreign currency, it is fairly easy to calculate the local currency (LCY) value of the invoice based on today's currency rate. However, the invoice often comes with payment terms so you can delay the payment to a later date, which implies a potentially different currency rate. This issue in combination with the fact that bank currency rates always differ from the official currency rates makes it impossible to anticipate the exact local currency (LCY) amount that is required to cover the invoice. If the due date of the invoice extends to the next month, you might also have to revaluate the local currency (LCY) amount at the end of the month. The currency adjustment is necessary because the new LCY value that is required to cover the invoice amount might be different, and the company debt to the vendor has potentially changed. The new LCY amount might be higher or lower than the previous amount and will therefore represent a gain or a loss. However, since the invoice has not been paid yet, the gain or loss is considered *unrealized*. Later, the invoice is paid, and the bank has returned with the actual currency rate for the payment. It is not until now the *realized* gain or loss is calculated. This unrealized gain or loss is then reversed, and the realized gain or loss is posted instead.

In the following example, an invoice is received on January 1 with the currency amount of 1000. At the time, the currency rate is 1.123.

|Date|Action|Currency Amount|Document Rate|LCY Amount on document|Adjustment Rate|Unrealized Gains Amount|Payment Rate|Realized Losses Amount|  
|-----|----------|------------|-----------|---------|-----------|-------------|---------|---------|
|1/1|**Invoice**|1000|1.123|1123|||||
|1/31|**Adjustment**|1000||1125|1.125|2|||
|2/15|**Adjustment Reversal on payment**|1000||||-2|||
|2/15|**Payment**|1000||1120|||1.120|-3|

At the end of the month, a currency adjustment is performed where the adjustment currency rate has been set to 1.125, which triggers an unrealized gain of 2.

At the time of payment, the actual currency rate registered on the bank transaction shows a currency rate of 1.120.

Here there is an unrealized transaction, and therefore it will be reversed together with the payment.

Finally, the payment is registered and the actual loss is posted to the realized losses account.
