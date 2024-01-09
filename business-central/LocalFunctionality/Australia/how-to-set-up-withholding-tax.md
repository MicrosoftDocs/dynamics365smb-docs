---
 title: Set Up Withholding Tax [AU]
 description: This topic explains how a company sets up withholding tax (WHT) when it makes a payment to a vendor using the General Ledger Setup page.
 author: brentholtorf
 ms.topic: conceptual
 ms.devlang: na
 ms.tgt_pltfrm: na
 ms.workload: na
 ms.search.form: 28041, 28042, 28043, 118
 ms.date: 06/25/2021
 ms.author: bholtorf

---
# Set Up Withholding Tax in the Australian Version

Withholding tax (WHT) is the tax withheld by a company when it makes a payment to a vendor, in which the full amount owed to the vendor is reduced by the tax withheld. The withheld tax is then remitted to the Australian Taxation Office (ATO) when the next Business Activity Statement (BAS) is submitted.  

If a supplier without an Australian Business Number (ABN) provides an invoice, a withholding tax amount must be withheld if the total amount of the invoice is more than the threshold amount. To use withholding tax, you must first enable WHT in the **General Ledger Setup** page and set up product posting groups and business posting groups for WHT.  

## To enable withholding tax

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  

2. On the **Local Functionalities** FastTab, choose the **Enable WHT** field.  

3. Optionally, choose the **Round Amount for WHT Calc** field.

    If you choose this field, all WHT amounts will be rounded down to the nearest number. For example, if the WHT amount on an invoice is calculated to be 33.90, and the **Round Amount for WHT Calc** field is chosen in the General Ledger Setup, then the WHT amount will round to 33.

[!INCLUDE [wht-posting-group-setup](../includes/AUNZ/wht-posting-group-setup.md)]

## See Also

[Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)  
[View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)  
[Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)  
[Withholding Tax](withholding-tax.md)  
[Australian Taxation Office (ATO)](https://www.ato.gov.au/)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]