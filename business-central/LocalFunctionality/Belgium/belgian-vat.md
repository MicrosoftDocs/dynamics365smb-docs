---
title: Belgian VAT
description: Belgian enhancements of the VAT reporting feature enable you to easily print VAT transaction details.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: VAT reporting feature, print VAT transaction details, Belgian version
ms.search.form: 11300, 11301,11303,11306,11307,11308
ms.date: 04/01/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Belgian VAT

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes Belgian extensions to the VAT reporting capabilities so that you can print VAT transaction details. You must send the following reports to the Belgian tax authorities:  

- **Monthly/Quarterly declaration**: Use this report to create monthly or quarterly VAT declarations, depending on your company revenue.  

- **VAT annual listing (on paper/disk)**: Use this report to annually report all amounts invoiced for both goods and services to all Belgian companies with a registered VAT number.  

- **EC sales list**: Use this report to report the sales of goods to other countries/regions in the European Union. Learn more in [About the EC Sales List Report](../../finance-how-report-vat.md#ecsaleslist).  

You're also required to provide a printed statement detailing the VAT transactions to the Belgian tax authorities.

## Nondeductible VAT

In Belgium, VAT can be fully or partially deductible. Expenses such as representation cost or purchases of cars are only partially deductible, and the transaction must specify how much of the VAT is nondeductible. For example, you create a general ledger account for fixed assets such as cars, and another account for representation cost. For each account, you specify how much of the reported VAT is nondeductible by setting the **Percentage Non deductible VAT** field. Then, when you post a transaction, the deductible VAT posts to the corresponding VAT account. The nondeductible VAT is added to the base amount and posted to the same account as a tangible or intangible asset.  

For fixed assets, the nondeductible VAT depreciates just like the base acquisition cost of the fixed asset. You must set up separate fixed asset posting groups for each percentage of nondeductible VAT. You must do so because each fixed asset posting group posts to a general ledger account where the **Percentage Non deductible VAT** field specifies how much VAT must post to the same account as the fixed asset.  

If you select the **Incl. Non Deductible VAT** field in a VAT statement line, nondeductible VAT is included in the VAT amount. The **Calc. and Post VAT Settlement** report adds the nondeductible part of that amount to the **Non Ded. VAT Amount** and **Non Ded. Source Curr. VAT Amt.** fields in the resulting VAT entries.  

## Multiple VAT numbers for customers

The feature for using multiple VAT registration numbers for customers, including adding different **VAT Registration Numbers**, **VAT Business Posting Groups**, and **General Business Posting Groups** for addresses in another country, are available in the Belgian localization. Learn more in [Multiple VAT registration numbers](../../finance-how-use-multiple-vat-registrations.md).

In addition to different **VAT Registration Numbers**, **VAT Business Posting Groups**, and **General Business Posting Groups**, businesses using the Belgian localization also need to work with the **Enterprise No.**. When you open the **Alternative Customer VAT Registration** page, you can add the **Enterprise No.** for the customer if their address is in another country. After you enter this information, [!INCLUDE[prod_short](../../includes/prod_short.md)] does the following things when you're working with sales documents:  

- If the customer is from Belgium and the ship-to address is in Belgium, the **Enterprise No.** comes from the **Customer** card.
- If the customer is from Belgium and the ship-to address isn't in Belgium, the **Enterprise No.** is removed.
- If the customer isn't from Belgium and the ship-to address is in Belgium, the **Enterprise No.** comes from the **Alternative Customer VAT Registration** page.
- If the customer isn't from Belgium and the ship-to address isn't in Belgium, the **Enterprise No.** isn't available.  

> [!NOTE]
> If there's a change in the **Enterprise No.** in a sales document, it displays on the **Confirm Alternative Customer VAT Registration** dialog.  

## Related information

- [Belgium Local Functionality](belgium-local-functionality.md)  
- [Print Periodic VAT Reports](how-to-print-periodic-vat-reports.md)  
- [Set Up Non-Deductible VAT](how-to-set-up-non-deductible-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
