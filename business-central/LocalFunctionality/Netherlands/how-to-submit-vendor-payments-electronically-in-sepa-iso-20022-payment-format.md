---
    title: How to Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format
    description: In Business Central, you can create and submit Single Euro Payments Area (SEPA) ISO 20022 vendor payments electronically.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can create and submit Single Euro Payments Area (SEPA) ISO 20022 vendor payments electronically.  

Before you can create and submit SEPA vendor payments, you must enable SEPA payments. For more information, see [Activate SEPA Payments](how-to-activate-sepa-payments.md).  

## To submit vendor payments electronically in SEPA ISO 20022 payment format  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Telebank-Bank Overview**, and then choose the related link.  
2.  Select the relevant bank account, and then choose the **Proposal** action.  
3.  Select the relevant vendor bank account, and then choose the **Get Entries** action.  
4.  In the **Get Proposal Entries** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Currency Date**|Specify the currency date.|  
    |**Pmt. Discount Date**|Specify the payment discount date.|  

5.  On the **Transaction Mode** FastTab, select the appropriate filters.  
6.  On the **Cust. Ledger Entry** FastTab, select the appropriate filters.  
7.  On the **Vendor Ledger Entry** FastTab, select the **Vendor No.** filter, and then select a vendor number.  

    > [!NOTE]  
    >  Select other appropriate filters if required.  

8.  Choose the **OK** button.  

The proposal lines populate on the **Telebank Proposal** page.  

## See Also  
 [Activate SEPA Payments](how-to-activate-sepa-payments.md)   
 [Single EURO Payments Area (SEPA)](single-euro-payments-area-sepa-.md)   
