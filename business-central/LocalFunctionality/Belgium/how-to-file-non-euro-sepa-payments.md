---
title: How to File Non-Euro SEPA Payments
description: In the Belgian version of Business Central, you can file non-euro SEPA payments with the bank. This is useful when you make payments to other countries that do not use SEPA and for currencies other than the euro.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords:
ms.date: 04/01/2021
ms.author: edupont

---
# File Non-Euro SEPA Payments
In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can file non-euro SEPA payments with the bank. This is useful when you make payments to other countries that do not use SEPA and for currencies other than the euro.  

Before you can file a non-euro SEPA payment you must complete the following administration tasks:  

- Set up a new export protocol for a non-euro SEPA.  
- In the **Country/Region** table, clear the **SEPA Allowed** field for each country that belongs to the EEA zone.  
- Verify that the **Currency Euro** field in the **General Ledger Setup** table is not in euro currency.  
- Verify that the vendor's **Preferred Bank Account** field in the **Vendor** table contains the IBAN and SWIFT code.  

## To file a non-euro SEPA payment  

1.  Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **File Non Euro SEPA Payments**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Specify the general journal template for the non-euro SEPA payment report.|  
    |**Journal Batch**|Specify the general journal batch for the non-euro SEPA payment report.|  
    |**Post General Journal Lines**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**Include Dimensions**|Enter the dimensions that you want to include in the non-euro SEPA payment report. The option is available only if the **Summarize Gen. Jnl. Lines** field on the **Electronic Banking Setup** page is selected.|  
    |**Execution Date**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**File Name**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  

3.  Choose the **OK** button.  

## See Also

[Activate SEPA Payments](how-to-activate-sepa-payments.md)  
[Make Payments with the AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)  
