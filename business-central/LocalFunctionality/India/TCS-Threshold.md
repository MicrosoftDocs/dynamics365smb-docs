---
    title: TCS calculation considering threshold limits
    description: TCS calculation considering threshold limits

    author: v-debapd

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 04/01/2021
    ms.author: v-debapd

---
# TCS with Threshold


This topic explains the requirement of threshold amount in TCS and  the process of calculating TCS for such transactions.

## TCS calculation considering threshold limits

TCS threshold defines the threshold limit for each TCS Nature of Collection.  TCS can be deducted only if the total transaction with the assessee exceeds the threshold limit in the financial year.

If a payment under TCS Type A is below Threshold INR 20,000, no tax will be collected. Another factor to be considered is the aggregate of total payments to be made in a year. If for a customer it is expected that the threshold limit would be crossed eventually, it means Threshold is overlooked. Hence, payments received from customers can cross the TCS threshold of INR 20,000. However, if the payment expected is below the threshold limit defined, TCS will not be collected.

1. GL Entries for TCS where payment is less than the threshold limits, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|19000|
    |**Sales Account**|-19000|

2. GL Entries for TCS where payment is more than (exceeding) Threshold limits, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000| 
    |**TCS Payable Account**|287| 
    |**Customer Account**|-9713|









## See Also 
[TCS Adjustment Entry](TCS-Adjustment-Entries.md)





























[!INCLUDE[footer-include](../../includes/footer-banner.md)]