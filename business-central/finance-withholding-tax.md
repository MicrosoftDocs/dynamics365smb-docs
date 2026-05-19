---
title: Calculate withholding tax for vendors
description: This article describes how to calculate withholding tax for your vendors.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: withholding, tax, sales, purchases
ms.search.form: 
ms.date: 03/06/2026
ms.custom: bap-template
---

# Calculate withholding tax for vendors

Companies in some countries/regions must pay withholding tax to the government for certain services or vendor purchases. [!INCLUDE [prod_short](includes/prod_short.md)] calculates withholding tax for purchase invoices and orders, based on your setup for withholding tax. The tax amount is withheld from the payment and reduces the total amount you owe to the vendor.

## Set up vendors for withholding tax

To include a vendor in withholding tax calculations, on the **Vendor Card** page, turn on the **Withholding Tax Liable** toggle. Then, in the **Withholding Tax Bus. Post. Group** field, specify the general ledger account to which to post tax amounts.

## Using withholding tax

If the vendor, item, and G/L account are set up for withholding tax, [!INCLUDE [prod_short](includes/prod_short.md)] automatically calculates the tax amount when you post purchase documents that include them on their lines. However, it only creates a withholding tax entry if the value is more than the minimum threshold in the posting setup you created for withholding tax. Learn more at [Create a posting setup for withholding tax](finance-set-up-withholding-tax.md#create-a-posting-setup-for-withholding-tax). 


## Related information

[Set up withholding tax](finance-set-up-withholding-tax.md)  
[View withholding tax entries](finance-withholding-tax-entries.md)  

[Financial management](finance.md)  
