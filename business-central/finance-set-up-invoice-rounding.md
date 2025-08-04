---
title: Set up invoice rounding
description: If you need to round invoice amounts when you create invoices, you can use the automatic rounding function explained here.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 5, 16, 118, 459, 460, 495
ms.date: 06/10/2024
ms.service: dynamics-365-business-central

---
# Set up invoice rounding

If you need to round invoice amounts when you create invoices, you can use the automatic rounding function. When an invoice is rounded, an extra line is added with the rounding amount and posted with the other invoice lines.

> [!NOTE]  
> Local regulations or local custom might require that you to round invoice amounts in a specific way. For example, to an amount divisible by 0.05.  

To use automatic invoice rounding, you must:  

* Specify the general ledger accounts to which rounding differences are posted.  
* Set up rules for rounding invoices in local currency and in foreign currency.  
* Activate the function.  

> [!NOTE]  
>  In addition to the invoice rounding features, you can round amounts on invoices by the unit-amount rounding feature and the amount rounding feature.  

## Set up general ledger accounts for invoice rounding differences

To use automatic invoice rounding, you must set up the general ledger account or accounts where rounding differences are posted. Before you can do so, you must set up VAT product posting groups. For more information, see [Set up VAT](finance-setup-vat.md).  

### To set up general ledger accounts for invoice rounding differences  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. On the **Chart of Accounts** page, set up the account and name it **Invoice Rounding** or something similar. [!INCLUDE[prod_short](includes/prod_short.md)] uses the account name as text for invoices that are rounded.  
3. Depending on whether you use VAT or sales tax, in the **Tax Prod. Posting Group** or **VAT Prod. Posting Group** fields, choose a posting group for rounded amounts. You might want to set up a new group code to use for invoice rounding.
4. Leave the **Gen. Posting Type**, and either the **Tax Bus. Posting Group** or **VAT Bus. Posting Group** fields blank. <!-- Why do we say to leave these blank, when there are a lot of other fields we also leave blank but don't mention? -->  

Now you can assign the invoice rounding account to posting groups on the **Vendor Posting Groups** page.  <!-- Why only the vendor posting groups? -->

## Set up rounding for foreign and local currencies
Before you can use the automatic invoice rounding function, you must set up rounding rules for foreign and local currencies.

### To set up rounding for foreign currencies  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.  
2. On the **Currencies** page, choose the foreign currency to open the **Currency Card**, and then fill in the **Amount Rounding Precision**, **Unit-Amount Rounding Precision**, **Invoice Rounding Precision** and **Invoice Rounding Type** fields.

### To set up rounding for your local currency
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, on the **General** FastTab, fill in the **Inv. Rounding Precision** and **Inv. Rounding Type** fields.  

## Activate the invoice rounding function  
To ensure that sales and purchase invoices are rounded automatically, you must activate the invoice rounding function. You activate invoice rounding separately for sales and purchase invoices.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup** or **Purchases & Payables Setup**, and then choose the related link.  
2. On the **General** FastTab, choose the **Invoice Rounding** check box.  

## Related information  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases](purchasing-how-record-purchases.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
