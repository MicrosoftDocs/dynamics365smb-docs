---
title: How to File SEPA Payments
description: In Business Central, you can use Single Euro Payments Area (SEPA) credit transfers to file SEPA payments with the bank.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# File SEPA Payments
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can use Single Euro Payments Area (SEPA) credit transfers to file SEPA payments with the bank.  

SEPA unifies payment methods in participating European countries/regions, which makes international payments as easy to process as domestic payments. European citizens and companies can make and receive payments in euros, whether within or across national borders, with the same basic conditions, rights, and obligations, regardless of location.  

Before you can file a SEPA payment, you must complete the following administration tasks:  

- Set up a new export protocol.
- In the **Country/Region** table, select the **SEPA Allowed** field for each country that belongs to the EEA zone.  
- Verify that the **Currency Euro** field in the **General Ledger Setup** table corresponds with the currency in the payment lines.  
- Verify that the vendor’s **Preferred Bank Account** field in the **Vendor** table contains the IBAN and SWIFT code.  

## To file a SEPA payment  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **File SEPA Payments**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Specify the general journal template for the SEPA payment report.|  
    |**Journal Batch**|Specify the general journal batch for the SEPA payment report.|  
    |**Post General Journal Lines**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**Include Dimensions**|Enter the dimensions that you want to include in the SEPA payment report. The option is available only if the **Summarize Gen. Jnl. Lines** field on the **Electronic Banking Setup** page is selected.|  
    |**Execution Date**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**File Name**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  

3.  Choose the **OK** button.  

## See Also  
 [Set Up Export Protocols](how-to-set-up-export-protocols.md)   
 [File Non-Euro SEPA Payments](how-to-file-non-euro-sepa-payments.md)   
 [Activate SEPA Payments](how-to-activate-sepa-payments.md)
