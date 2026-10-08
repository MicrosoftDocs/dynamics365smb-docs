---
author: brentholtorf
ms.topic: include
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

You must submit a periodic goods and services tax (GST) settlement, known as a BAS (Business Activity Statement) report, to the Australian Taxation Office (ATO). You create and settle the BAS report from the **BAS Return Periods** page.

## Print a goods and service tax settlement

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **BAS Return Periods**, and then choose the related link.  
1. If the period that you want to report isn't listed, choose the **Get VAT Return Periods** action to load it.  
1. Select the period, and then choose the **Create VAT Return** action to create a new BAS report, or choose **Open VAT Return Card** to continue with one that already exists.  
1. On the **BAS Report** page, choose the **Suggest Lines** action to fill the report with the GST entries for the period.  
1. Review the suggested lines, and then choose the **Release** action to lock the report so that you can settle and submit it.  
1. Choose the **Calculate and Post VAT Settlement** action, fill in the fields as described in the following table, and then choose the **OK** button to post the settlement entries.  

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Starting Date**|The first date in the period from which GST entries are processed.|  
   |**Ending Date**|The last date in the period from which GST entries are processed.|  
   |**Posting Date**|The posting date for the settlement entries.|  
   |**Document No.**|The document number of the settlement entries.|  
   |**Settlement Account**|The general ledger account to which the settlement amount is posted.|  
   |**Show VAT Entries**|Select if you want the individual GST entries to be included on the printed report. If you don't select it, only the settlement amount for each GST posting group is shown.|  
   |**Post**|Select to post the transfer to the settlement account. If you don't select it, the batch job only prints a test report.|  
   |**Show Amounts in Add. Reporting Currency**|Select if you want the reported amounts to be shown in the additional reporting currency.|  

1. Choose the **Submit** action to send the BAS report to the ATO electronically, or choose the **Print** action to print it.
